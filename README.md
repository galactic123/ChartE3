<h1> ChartE$^{3}$: A Comprehensive Benchmark for End-to-End Chart Editing
 </h1>
</div>

<div align="center">

![Data License](https://img.shields.io/badge/Data%20License-Apache--2.0-blue.svg)
![Code License](https://img.shields.io/badge/Code%20License-Apache--2.0-blue.svg)
![Python 3.9+](https://img.shields.io/badge/python-3.9.0-blue.svg)
</div>

 <div align="center">
  <!-- <a href="#model">Model</a> • -->
  📚 <a href="https://huggingface.co/datasets/lishuo123/ChartE3">Data</a> |
  📃 <a href="https://arxiv.org/abs/2601.21694">Paper</a>
</div> 

## 🎉 What's New

- **[2026.05.20]** We open-source the benchmark in [huggingface](https://huggingface.co/datasets/lishuo123/ChartE3).
- **[2026.01.29]** We created the project on github.


## 🎏 Introduction
We introduce ChartE$^{3}$, an **E**nd-to-**E**nd Chart  **E**diting benchmark that directly evaluates models without relying on intermediate natural language programs or code-level supervision. ChartE$^{3}$ focuses on two complementary editing dimensions: local editing, which involves fine-grained appearance changes such as font or color adjustments, and global editing, which requires holistic, data-centric transformations including data filtering and trend line addition.
ChartE$^{3}$ contains over 1,200 high-quality samples constructed via a well-designed data pipeline with human curation. Each sample is provided as a triplet of a chart image, its underlying code, and a multimodal editing instruction, enabling evaluation from both objective and subjective perspectives. Extensive benchmarking of state-of-the-art multimodal large language models reveals substantial performance gaps, particularly on global editing tasks, highlighting critical limitations in current end-to-end chart editing capabilities.
<!-- <div align="center">
<img src="./assets/benchmark.jpg" style="width: 100%;height: 100%">
</div> -->
<img width="1138" height="530" alt="image" src="https://github.com/user-attachments/assets/9caf9aa3-0c7d-4fca-81fd-270c5c0de1d5" />

## 🚀 Quick Start
下面是一段适合放在 GitHub README 中的 **Quick Start**：

## Quick Start

Each example in our benchmark contains three components:

* **Instruction**: the text prompt describing the desired image editing operation.
* **Origin Image**: the original input image before editing.
* **Reference Image**: the ground-truth edited image used for evaluation.

Given an instruction and a source image, an image editing model generates an edited result, which can then be evaluated against the reference image.

### Evaluation

We provide [example scripts](https://huggingface.co/datasets/lishuo123/ChartE3) for both objective and GPT-based evaluation:

* **Objective Metrics**: `example_objective_eval.py`
* **GPT-based Evaluation**: `example_gpt_eval.py`

To evaluate your generated images, first organize the outputs according to the benchmark format, and then run the corresponding evaluation script.

Please refer to the comments in the example scripts for detailed configuration options and supported evaluation metrics.

### Data Format

A typical benchmark sample is organized as follows:

```text
sample/
├── instruction.json      # editing instruction
├── origin_image.jpg           # original image
└── edit_image.jpg        # reference edited image
```

Your model should take `instruction.json` and `edit_image.jpg` as input and produce an edited image. The generated result can then be compared with `edit_image.jpg` using the provided evaluation scripts.


