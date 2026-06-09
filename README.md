# Awesome-Quantization
## Model Quantization Types

Quantization compresses continuous or high-precision values (like FP32) into lower-precision formats (like INT8 or INT4). This saves memory and speeds up computation. The top types range from foundational signal processing categories to advanced algorithmic techniques used in AI and Large Language Models (LLMs).

## 1. By Data Format & Distribution

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Uniform Quantization** | All quantization intervals are equal in size. It maps continuous values into a discrete, linear integer scale. Includes *Mid-Tread* (zero maps to a level) and *Mid-Rise* (zero falls between levels). | 1948 | [Bennett (1948)](https://ieeexplore.ieee.org/document/6773231) |
| **Non-Uniform Quantization** | The step sizes are unequal. Smaller intervals are assigned to frequently occurring values, maintaining accuracy where needed (e.g., speech or audio coding). | 1957 | [Lloyd (1957)](https://ieeexplore.ieee.org/document/1056489) |

## 2. By Mathematical Approach (AI & Signal Processing)

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Scalar Quantization** | Each input value is quantized entirely independently, without considering surrounding data points. | 1948 | [Oliver et al. (1948)](https://ieeexplore.ieee.org/document/6773232) |
| **Vector Quantization** | Groups multiple values together into a vector and quantizes them as a single unit using a predefined "codebook". | 1980 | [Linde et al. (1980)](https://ieeexplore.ieee.org/document/1094577) |
| **Symmetric vs. Asymmetric** | *Symmetric:* Maps values symmetrically around zero. *Asymmetric:* Dynamically scales and offsets the range, mapping the exact zero value perfectly. | 2018 | [Jacob et al. (2018)](https://arxiv.org/abs/1712.05877) |

## 3. By Workflow in Deep Learning

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Post-Training Quantization (PTQ)** | A fully trained model's weights and activations are quantized after training. Highly efficient for edge devices. | 2018 | [Krishnamoorthi (2018)](https://arxiv.org/abs/1806.08342) |
| **Quantization-Aware Training (QAT)** | Simulates the loss of precision during training. The model learns to compensate for the lower-precision format. | 2015 | [Courbariaux et al. (2015)](https://arxiv.org/abs/1511.00363) |

## 4. By Activation Computation Method

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Static Quantization** | The range (min/max) of weights and activations is pre-calculated using a "calibration" dataset before inference. | 2018 | [Jacob et al. (2018)](https://arxiv.org/abs/1712.05877) |
| **Dynamic Quantization** | The scaling range for activations is computed on the fly during inference, offering higher accuracy with slight overhead. | 2018 | [Krishnamoorthi (2018)](https://arxiv.org/abs/1806.08342) |

## 5. Advanced LLM Quantization Methods

Running massive models locally often relies on highly specialized post-training algorithms:

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **GGUF** | A file format optimized for running LLMs on consumer hardware (especially CPUs), offering various quantization bits. | 2023 | [llama.cpp (2023)](https://github.com/ggerganov/llama.cpp) |
| **GPTQ** | Layer-wise weight quantization that minimizes the Mean Squared Error (MSE) between original and quantized outputs. | 2022 | [Frantar et al. (2022)](https://arxiv.org/abs/2210.17323) |
| **AWQ** | Activation-aware Weight Quantization. It preserves high-impact outlier weights to maintain output quality while shrinking models. | 2023 | [Lin et al. (2023)](https://arxiv.org/abs/2306.00978) |
| **QLoRA** | Combines quantization with Low-Rank Adaptation (LoRA), storing weights in 4-bit and fine-tuning on a single GPU. | 2023 | [Dettmers et al. (2023)](https://arxiv.org/abs/2305.14314) |

## Useful Resources

* [NVIDIA: Model Quantization Concepts](https://nvidia.com)
* [Hugging Face: Quantization Documentation](https://huggingface.co)
