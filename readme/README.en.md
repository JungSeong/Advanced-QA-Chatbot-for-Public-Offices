# Advanced Q&A Chatbot System

[![Documentation](https://img.shields.io/badge/Documentation-GitHub%20Pages-0A66C2)](https://jungseong.github.io/projects/qa-finetune/)
[![Synthetic Data](https://img.shields.io/badge/Synthetic%20Data-Q%26A%20Augmentation-5B5FC7)](https://jungseong.github.io/projects/qa-finetune/#getting-started)
[![Fine Tuning](https://img.shields.io/badge/Fine%20Tuning-SFT%20Pipeline-FFB000)](https://jungseong.github.io/projects/qa-finetune/#getting-started)
[![Inference Workflow](https://img.shields.io/badge/Inference-Model%20Serving-0A66C2)](https://jungseong.github.io/projects/qa-finetune/#getting-started)

[한국어](README.ko.md) | [English](README.en.md)

![Q&A chatbot preview](https://jungseong.github.io/img/projects/chatbot.jpg)

Domain-specific Q&A fine-tuning experiments for public-office style inquiries, including synthetic data generation, instruction tuning, LoRA, DeepSpeed, vLLM, and Hugging Face model utilities.

## Documentation

- [Live project documentation](https://jungseong.github.io/projects/qa-finetune/)
- [Getting Started](https://jungseong.github.io/projects/qa-finetune/#getting-started)
- [Repository Map](https://jungseong.github.io/projects/qa-finetune/#getting-started)

## Getting Started

```bash
git clone https://github.com/JungSeong/QA-FineTune.git
cd QA-FineTune
```

## Repository Map

| Area | Path |
| --- | --- |
| Library Q&A training | `도서관_QA_Finetune/final/train/main.py` |
| Library Q&A inference | `도서관_QA_Finetune/final/infer/main.py` |
| Prompt templates | `도서관_QA_Finetune/final/train/prompts.py` |
| Experiment notebooks | `도서관_QA_Finetune/notebook/` |
| Legal Q&A experiments | `법률_QA_Finetune/` |
