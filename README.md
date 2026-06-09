<div align="center">
  <a href="https://github.com/your-username/Awesome-Quantization">
    <img src="./banner.svg" alt="Awesome Quantization Banner" width="100%">
  </a>

  # 🚀 Awesome-Quantization

  [![Awesome](https://awesome.re/badge.svg)](https://github.com/ishandutta2007/awesome-awesome-awesome)
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![Deep Learning](https://img.shields.io/badge/Field-Deep%20Learning-blue)](https://en.wikipedia.org/wiki/Deep_learning)
  [![Quantization](https://img.shields.io/badge/Focus-Model%20Compression-orange)](#)
  [![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](#)

  **A curated list of model quantization types, techniques, and advanced LLM optimization methods.**

  [Introduction](#-introduction) • [Table of Contents](#-table-of-contents) • [Contribute](#-contribute)
</div>

---

## 📖 Introduction

**Model Quantization** is the process of compressing continuous or high-precision values (like FP32) into lower-precision formats (like INT8 or INT4). This critical optimization technique saves memory, reduces power consumption, and speeds up computation—enabling complex AI models to run on edge devices and consumer hardware.

---

## 🗂️ Table of Contents

1. [By Data Format & Distribution](#1-by-data-format--distribution)
2. [By Mathematical Approach](#2-by-mathematical-approach-ai--signal-processing)
3. [By Workflow in Deep Learning](#3-by-workflow-in-deep-learning)
4. [By Activation Computation Method](#4-by-activation-computation-method)
5. [Advanced LLM Quantization Methods](#5-advanced-llm-quantization-methods)
6. [Useful Resources](#-useful-resources)

---

## 1. 📊 By Data Format & Distribution

Mapping continuous signals to discrete scales.

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Uniform Quantization** | 📏 All quantization intervals are equal in size. Maps continuous values into a discrete, linear integer scale. Includes *Mid-Tread* and *Mid-Rise*. | 1948 | [Bennett (1948)](https://ieeexplore.ieee.org/document/6773231) |
| **Non-Uniform Quantization** | 📈 Step sizes are unequal. Smaller intervals are assigned to frequent values, maintaining accuracy where needed (e.g., audio coding). | 1957 | [Lloyd (1957)](https://ieeexplore.ieee.org/document/1056489) |

## 2. 🧮 By Mathematical Approach (AI & Signal Processing)

The logic behind point-wise or group-wise mapping.

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Scalar Quantization** | 📍 Each input value is quantized entirely independently, without considering surrounding data points. | 1948 | [Oliver et al. (1948)](https://ieeexplore.ieee.org/document/6773232) |
| **Vector Quantization** | 📦 Groups multiple values together into a vector and quantizes them as a single unit using a predefined "codebook". | 1980 | [Linde et al. (1980)](https://ieeexplore.ieee.org/document/1094577) |
| **Symmetric vs. Asymmetric** | ⚖️ *Symmetric:* Maps values symmetrically around zero. *Asymmetric:* Dynamically scales and offsets the range, mapping zero perfectly. | 2018 | [Jacob et al. (2018)](https://arxiv.org/abs/1712.05877) |

## 3. ⚙️ By Workflow in Deep Learning

When and how quantization is integrated into the training pipeline.

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Post-Training Quantization (PTQ)** | 🛠️ A fully trained model's weights and activations are quantized after training. Highly efficient for edge devices. | 2018 | [Krishnamoorthi (2018)](https://arxiv.org/abs/1806.08342) |
| **Quantization-Aware Training (QAT)** | 🎓 Simulates precision loss during training. The model learns to compensate for the lower-precision format. | 2015 | [Courbariaux et al. (2015)](https://arxiv.org/abs/1511.00363) |

## 4. ⚡ By Activation Computation Method

Handling dynamic ranges during inference.

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **Static Quantization** | 🧊 The range (min/max) of weights and activations is pre-calculated using a "calibration" dataset before inference. | 2018 | [Jacob et al. (2018)](https://arxiv.org/abs/1712.05877) |
| **Dynamic Quantization** | 🌊 The scaling range for activations is computed on the fly during inference, offering higher accuracy with slight overhead. | 2018 | [Krishnamoorthi (2018)](https://arxiv.org/abs/1806.08342) |

## 5. 🤖 Advanced LLM Quantization Methods

State-of-the-art algorithms for Large Language Model compression.

| Type | Description | Year | Paper / Source |
| :--- | :--- | :--- | :--- |
| **GGUF** | 📁 Optimized file format for running LLMs on consumer hardware (especially CPUs), offering various bit depths. | 2023 | [llama.cpp (2023)](https://github.com/ggerganov/llama.cpp) |
| **GPTQ** | 💎 Layer-wise weight quantization minimizing the Mean Squared Error (MSE) between original and quantized outputs. | 2022 | [Frantar et al. (2022)](https://arxiv.org/abs/2210.17323) |
| **AWQ** | 🎯 Activation-aware Weight Quantization. Preserves high-impact outlier weights to maintain output quality. | 2023 | [Lin et al. (2023)](https://arxiv.org/abs/2306.00978) |
| **QLoRA** | 🐍 Combines quantization with Low-Rank Adaptation (LoRA), storing weights in 4-bit and fine-tuning on a single GPU. | 2023 | [Dettmers et al. (2023)](https://arxiv.org/abs/2305.14314) |

---

## 🔗 Useful Resources

*   📚 [NVIDIA: Model Quantization Concepts](https://nvidia.com)
*   🤗 [Hugging Face: Quantization Documentation](https://huggingface.co)
*   🎥 [Neural Network Compression Explained (YouTube)](#)

---

## 🤝 Contribute

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

<div align="center">
  Made with ❤️ for the AI Community
</div>
