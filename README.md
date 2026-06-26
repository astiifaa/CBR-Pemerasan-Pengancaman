# Case-Based Reasoning (CBR) for Criminal Defamation and Threat Cases

## Project Overview

This project implements a **Case-Based Reasoning (CBR)** system to retrieve and reuse previous Indonesian Supreme Court decisions related to **criminal defamation (pencemaran nama baik)** and **threat (pengancaman)** cases.

The system follows the complete CBR cycle:

1. Case Base Construction
2. Case Representation
3. Case Retrieval
4. Case Solution Reuse
5. Model Evaluation

The project was developed as the final assignment for the **Computer Reasoning** course.

---

# Repository Structure

```
CBR-Pemerasan-Pengancaman/
│
├── data/
│   ├── raw/
│   │   ├── pdf/
│   │   └── text/
│   │
│   ├── processed/
│   │   ├── clean_text/
│   │   ├── final_text/
│   │   ├── cases.csv
│   │   └── case_representation.csv
│   │
│   ├── evaluation/
│   │   ├── queries.json
│   │   ├── retrieval_metrics.csv
│   │   ├── prediction_metrics.csv
│   │   └── evaluation_result.csv
│   │
│   └── results/
│       ├── predictions.csv
│       └── top5_similarity.csv
│
├── notebooks/
│   ├── tahap1_pdf_to_text.ipynb
│   ├── tahap2_cleaning.ipynb
│   ├── tahap2_case_representation.ipynb
│   ├── tahap3_retrieval.ipynb
│   ├── tahap4_predict.ipynb
│   └── tahap5_evaluation.ipynb
│
├── requirements.txt
└── README.md
```

---

# Dataset

The dataset consists of **40 Indonesian Supreme Court (Mahkamah Agung) criminal decisions** related to:

- Criminal Defamation
- Insult
- Threat
- Reputation Damage

Each document is converted from PDF into plain text before preprocessing.

---

# Requirements

Install all required Python libraries:

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install pandas
pip install numpy
pip install scikit-learn
pip install transformers
pip install torch
pip install sentence-transformers
pip install matplotlib
pip install tqdm
pip install joblib
```

---

# How to Run

Run the notebooks sequentially.

## Step 1 — Build Case Base

```
notebooks/tahap1_pdf_to_text.ipynb
```

Output:

- Raw text documents

---

## Step 2 — Text Cleaning & Case Representation

```
notebooks/tahap2_cleaning.ipynb
```

Continue with

```
notebooks/tahap2_case_representation.ipynb
```

Output:

- Clean text
- Metadata extraction
- Case representation
- cases.csv
- case_representation.csv

---

## Step 3 — Case Retrieval

```
notebooks/tahap3_retrieval.ipynb
```

This notebook performs:

- TF-IDF vectorization
- IndoBERT embedding
- Train-test splitting (80:20)
- Similarity calculation
- Top-k retrieval
- Retrieval evaluation

Outputs:

- queries.json
- top5_similarity.csv

---

## Step 4 — Case Solution Reuse

```
notebooks/tahap4_predict.ipynb
```

This stage:

- Extracts previous court decisions
- Applies weighted similarity
- Predicts legal outcome
- Generates predictions.csv

---

## Step 5 — Model Evaluation

```
notebooks/tahap5_evaluation.ipynb
```

Evaluation includes:

- Accuracy
- Precision
- Recall
- F1-score
- Retrieval evaluation
- Prediction evaluation
- Error analysis
- Performance visualization

Outputs:

- retrieval_metrics.csv
- prediction_metrics.csv

---

# Example Query

```
Penghinaan dengan kata "anjing" kepada seseorang di depan umum
```

Example output:

```
Top-5 Similar Cases
Predicted Decision
Similarity Score
```

---

# Models Used

### Retrieval

- TF-IDF
- IndoBERT

### Similarity

- Cosine Similarity

### Prediction

- Majority Voting
- Weighted Similarity

---

# Evaluation Metrics

The following metrics are used:

- Accuracy
- Precision
- Recall
- F1-Score

Implemented using:

```
sklearn.metrics
```

---

# Results

The system successfully performs:

- Case representation
- Similar case retrieval
- Legal outcome prediction
- Retrieval evaluation
- Prediction evaluation

---

# Author

**Radhiya Astifa**
**Ricah Cinta Sari**

Computer Science Undergraduate Student

Universitas Muhammadiyah Malang

Course:
Computer Reasoning

2026
