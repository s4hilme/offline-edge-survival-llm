# 🧭 Emergency Survival Assistant (Fine-Tuning Experiment)

[![Hugging Face Model](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-sahil2605%2Fsurvival--qwen--0.5b-yellow)](https://huggingface.co/sahil2605/survival-qwen-0.5b)
[![Base Model](https://img.shields.io/badge/Base%20Model-Qwen2.5--0.5B--Instruct-blue)](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct)


A lightweight experiment exploring supervised fine-tuning (SFT) on open-weights language models. This project adapts **Qwen2.5-0.5B-Instruct** into a concise, direct assistant for emergency and wilderness survival guidance using Hugging Face's `trl` library.

The trained weights (`.safetensors`) and tokenizer are hosted directly on Hugging Face:  
👉 **[sahil2605/survival-qwen-0.5b](https://huggingface.co/sahil2605/survival-qwen-0.5b)**

---

## 📌 Project Overview

- **Base Model:** [`Qwen/Qwen2.5-0.5B-Instruct`](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct)
- **Fine-Tuned Checkpoint:** [`sahil2605/survival-qwen-0.5b`](https://huggingface.co/sahil2605/survival-qwen-0.5b)
- **Training Method:** Full parameter Supervised Fine-Tuning (SFT) via `trl.SFTTrainer`
- **Dataset:** Custom instruction-response pairs formatted as chat dialogues (`survival_data.jsonl`)
- **Status:** Initial training completed and published to Hugging Face Hub. Quantization and output guardrails are planned for future iterations.

---

## ⚙️ Training Setup & Hyperparameters

The training was executed in Google Colab using PyTorch and Hugging Face ecosystem tools:

| Parameter | Value |
|---|---|
| Epochs | 5 |
| Per-Device Batch Size | 2 |
| Gradient Accumulation Steps | 2 |
| Learning Rate | `3e-5` |
| Max Sequence Length | 512 |
| Precision | FP32 |
| Optimizer / Trainer | Hugging Face `SFTTrainer` |

---

## 📂 Repository Structure

```text
├── survival_data.jsonl       # Custom Q&A dataset for survival guidance
├── train.py                  # Tokenization, chat templates, and SFTTrainer pipeline
├── .gitignore                # Excludes heavy checkpoints/cache from git
└── README.md
