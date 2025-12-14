# Small Language Model (SLM) – End-to-End Pipeline

This project demonstrates an **end-to-end pipeline** for building a **Small Language Model (SLM)** from scratch using a lightweight, synthetic dataset. The objective is to understand how language models are trained **without relying on large pretrained models**, focusing on the complete workflow: data preparation, tokenization, model design, training, and text generation.

The project uses the **TinyStories** dataset, which consists of short, simple stories generated using GPT models. Its simplicity makes it ideal for efficiently training compact language models and experimenting with custom training logic.

---

## 📂 Dataset

**Name:** TinyStories  
**Source:** HuggingFace – `roneneldan/TinyStories`

### Description
- A collection of short, coherent stories written in simple English
- Designed specifically for training small-scale language models

### Why TinyStories?
- Small vocabulary and simple sentence structures
- Low computational requirements
- Ideal for experimenting with custom language models and training pipelines

---

## 🏗️ Project Pipeline

### 1️⃣ Dataset Loading

The dataset is loaded using the HuggingFace `datasets` library. The text data is extracted and prepared for language modeling tasks.

```python
from datasets import load_dataset
ds = load_dataset("roneneldan/TinyStories")
```

---

### 2️⃣ Text Preprocessing

- Raw text is cleaned and normalized
- Data is split into training and validation sets
- Tokenization is applied to convert text into numerical representations suitable for model input

---

### 3️⃣ Vocabulary & Tokenizer

A **custom tokenizer** is built to ensure full control over the language modeling process:
- Maps words or characters to token IDs
- Handles padding and sequence truncation
- Defines special tokens (e.g., padding, unknown tokens)

---

### 4️⃣ Model Architecture

A **Small Language Model (SLM)** is implemented using a neural network architecture suitable for sequence modeling.

**Key characteristics:**
- Lightweight and computationally efficient
- Designed for educational clarity rather than large-scale performance
- Easily extendable to more advanced architectures such as Transformers

---

### 5️⃣ Training

The model is trained using the standard **language modeling objective**, where it learns to predict the next token given a sequence of previous tokens:

\[
P(w_t \mid w_1, w_2, \ldots, w_{t-1})
\]

- Loss is computed at each step
- Training and validation performance are monitored throughout the process

---

### 6️⃣ Text Generation

After training, the model is used to:
- Generate short stories
- Continue text based on user-provided prompts

This step demonstrates that the model has learned basic language structure, grammar, and coherence from the dataset.

---

## 🎯 Key Takeaways

- Provides a clear understanding of how language models are built from scratch
- Demonstrates the complete ML pipeline for sequence modeling
- Serves as a strong foundation for experimenting with larger models and Transformer-based architectures

---

## 📌 Future Extensions

- Replace the current architecture with a Transformer-based SLM
- Experiment with subword tokenization (BPE, WordPiece)
- Scale training to larger datasets
- Add evaluation metrics such as perplexity

