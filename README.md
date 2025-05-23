# 🧠 Wordle Solver with Qwen2.5 (LLM-Powered)

This project demonstrates how a Large Language Model (LLM) — specifically **Qwen2.5 7B Instruct** — can be prompted and fine-tuned to master the logic and strategy behind the popular word game **Wordle**. Using prompt engineering, response parsing, and Reinforcement Fine-Tuning (RFT), the model is guided to think through guesses and learn from feedback in a structured, interpretable way.

---

## 🚀 Features

- 🔡 Solves Wordle using **step-by-step reasoning**
- 🔄 Simulates **6-turn gameplay loop**
- ⚙️ Implements a **prompt-based feedback mechanism**
- 🤖 Uses both **base and fine-tuned LLMs** for performance comparison
- 🧪 Supports **interactive play** and evaluation

---

## 🧠 Model Info

- **Base Model**: [`Qwen/Qwen2.5-7B-Instruct`](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct)
- **Inference Platform**: Predibase (OpenAI-compatible)
- **Fine-Tuned Adapter**: `wordle-dlai/2` (trained via RFT)

---

## 🛠️ Requirements

- Python 3.8+
- `transformers`
- `openai`
- `python-dotenv`
- `re`, `enum`, `dataclasses`, `typing`

Install dependencies:

```bash
pip install -r requirements.txt
🔧 Setup
Clone this repo
```
Create a .env file in the root directory with:
PREDIBASE_API_KEY=your_api_key
PREDIBASE_MODEL_QWEN_URL=https://serving.app.predibase.com/<tenant_id>/deployments/v2/llms/<model_name>/v1

Run the script:
```
python Wordle.py
```
---
### Gameplay Logic
The model receives a structured system prompt with Wordle rules and example feedback.

After each guess, the script updates the prompt with new feedback using <think> and <guess> tags.

The model streams its reasoning and final guess using OpenAI’s .completions.create().

### Try It Out
You can test both:

Base model performance

Fine-tuned model performance (adapter_id="wordle-dlai/2")

Update the secret word in the script and try different runs to see how the LLM handles reasoning and pattern recognition.

---
### Learning Objectives
This project is part of a larger study in:

Foundation Models and LLM reasoning

Prompt Engineering

Reinforcement Fine-Tuning (RFT)

AI interpretability and step-by-step logic

### Related Topics
LLMs and Games

Chain-of-Thought prompting

Model reasoning in constrained environments

Few-shot and zero-shot learning
