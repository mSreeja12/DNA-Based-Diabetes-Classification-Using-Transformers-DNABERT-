# 🧬 DNABERT-Based DNA Sequence Classification for Diabetes Prediction

> Predicting Type 1 Diabetes, Type 2 Diabetes, and Non-Diabetic sequences from genomic DNA using Transformers (DNABERT)  
> **Model Accuracy:** 📈 **73.73%**

---

## 📌 Overview

This project implements a deep learning pipeline using **DNABERT**, a DNA-specific version of the BERT model, to classify genomic DNA sequences into three categories:
- **Type 1 Diabetes (DMT1)**
- **Type 2 Diabetes (DMT2)**
- **Non-Diabetic (NONDM)**

DNABERT treats DNA like a biological language, enabling deep understanding of patterns and mutations in genetic sequences.

---

## 📂 Dataset

- **Source:** Public Kaggle dataset on diabetic-related DNA sequences.
- **Files:**
  - `SKRIPSI_Data_DM_DNA_Sequence.csv` — Labeled sequences with:
    - `sequence`: DNA string (A, T, G, C)
    - `length`: Length of the sequence
    - `class`: DMT1 / DMT2 / NONDM

---

## ⚙️ Methodology

### 🔬 Preprocessing
- Converted DNA sequences into **k-mers** (6-mers) — substrings of length 6 — to tokenize sequences for BERT.
- Used `zhihan1996/DNA_bert_6` tokenizer and model from Hugging Face.

### 🔎 Model
- Model: **TFBertForSequenceClassification**
- Pretrained weights: `zhihan1996/DNA_bert_6` (loaded with `from_pt=True`)
- Fine-tuned on the diabetic DNA dataset

### 🧠 Training
- 80/20 Train-Validation split
- Optimizer: Adam with learning rate `2e-5`
- Loss: SparseCategoricalCrossentropy
- Batch size: 8
- Epochs: 3

---

## 📈 Results

- **Final Accuracy:** `73.73%`
- **Evaluation:** Used `classification_report()` from `sklearn` to assess precision, recall, and F1-score

---

## 💡 Use Cases

- 🔬 **Genomic Disease Prediction**: Early detection of diabetes predisposition through DNA analysis
- 🧬 **Precision Medicine**: Tailoring treatments based on patient-specific genetics
- 🧫 **Bioinformatics Research**: Automating DNA sequence classification tasks

