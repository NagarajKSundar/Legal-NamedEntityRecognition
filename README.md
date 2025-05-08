# 🏛️ L-NER: Legal Named Entity Recognition for Indian Court Documents

**📦 Dataset**: [IL-TUR / lner on Hugging Face](https://huggingface.co/datasets/Exploration-Lab/IL-TUR/tree/main/lner)

---

## 📌 Overview

**Legal Named Entity Recognition (L-NER)** aims to identify domain-specific named entities in Indian legal documents. Standard NER systems often misclassify these entities under generic types (like `PERSON`). L-NER solves this by using more fine-grained legal entity labels such as `JUDGE`, `APPELLANT`, `RESPONDENT`, etc.

This task is crucial for:
- Legal information extraction
- Legal knowledge graph construction
- Anonymization of sensitive names
- Training unbiased legal NLP systems

---

## 📂 Dataset Summary

- **Source**: [Indian Kanoon](https://www.indiankanoon.org/)
- **Language**: English
- **Jurisdictions**: Supreme Court and High Courts of India
- **Total Documents**: 105
- **Splits**:
  - `fold_1`: 35 documents
  - `fold_2`: 35 documents
  - `fold_3`: 35 documents

---

## 🏷️ Entity Labels

The following 12 entity types are annotated:

| Label | Description            |
|-------|------------------------|
| APP   | Appellant              |
| RESP  | Respondent             |
| A.COUNSEL | Appellant Counsel |
| R.COUNSEL | Respondent Counsel |
| JUDGE | Judge                  |
| WIT   | Witness                |
| AUTH  | Authority              |
| COURT | Court                  |
| STAT  | Statute                |
| PREC  | Precedent              |
| DATE  | Date                   |
| CASENO | Case Number           |

---

## 📄 Data Format

Each document is a JSON object structured as:

```json
{
  "id": "115651329",
  "text": "REPORTABLE IN THE SUPREME COURT OF INDIA...",
  "spans": [
    { "start": 137, "end": 153, "label": 1 },
    { "start": 252, "end": 261, "label": 10 }
  ]
}
```


## 📝 Field Explanation

- **id**: Unique case identifier  
- **text**: Full text of the legal judgment  
- **spans**: List of named entities with:  
  - **start**: Start character index of the entity  
  - **end**: End character index (exclusive)  
  - **label**: Entity class ID (0–11)  

---

## 🧪 Task Objective

Formally, L-NER is a sequence labeling task using the **BIO tagging scheme**:

- `B-X`: Beginning of entity X  
- `I-X`: Inside entity X  
- `O`: Outside any entity  

The model must correctly identify both:

1. The exact character span of the entity  
2. The appropriate legal class  

---

## 📊 Evaluation Metrics

We use **strict macro-averaged scores**:

- **Precision (mP)**: Entity match + label match  
- **Recall (mR)**  
- **F1-score (mF1)**  

> A predicted entity is **only correct** if both its **span and label** match exactly.

---

---

## 💡 Applications

- Legal search engines  
- Summarization of legal texts  
- Knowledge base population  
- Legal document anonymization  

---

## 📜 License & Credits

- Dataset available under the terms on [Hugging Face](https://huggingface.co/datasets/Exploration-Lab/IL-TUR/tree/main/lner)  
- Annotated by legal experts (law professors and graduates)  

---

## 🙌 Acknowledgements

Thanks to the researchers, legal scholars, and the open-source community for supporting this initiative to make legal AI more transparent and accessible.
