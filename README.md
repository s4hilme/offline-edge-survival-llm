# 🧭 Emergency Survival Assistant (Fine-Tuning Experiment)

A lightweight experiment exploring supervised fine-tuning (SFT) on open-weights language models. This project adapts **Qwen2.5-0.5B-Instruct** into a concise, direct assistant for emergency and wilderness survival guidance using Hugging Face's `trl` library.

---

## 📌 Project Overview

- **Base Model:** `Qwen/Qwen2.5-0.5B-Instruct`
- **Training Method:** Full parameter Supervised Fine-Tuning (SFT) via `trl.SFTTrainer`
- **Dataset:** Custom instruction-response pairs formatted as chat dialogues (`survival_data.jsonl`)
- **Status:** Initial training completed; baseline safetensors saved. Quantization and output guardrails are planned for future iterations.

---

## ⚙️ Training Setup & Hyperparameters

The training was run in Google Colab using PyTorch and Hugging Face ecosystem tools:

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
├── train.py                  # Tokenization, setup, and SFTTrainer pipeline
├── survival_model_final/     # Output model weights (safetensors) & tokenizer configs
└── README.md
