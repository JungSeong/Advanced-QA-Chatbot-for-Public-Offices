# Advanced QA Chatbot for Public Offices

[한국어](README.ko.md) | [English](README.en.md)

A system enhancement project for improving both response quality and inference latency in a public-office Q&A chatbot. <br>

## Project Overview
This project improves the data construction, model training, evaluation, inference, and external-tool integration pipeline to reduce answer-format mismatches, insufficient retrieval context, and inference latency in a public-office FAQ-based question-answering system.

<details>
<summary><strong>[1] Dataset Construction and Evaluation Setup</strong></summary>

Golden datasets for training and evaluation were built from public-office FAQ source data using Chain-of-Thought(CoT) generation and the DeepEval Synthesizer.

| Data | Role | Purpose |
|------|------|---------|
| Source FAQ data | Public-office question-answer documents | Analyze domain questions and answer formats |
| Synthetic data | Data generated with the DeepEval Synthesizer | Cover diverse question expressions and answer patterns |
| Golden dataset | Train/validation/test split data | Support SFT training and LLM-as-a-Eval evaluation |

The evaluation stage separates baseline, RAG, CoT, and SFT experiments to compare response quality and response time. This setup makes it possible to measure how retrieval context, reasoning style, and supervised fine-tuning affect performance compared with a plain generation model.

</details>

<details>
<summary><strong>[2] Model Enhancement and Inference Pipeline</strong></summary>

Supervised Fine-Tuning(SFT) was applied to improve answer quality, and a vLLM-based asynchronous parallel inference pipeline was built to reduce inference latency.

| Component | Role |
|-----------|------|
| SFT | Learn public-office FAQ answer formats and domain response patterns |
| RAG | Provide retrieval context with PostgreSQL + pgvector |
| vLLM | Serve fast inference for concurrent requests |
| MCP | Connect external tools, context storage, and inference servers through a standard interface |

The inference pipeline separates RAG query, retrieved contexts, and final evaluation flows for better extensibility. It also uses the Model Context Protocol(MCP) to connect external tool calls and retrieval context through a standardized interface.

</details>

## Key Contributions

```
1. Built a Chain-of-Thought(CoT) and DeepEval Synthesizer based golden dataset, improving LLM-as-a-Eval benchmark performance by up to 22%
2. Reduced question-answer format mismatches with Supervised Fine-Tuning(SFT), and improved response speed by up to 66% with vLLM asynchronous parallel inference
3. Designed an external-tool integration structure that connects PostgreSQL + pgvector based RAG context with Model Context Protocol(MCP) tool calls
```
<br>

<img src="../pdf/preview/public-office-qa-chatbot-1.png" alt="Public-office Q&A chatbot system enhancement benchmark and architecture" width="100%">

[View Original PDF](<../pdf/관공서 Q&A 챗봇 시스템 고도화.pdf>)

## Getting Started

### 1. Set Up a Virtual Environment

```bash
git clone https://github.com/JungSeong/Advanced-QA-Chatbot-for-Public-Offices.git
cd Advanced-QA-Chatbot-for-Public-Offices
python3 -m venv .venv
source .venv/bin/activate
pip install -r docker/requirements_exaone.txt
```

The project uses Python `3.12`, as defined in `.python-version`.

### 2. Register the Virtual Environment Kernel

```bash
python3 -m ipykernel install --user --name .venv --display-name public-office-qa
```

Use this virtual environment as the kernel when running training, evaluation, inference scripts, and notebook experiments.

### 3. Run Training, Evaluation, and Inference

```bash
python main/train/main.py
python main/eval/evaluate.py
python main/infer/infer.py
```

## Repository Map

| Path | Role |
|------|------|
| `main/data/` | Source FAQ processing, synthetic data generation, and golden dataset splitting |
| `main/data/custom/` | DeepEval-based data augmentation and CoT data generation logic |
| `main/data/golden_data/` | Train/validation/test golden datasets |
| `main/train/` | SFT training configuration, prompts, and model utilities |
| `main/eval/` | LLM-as-a-Eval evaluation logic and experiment results |
| `main/infer/` | Baseline/RAG/CoT/SFT inference execution and result generation |
| `main/rag/` | PostgreSQL + pgvector based RAG indexing and search |
| `main/web/` | Web server and application entry points |
| `docker/` | Docker configuration for running vLLM, RAG, and MCP |
| `wandb/` | Training experiment logs and run history |
| `pdf/` | Project summary PDF and README preview image |
| `readme/` | Korean and English README documents |
