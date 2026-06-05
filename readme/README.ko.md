# 고급 Q&A 챗봇 시스템

[![Documentation](https://img.shields.io/badge/Documentation-GitHub%20Pages-0A66C2)](https://jungseong.github.io/projects/qa-finetune/)
[![Synthetic Data](https://img.shields.io/badge/Synthetic%20Data-Q%26A%20Augmentation-5B5FC7)](https://jungseong.github.io/projects/qa-finetune/#getting-started)
[![Fine Tuning](https://img.shields.io/badge/Fine%20Tuning-SFT%20Pipeline-FFB000)](https://jungseong.github.io/projects/qa-finetune/#getting-started)
[![Inference Workflow](https://img.shields.io/badge/Inference-Model%20Serving-0A66C2)](https://jungseong.github.io/projects/qa-finetune/#getting-started)

[한국어](README.ko.md) | [English](README.en.md)

![Q&A chatbot preview](https://jungseong.github.io/img/projects/chatbot.jpg)

공공기관 질의응답에 가까운 도메인 특화 Q&A를 대상으로 합성 데이터 생성, instruction tuning, LoRA, DeepSpeed, vLLM, Hugging Face 유틸리티를 실험한 LLM fine-tuning 프로젝트입니다.

## 문서

- [프로젝트 문서](https://jungseong.github.io/projects/qa-finetune/)
- [시작하기](https://jungseong.github.io/projects/qa-finetune/#getting-started)
- [프로젝트 구조](https://jungseong.github.io/projects/qa-finetune/#getting-started)

## 시작하기

```bash
git clone https://github.com/JungSeong/QA-FineTune.git
cd QA-FineTune
```

## 저장소 구조

| 영역 | 경로 |
| --- | --- |
| 도서관 Q&A 학습 | `도서관_QA_Finetune/final/train/main.py` |
| 도서관 Q&A 추론 | `도서관_QA_Finetune/final/infer/main.py` |
| 프롬프트 템플릿 | `도서관_QA_Finetune/final/train/prompts.py` |
| 실험 노트북 | `도서관_QA_Finetune/notebook/` |
| 법률 Q&A 실험 | `법률_QA_Finetune/` |
