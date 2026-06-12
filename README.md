# TextVQA and Grounding Finetuning with Qwen2.5-VL

<p align="right">
  <a href="#english">English</a> | <a href="#chinese">中文</a>
</p>

<a id="english"></a>
<details open>
<summary><strong>English</strong></summary>

## Overview
A compact training repository for domain-specific Qwen2.5-VL fine-tuning on TextVQA and grounding-style vision-language tasks.

## Highlights
- Uses Qwen2.5-VL as the base model.
- Provides a main supervised fine-tuning entry point in `sft.py`.
- Includes both 4-GPU and 8-GPU DeepSpeed / Accelerate launch scripts.
- Ships configs, download helpers, an inference notebook, and data conversion scripts.

## Repository Layout
- `configs/`: model and DeepSpeed configuration files.
- `scripts/`: download, conversion, launch, inference, and merge helpers.
- `sft.py`: main supervised fine-tuning entry point.
- `vision_datacollator.py`: multimodal batch collation logic.
- `utils.py`: shared utility functions.
- `inference_scripts.ipynb`: notebook for quick inference checks.
- `docs/original-readme.md`: preserved copy of the original project README.

## Getting Started
```bash
pip install -r requirements.txt
bash scripts/download_data.sh
bash scripts/download_model.sh
python scripts/convert2sft_format.py
bash scripts/sft_vqa_4gpu-z2.sh configs/SFT_Qwen2_5-VL-3B-Instruct_vqa.yaml
```

Use `scripts/sft_vqa_8gpu-z2.sh` when training on an 8-GPU node.

</details>

<a id="chinese"></a>
<details>
<summary><strong>中文</strong></summary>

## 项目简介
这是一个面向 TextVQA 和 grounding 类视觉语言任务的紧凑训练仓库，用于 Qwen2.5-VL 的领域微调。

## 项目亮点
- 以 Qwen2.5-VL 作为基础模型。
- 在 `sft.py` 中提供主监督微调入口。
- 同时提供 4 卡和 8 卡的 DeepSpeed / Accelerate 启动脚本。
- 包含配置文件、数据 / 模型下载辅助脚本、推理 notebook，以及数据转换脚本。

## 仓库结构
- `configs/`：模型与 DeepSpeed 配置文件。
- `scripts/`：下载、转换、启动、推理和合并辅助脚本。
- `sft.py`：监督微调主入口。
- `vision_datacollator.py`：多模态 batch 拼装逻辑。
- `utils.py`：通用工具函数。
- `inference_scripts.ipynb`：快速推理检查 notebook。
- `docs/original-readme.md`：保留的原始 README 副本。

## 快速开始
```bash
pip install -r requirements.txt
bash scripts/download_data.sh
bash scripts/download_model.sh
python scripts/convert2sft_format.py
bash scripts/sft_vqa_4gpu-z2.sh configs/SFT_Qwen2_5-VL-3B-Instruct_vqa.yaml
```

如果在 8 卡节点上训练，请使用 `scripts/sft_vqa_8gpu-z2.sh`。

</details>