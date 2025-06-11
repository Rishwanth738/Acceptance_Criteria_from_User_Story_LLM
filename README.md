# 🧠 Acceptance Criteria Generator with LoRA Fine-Tuned Mistral

This project fine-tunes [`mistralai/Mistral-7B-Instruct-v0.3`](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.3) using [LoRA (Low-Rank Adaptation)](https://arxiv.org/abs/2106.09685) to generate **structured acceptance criteria** — both positive and negative — from plain English user stories.

---

## 🚀 What It Does

Given a user story like:

> As a user, I want to reset my password if I forget it.

It outputs JSON like this:

```json
{
  "positive_criteria": [
    { "criterion": "User can request password reset via email.", "role": "System" },
    { "criterion": "System sends reset link within 2 minutes.", "role": "System" }
  ],
  "negative_criteria": [
    { "criterion": "User should not be able to reset without a valid email.", "role": "User" }
  ]
}
```

Perfect for:
- QA Engineers 🧪  
- Product Owners 📋  
- Agile Dev Teams 🔁  

---

## 🧪 How It Works

✅ Fine-tunes Mistral-7B using Hugging Face's `transformers`, `peft`, and `trl`  
✅ Uses QLoRA for memory-efficient training (yes, it runs on Colab or Kaggle)  
✅ Accepts `.jsonl` data with prompt + completion format  
✅ Outputs JSON-formatted criteria with role tagging  

---

## Usage

### 🏋️‍♂️ Fine-Tuning (Colab/Kaggle)

This repo includes:
- Training script
- Dataset
- LoRA adapter weights

 Check out the Kaggle notebook here: **https://www.kaggle.com/code/rishwanthj/acceptance-criteria-generator-from-user-story**

---


##  Requirements

- Python 3.10+
- `transformers`, `peft`, `trl`, `bitsandbytes`, `datasets`, `accelerate`
- GPU (Colab, Kaggle, or local A100/T4 — your call)


---


## 📎 Related Resources

- [LoRA Paper](https://arxiv.org/abs/2106.09685)  
- [Transformers Fine-Tuning Guide](https://huggingface.co/docs/transformers/training)  

