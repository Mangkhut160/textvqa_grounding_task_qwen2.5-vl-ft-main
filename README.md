# TextVQA and Grounding Finetuning with Qwen2.5-VL

A compact training repository for domain-specific Qwen2.5-VL fine-tuning on TextVQA and grounding-style vision-language tasks.

## Project Snapshot
- Base model: Qwen2.5-VL
- Training entry point: `sft.py`
- Launch modes: 4-GPU and 8-GPU DeepSpeed / Accelerate scripts
- Assets included: configs, download helpers, inference notebook, and data conversion scripts

## Workflow
1. Install dependencies from `requirements.txt`
2. Download data and model assets with the helper scripts
3. Convert raw data into supervised fine-tuning format
4. Launch training with the provided 4-GPU or 8-GPU scripts
5. Run inference or merge artifacts for downstream use

## Repository Layout
- `configs/`: model and DeepSpeed configuration files
- `scripts/`: download, conversion, launch, inference, and merge helpers
- `sft.py`: main supervised fine-tuning entry point
- `vision_datacollator.py`: multimodal batch collation logic
- `utils.py`: shared utility functions
- `inference_scripts.ipynb`: notebook for quick inference checks
- `docs/original-readme.md`: preserved copy of the original project README

## Quick Start
```bash
pip install -r requirements.txt
bash scripts/download_data.sh
bash scripts/download_model.sh
python scripts/convert2sft_format.py
bash scripts/sft_vqa_4gpu-z2.sh configs/SFT_Qwen2_5-VL-3B-Instruct_vqa.yaml
```

Use `scripts/sft_vqa_8gpu-z2.sh` when training on an 8-GPU node.

## Notes
The repository was flattened so the actual training code now sits at the repository root instead of inside a nested folder.