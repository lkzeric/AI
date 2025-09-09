# High-Level Goal
  - Task
    - Perform channel decoding of Polar Codes with CRC under an AWGN channel.
  - Method
    - Break down the traditional Polar code min-sum / BP-style decoding process into multiple L/R message-passing layers.
    - Insert learnable thresholds and scaling parameters (called Neural Ex-BP) into certain layers. 
    - Train these parameters in TensorFlow using cross-entropy loss, with the expectation of outperforming fixed-rule decoders by reducing BER/loss.


# End-to-End Data Pipeline
  - Generate random messages
    - Create bit sequences (message) of length N_message.
    - Apply CRC encoding → concatenate into N_message_polar.
    - Embed into the Polar codeword of length N_polar (place info/frozen bits).
    - Perform Polar encoding → get codeword {0,1}, then map to BPSK {-1,+1}.
    - Add AWGN noise (controlled by SNR_in_db).

  - Forward propagation (forwardprop)
    - Convert to LLR: channel_LLR = 2 * x / sigma^2.
    - Run a sequence of R/L propagation layers (message passing on the Polar factor graph) using min-sum updates (f(x,y) = sign * min).
    - Insert Neural Ex-BP at selected layers:
    - Apply learnable parameters (alpha, beta, threshold) to scale/threshold messages (via sim_step + linear combination), stabilizing or reinforcing the message flow.
    - At the end, rearrange LLRs and extract the information-bit LLRs → polar_output_llr.
    - Define logits as y_hat = -sim_sign(polar_decoded_llr).
  
  - Training Objective
    - Loss: sigmoid_cross_entropy_with_logits(labels=y, logits=y_hat) → binary cross-entropy per bit.
    - Metric: Compute bit errors → report BER.
    - Optimization: Adam (learning_rate=2e-4), train for N_epochs, each epoch processes N_codewords (batched).

  - Validation
    - Fix the trained parameters.
    - Generate a large batch of codewords, run forward propagation, and compute total loss and BER.

⸻

# Key Components and Parameters
  - Polar Code Structure:
    - B_N: bit-reversal permutation matrix.
    - G_polar: Polar code generator matrix.
    - frozen_indexes / info_indexes: frozen and information bit positions.

  - L/R propagation:
    - R layers: use decision LLRs (frozen bits set to large constant BIG_NUM) to propagate upward.
    - L layers: combine channel LLRs with reverse messages, propagate downward.
    - Layers are interlaced/concatenated to follow the Polar butterfly structure.
    - Neural Ex-BP (Learnable extension)
    - After some L-layer updates, apply:
    
upper = upper * alpha_c + previous_layer * beta_c * step(|previous_layer| - threshold_c) + upper * (1 - step(|previous_layer| - threshold_c))

lower = lower * alpha_c + previous_layer * beta_c * step(|previous_layer| - threshold_c) + lower * (1 - step(|previous_layer| - threshold_c))


  - Intuition: 
    - Use a threshold to judge message strength. Apply different scaling for “strong” messages, reducing distortions where vanilla min-sum struggles.
	

# One-Sentence Summary

  - This program represents Polar code decoding as a deep message-passing network in TensorFlow, where selected updates are augmented with learnable scaling and thresholds (Neural Ex-BP).
  - It trains these parameters with supervised learning using binary cross-entropy to improve decoding accuracy over traditional fixed rules.