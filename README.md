# Code-Mix-Hindi-Marathi-Sentiment-Analysis
Research project on sentiment analysis of Hindi–Marathi code-mixed social media text written in Roman script. The study integrates transliteration to Devanagari, applies transformer models (MuRIL, IndicBERT, XLM-R, mBERT), and evaluates with K-Fold validation, and cross-script experiments.


# Sentiment Analysis of Code-Mixed Hindi–Marathi Text in Roman Script

This repository contains the research project and implementation for **Sentiment Analysis of Code-Mixed Hindi–Marathi Social Media Text in Roman Script**, conducted as part of the MSc Big Data Science program at Queen Mary University of London under the supervision of Prof. Haim Dubossarsky.

The project explores the challenges of sentiment classification in code-mixed text where Hindi and Marathi are written in **Roman script**—a frequent phenomenon on social media. The study introduces a transliteration-driven pipeline, applies multiple transformer models, and evaluates performance through advanced strategies such as **K-Fold validation**, **dataset subset evaluation**, and **cross-script generalization**.


## 🔑 Key Objectives
- Build a robust pipeline for Hindi–Marathi code-mixed sentiment analysis.  
- Apply Roman → Devanagari transliteration for compatibility with Indic pretrained models.  
- Benchmark baseline transformer models (MuRIL, IndicBERT, XLM-R, mBERT).  
- Optimize models using **Optuna hyperparameter tuning**.  
- Fine-tune models with **Stratified K-Fold cross-validation**.  
- Evaluate across **three dataset types** (intra-sentential, inter-sentential, tag-switch).  
- Conduct **cross-script experiments** (Roman ↔ Devanagari).  

---

## 📂 Repository Structure
project-root/
│
├── notebooks/
│ └── analysis.ipynb # Jupyter Notebook with full pipeline
├── data/
│ └── dataset.csv, Inter-sentential.csv, Intra_sentential.csv, Tag_Switch.csv # Annotated code-mixed dataset
├── dashboard/
│ └── dashboard.html # Interactive HTML dashboard
├── essay/
│ └── report.pdf / report.docx # Detailed academic essay
└── README.md # Project documentation

---

## 🛠️ Methodology
1. **Data Collection** – 300 manually annotated samples from YouTube, Twitter, and public docs.  
   - Intra-sentential, Inter-sentential, and Tag-switch subsets.  
   - Balanced Positive/Negative labels.  
   - Ambiguity list for overlapping Hindi–Marathi words.  

2. **Preprocessing** –  
   - Roman text cleaning (lowercasing, URL/user mention removal, tokenization, stopword removal, lemmatization).  
   - Roman → Devanagari transliteration using `indic-transliteration`.  
   - Devanagari-specific preprocessing (punctuation removal, stopword filtering).  

3. **Modeling** –  
   - Baselines: MuRIL, IndicBERT, XLM-R, mBERT.  
   - Hyperparameter tuning with **Optuna** (learning rate, batch size, epochs, freezing).  
   - Fine-tuning with **Stratified K-Fold cross-validation**.  

4. **Evaluation** –  
   - **Within-script**: Accuracy on test splits.  
   - **Subset-level**: Performance on intra/inter/tag-switch datasets.  
   - **Cross-script**: Training on Roman, testing on Devanagari (and vice versa).  

---

## 📊 Results (Highlights)
- **Fine-tuned Accuracies (K-Fold):**  
  - MuRIL: **83.3% ± 2.9%**  
  - mBERT: 79.9% ± 2.1%  
  - IndicBERT: 68.5% ± 5.7%  
  - XLM-R: 59.8% ± 7.7%  

- **Dataset Subset Evaluation (MuRIL):**  
  - Intra-sentential: 80%  
  - Inter-sentential: 75%  
  - Tag-switch: 93.7%  

- **Cross-Script Evaluation (MuRIL):**  
  - Roman → Devanagari: 78.3%  
  - Devanagari → Roman: 66.7%  

MuRIL consistently demonstrated superior performance, especially in **cross-script generalization**.

---
