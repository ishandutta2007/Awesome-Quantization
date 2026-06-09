# Awesome-Quantization
## Model Quantization Types

Quantization compresses continuous or high-precision values (like FP32) into lower-precision formats (like INT8 or INT4). This saves memory and speeds up computation. The top types range from foundational signal processing categories to advanced algorithmic techniques used in AI and Large Language Models (LLMs).

## 1. By Data Format & Distribution

* **Uniform Quantization:** All quantization intervals are equal in size. It maps continuous values into a discrete, linear integer scale.
  * *Mid-Tread:* The zero amplitude is mapped directly to a quantization level.
  * *Mid-Rise:* Zero is not a direct quantization level, but falls between levels.
* **Non-Uniform Quantization:** The step sizes are unequal. Smaller intervals are assigned to frequently occurring values, which maintains accuracy where it is most needed (e.g., speech or audio coding).

## 2. By Mathematical Approach (AI & Signal Processing)

* **Scalar Quantization:** Each input value is quantized entirely independently, without considering surrounding data points.
* **Vector Quantization:** Groups multiple values together into a vector and quantizes them as a single unit using a predefined "codebook". This preserves fidelity in highly correlated signals like images and audio.
* **Symmetric vs. Asymmetric:**
  * *Symmetric:* Maps values symmetrically around zero.
  * *Asymmetric:* Dynamically scales and offsets the range of values, mapping the exact zero value of your data perfectly.

## 3. By Workflow in Deep Learning

* **Post-Training Quantization (PTQ):** A fully trained model's weights and activations are quantized after the training process. It is highly efficient for shrinking models for edge devices.
* **Quantization-Aware Training (QAT):** Simulates the loss of precision during the actual training phase. The model naturally learns to compensate for the lower-precision format, yielding higher accuracy.

## 4. By Activation Computation Method

* **Static Quantization:** The range (min/max) of weights and activations is pre-calculated using a representative "calibration" dataset before inference. It is fast but can be sensitive to data outliers.
* **Dynamic Quantization:** The scaling range for activations is computed on the fly during inference. This generally results in higher accuracy but incurs slight computational overhead.

## 5. Advanced LLM Quantization Methods

Running massive models locally often relies on highly specialized post-training algorithms:

* **GGUF:** A file format optimized for running LLMs on consumer hardware (especially CPUs), offering a wide range of quantization bits (e.g., Q4_K_M, Q8_0).
* **GPTQ:** Layer-wise weight quantization that minimizes the Mean Squared Error (MSE) between original and quantized outputs.
* **AWQ:** Focuses on "Activation-aware Weight Quantization". It preserves high-impact outlier weights to maintain output quality while shrinking model sizes.
* **QLoRA:** Combines quantization with Low-Rank Adaptation (LoRA), storing model weights in 4-bit and performing fine-tuning on a single GPU.

## Useful Resources

* [NVIDIA: Model Quantization Concepts](https://nvidia.com)
* [Hugging Face: Quantization Documentation](https://huggingface.co)
