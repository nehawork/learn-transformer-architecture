# 🧠 Understanding LLaMA-2 (7B) – A Visual Exploration

Welcome to Day 3 of my [#100DaysOfAI](https://www.linkedin.com/feed/hashtag/100DaysOfAI/) journey!
This project is all about **demystifying how Transformer models work** — specifically Meta's **LLaMA-2 (7B)** — using **Python**, **Hugging Face**, and **visualization tools** like PCA and Seaborn.

> 🔬 "Transformers feel like black boxes. This notebook peeks inside — layer by layer, token by token."

---

## 📌 What This Notebook Does

✅ Load the **LLaMA-2 7B** model using Hugging Face Transformers
✅ Tokenize input and visualize **4096-dimensional token embeddings**
✅ Track how token representations evolve after each transformer layer
✅ Predict the next token and list top-k predictions with probabilities
✅ Use **PCA** to project high-dimensional vectors into 2D space
✅ Make AI *interpretable* and *visual*

---

## 🧩 Key Components

### 1. Load Model & Tokenizer
```python
from transformers import AutoTokenizer, AutoModelForCausalLM

model_id = "meta-llama/llama-2-7b-hf"

tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(
    model_id,
    torch_dtype=torch.float16,
    device_map="auto"
)
```

> 🔐 You’ll need access to gated models like LLaMA-2 via Hugging Face Hub login.

---

### 2. Input a Sentence
```python
sentence = "Cricket is a"
```
Tokenized, embedded, and passed through the model layer by layer.

---

### 3. Visualize Embeddings
We use **PCA** and **Seaborn** to visualize token vectors at three stages:

- Before any transformer layers
- After the first transformer layer
- After the final transformer layer

This shows how token meaning is shaped progressively through the network.

---

### 4. Predict the Next Token
Example output:
```
Predicted Next Token: 'game'

Top 5 Predictions:
1. game     → 0.1456
2. bat      → 0.1400
3. sport    → 0.1207
4. team     → 0.0682
5. popular  → 0.0511
```

---

## 💡 Why This Matters

Transformers work by **building meaning** through attention across layers.
This notebook:

- Makes those transformations visible
- Helps debug, understand, and interpret model behavior
- Bridges theory with practice

---

## 🙋‍♀️ About Me

I'm **Neha**, a Senior Software Developer transitioning into **AI Engineering**.
Follow my [100 Days of AI](https://github.com/stars/nehawork/lists/100daysofai) journey as I learn, build, and share!

📍 [LinkedIn](https://www.linkedin.com/in/neha-ramchandani-2898nr)
📍 [GitHub 100 Days Progress](https://github.com/stars/nehawork/lists/100daysofai)

---

## 📬 Feedback

If you're exploring LLM internals, model visualization, or interpretability — let’s connect!
Feel free to fork, star ⭐️, or open an issue!

