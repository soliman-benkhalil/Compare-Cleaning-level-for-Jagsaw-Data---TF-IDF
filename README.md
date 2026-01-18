# Compare-Cleaning-level-for-Jagsaw-Data---TF-IDF

This project compares light vs deep text cleaning strategies on the Jigsaw Toxic Comments dataset, showing how both **preprocessing depth and model capacity** impact neural network performance and convergence in NLP classification tasks.

---

## Text Cleaning Depth vs Model Performance  
**Toxic Comment Classification (Jigsaw Dataset)**

This project studies how different levels of text preprocessing affect the performance and convergence behavior of a deep learning model in a toxic comment classification task, while also improving the underlying neural architecture.

Rather than changing the task, this work controls two tightly related factors:

- The **depth of text cleaning**
- The **strength of the neural architecture**

---

## 🔍 Project Motivation

Text preprocessing is often treated as a fixed step in NLP pipelines.  
However, every cleaning decision injects assumptions into the data, and every architectural decision controls how well sparse textual features can be learned.

This project investigates:

- How much cleaning is really beneficial?
- When does cleaning start to remove useful semantic signal?
- How does model capacity interact with preprocessing depth?
- How does this affect convergence stability?

---

## 🧠 Model

Compared to the previous project, the model here is **stronger and deeper**:

- TF-IDF feature size increased: **5000 → 8000**
- Deeper fully-connected architecture
- Heavy use of **Batch Normalization + Dropout** to control overfitting on sparse text representations

All experiments in this repository use:

- The same optimizer and loss function
- The same training strategy

Only the **cleaning pipeline** is varied between runs.

This ensures that performance differences are primarily driven by preprocessing depth, under a fixed (but improved) model capacity.

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
Text cleaning is not neutral — it is a modeling choice that interacts strongly with model capacity.

---

## 📈 Exploratory Data Analysis (EDA)

Detailed dataset analysis and label distribution studies are provided in a separate project:

👉 https://github.com/soliman-benkhalil/Toxic-Comment-Classification

This repository focuses on modeling behavior rather than dataset exploration.

---

## 🛠️ Tech Stack

- Python  
- NLTK  
- Scikit-learn (TF-IDF)   

---

## 🚀 Future Work

- Embedding-based representations (Word2Vec, FastText)
- Transformer tokenization comparison
- Robustness vs noise trade-off analysis
- Feature importance before & after cleaning

---

If you find this project useful, feel free to ⭐ the repository.
