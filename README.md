<div>

<h1 align="center">UIT-ViCorpReviews: A Benchmark Dataset for Multi-Dimensional Sentiment and Toxic Span Detection in Vietnamese Workplace Context</h1>

</div>

<p align="center">
  <img src="common/img/VLAISOS_ViVQAGPTOSS.png" alt="VLAI" height="30%"/>
</p>

This repository contains the official implementation for **GPT-OSS-VQA**, a modular and extensible framework designed for Visual Question Answering (VQA) tasks. Our approach leverages the powerful dense captioning capabilities of the **Gemini 2.5 Model** to provide rich context for Large Language Models (LLMs), enabling more accurate and detailed answers to visual queries.

This framework is built with a focus on modularity, performance, and ease of use, making it suitable for both research and practical applications.

<details>
<summary><b>Table of Contents</b></summary>

- [Features](#features)
- [Experimental Results](#experimental-results)
  - [ViVQA-X](#vivqa-x)
  - [OpenViVQA](#openvivqa)
- [Getting Started](#getting-started)
  - [Setup and Installation](#setup-and-installation)
  - [Usage](#usage)
- [Framework Guides](#framework-guides)
  - [Configuration](#configuration)
  - [Evaluation](#evaluation)
- [Programmatic Usage](#programmatic-usage)
- [Citation](#citation)
- [Acknowledgements](#acknowledgements)

</details>

## Features

- **Modular Architecture**: Decoupled components for data handling, model inference, and captioning, allowing for easy extension and modification.
- **Multi-Model Support**: Seamlessly integrates multiple LLMs, including Gemini, Qwen3, and DeepSeek, for comparative analysis.
- **High-Performance Inference**: Utilizes `vLLM` and `unsloth` for optimized, high-throughput inference on modern GPUs.
- **Rich Context Generation**: Employs `Gemini-Pro-2.5` model to generate detailed, object-aware image descriptions that enhance LLM reasoning.
- **Comprehensive Tooling**: Includes scripts for batch processing, automated evaluation on standard benchmarks (OpenViVQA, ViVQA-X), and detailed result analysis.
- **Resilience and Efficiency**: Features automatic job resumption, multi-threaded data loading, and periodic progress saving.



## Experimental Results

### ViVQA-X

| Mode           | BLEU@4 | ROUGE-L | METEOR | CIDEr | SPICE | BERTScore | FLOPs ↓ | Time (s) ↓ |
|----------------|--------|---------|--------|-------|-------|-----------|---------|------------|
| GPT-OSS Low    | 0.135  | 0.635   | 0.407  | 1.181 | 0.504 | 0.848     | 54,854  | 282        |
| GPT-OSS High   | 0.141  | 0.641   | 0.413  | 0.840 | 0.570 | 0.820     | 98,884  | 3,317      |
| **GPT-OSS Ada (Ours)** | **0.142** | **0.654** | **0.421** | 1.022 | 0.503 | 0.839     | 62,356  | 815        |


### OpenViVQA

| Mode           | BLEU@4 | ROUGE-L | METEOR | CIDEr | SPICE | BERTScore | FLOPs ↓ | Time (s) ↓ |
|----------------|--------|---------|--------|-------|-------|-----------|---------|------------|
| GPT-OSS Low    | 0.091  | 0.340   | 0.214  | 0.584 | 0.156 | 0.732     | 113,699 | 480        |
| GPT-OSS High   | 0.072  | 0.295   | 0.171  | 0.452 | 0.185 | 0.695     | 258,089 | 7,602      |
| **GPT-OSS Ada (Ours)** | 0.085  | 0.326   | 0.200  | 0.542 | **0.212** | 0.719     | 163,574 | 3,009      |



## Getting Started

To get started with the framework, please follow the detailed setup and usage guides.

### Setup and Installation

Our comprehensive setup guide provides detailed instructions for environment preparation, dependency installation, and model/dataset acquisition. It covers system requirements, virtual environment setup, and verification steps to ensure a smooth start.

**➡️ [View Full Setup Guide](./common/md/SETUP.md)**

### Usage

The usage guide explains how to run inference, perform batch processing, and evaluate models on benchmark datasets. It includes command-line examples for various scenarios.

**➡️ [View Full Usage Guide](./common/md/USAGE.md)**

## Framework Guides

For advanced users and researchers, we provide in-depth guides on configuring the framework and running evaluation protocols.

### Configuration

The configuration system is designed for flexibility. You can easily modify data paths, model parameters, and processing settings. This guide details the structure of the configuration files and how to customize them.

**➡️ [View Full Configuration Guide](./common/md/CONFIG.md)**

### Evaluation

This guide provides instructions on how to run the evaluation scripts, interpret the results, and perform comparative analysis between different models and configurations.

**➡️ [View Full Evaluation Guide](./common/md/EVALUATION.md)**

## Programmatic Usage

The modular design of the framework allows for easy integration into your own Python projects. You can import and use the components directly for custom workflows.

```python
from src.config import DAMConfig, CaptioningConfig
from src.captioner import run_captioning

# 1. Setup configurations
dam_config = DAMConfig(model_path='nvidia/DAM-3B-Self-Contained')
caption_config = CaptioningConfig(csv_path='my_captions.csv')

# 2. Define image source
image_folder = '/path/to/your/images'

# 3. Run the captioning process
run_captioning(image_folder, dam_config, caption_config)

print(f"Captions saved to {caption_config.csv_path}")
```

## Citation

If you use this framework or our findings in your research, please consider citing our paper.

```bibtex
@misc{nhan2025gptossvqa,
  author    = {Dai-Nhan Tran, Phuc-Thinh Nguyen, Tue-Anh Vu, Bao Do, Hai-Au Trinh, Anh-Khoi Nguyen},
  title     = {Difficulty-Aware Adaptive Reasoning for Vietnamese VQA with GPT-OSS},
  year      = {2025},
  publisher = {},
  journal   = {},
  howpublished = {\url{https://github.com/hugebenevolence/ViVQA_GPT-OSS_DRA}},
}
```

## Acknowledgements

This project is built upon the excellent work of several open-source projects and research contributions. We would like to extend our gratitude to:
- The teams behind [Unsloth](https://github.com/unslothai/unsloth) and [vLLM](https://github.com/vllm-project/vllm) for their high-performance inference libraries.
- The maintainers of the [OpenViVQA](https://github.com/nghiangh/OpenViVQA-dataset) and [ViVQA-X](https://github.com/duongtruongbinh/ViVQA-X) datasets.
- The Hugging Face team for the `transformers` and `accelerate` libraries.

