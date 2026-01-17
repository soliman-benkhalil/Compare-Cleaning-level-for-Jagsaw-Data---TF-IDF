# Compare-Cleaning-level-for-Jagsaw-Data---TF-IDF
This project compares light vs deep text cleaning strategies on the Jigsaw Toxic Comments dataset, showing how preprocessing depth directly impacts neural network performance in NLP classification tasks.

# Text Cleaning Depth vs Model Performance  
**Toxic Comment Classification (Jigsaw Dataset)**

This project studies how different levels of text preprocessing affect the performance and convergence behavior of a deep learning model in a toxic comment classification task.

Rather than changing the model, this work isolates one variable:

> **The depth of text cleaning.**

---

## 🔍 Project Motivation

Text preprocessing is often treated as a fixed step in NLP pipelines.  
However, every cleaning decision injects assumptions into the data.

This project investigates:
- How much cleaning is really beneficial?
- When does cleaning start to remove useful semantic signal?
- How does preprocessing depth affect training stability and convergence?

---

## 🧠 Model

- Same neural network architecture for all experiments  
- Same optimizer, loss function, and training strategy  
- Input representation: **TF-IDF features**

Only the **text cleaning pipeline** is changed.

This ensures that performance differences are caused by preprocessing, not by model design.

---

## 🧹 Cleaning Strategies

### 1. Light Cleaning
- Lowercasing  
- Whitespace normalization  

Preserves most of the original linguistic and stylistic information.

---

### 2. Deep Cleaning
- Unicode normalization (emoji & non-ASCII removal)  
- Repetition normalization  
- Contraction expansion  
- URL & Email removal  
- Non-alphabetic filtering  
- Stopword removal  
- Lemmatization  
- Token length filtering  

Introduces stronger normalization but risks removing semantic and emotional cues.

---

## 📊 Key Findings

- Light cleaning achieved better test performance.
- Light cleaning converged faster and more smoothly.
- Deep cleaning required more epochs and showed slower early learning.

**Conclusion:**  
Text cleaning is not neutral — it is a modeling choice.

---

## 📈 Exploratory Data Analysis (EDA)

Detailed dataset analysis, distribution studies, and label exploration were conducted in a separate project:

👉 https://github.com/soliman-benkhalil/Toxic-Comment-Classification

This repository focuses on the modeling and preprocessing impact rather than dataset exploration.

---

## 🛠️ Tech Stack

- Python  
- NLTK  
- Scikit-learn (TF-IDF)  
- TensorFlow / Keras  

---

## 🚀 Future Work

- Embedding-based representations (Word2Vec, FastText)
- Transformer tokenization comparison
- Robustness vs noise trade-off analysis
- Feature importance before & after cleaning

---

If you find this project useful, feel free to ⭐ the repository.

