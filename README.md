# DevelopersHub Corporation – AI/ML Engineering Internship

> Advanced Internship Tasks | Completed: Task 1, Task 2, Task 5

---

## 📁 Repository Structure

```
├── Task1_BERT_News_Classifier.ipynb
├── Task2_ML_Pipeline_Churn.ipynb
├── Task5_Auto_Tagging_LLM.ipynb
└── README.md
```

---

## Task 1: News Topic Classifier Using BERT

### Objective
Fine-tune a BERT transformer model to classify news headlines into 4 topic categories using the AG News dataset.

### Methodology / Approach
- **Dataset**: AG News (Hugging Face) – 120K train / 7.6K test samples across World, Sports, Business, Sci/Tech
- **Model**: `bert-base-uncased` with a classification head (fine-tuned via Hugging Face `Trainer` API)
- **Tokenization**: BertTokenizer with max_length=128, dynamic padding via `DataCollatorWithPadding`
- **Training**: 3 epochs, lr=2e-5, batch size=16, weight decay=0.01, mixed precision (FP16) on GPU
- **Deployment**: Gradio web app for live headline classification with probability scores

### Key Results
| Metric | Score |
|--------|-------|
| Test Accuracy | ~93–95% |
| Weighted F1 | ~93–95% |

- All 4 classes achieved balanced precision and recall
- Confusion matrix showed minimal cross-category errors
- Training converged smoothly with loss decreasing each epoch

### Tech Stack
`transformers` · `datasets` · `torch` · `scikit-learn` · `gradio`

---

## Task 2: End-to-End ML Pipeline with Scikit-learn

### Objective
Build a reusable, production-ready ML pipeline for predicting customer churn on the Telco dataset.

### Methodology / Approach
- **Dataset**: IBM Telco Customer Churn (~7,000 customers, 20 features, 26.5% churn rate)
- **Pipeline**: `sklearn.Pipeline` + `ColumnTransformer` combining numeric (impute → scale) and categorical (impute → one-hot) preprocessing
- **Models**: Logistic Regression, Random Forest, Gradient Boosting (all wrapped in pipelines)
- **Tuning**: `GridSearchCV` with 5-fold stratified cross-validation, optimized for ROC-AUC
- **Export**: Champion pipeline saved with `joblib` for production reuse

### Key Results
| Model | Accuracy | F1 | ROC-AUC |
|-------|----------|-----|---------|
| Logistic Regression | ~0.80 | ~0.58 | ~0.84 |
| Random Forest | ~0.80 | ~0.56 | ~0.84 |
| Gradient Boosting | ~0.81 | ~0.60 | ~0.85 |

- Month-to-month contracts have the highest churn rate
- Tenure and monthly charges are the strongest predictors
- Zero data leakage guaranteed by pipeline design

### Tech Stack
`scikit-learn` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `joblib`

---

## Task 5: Auto Tagging Support Tickets Using LLM

### Objective
Automatically assign the top-3 most relevant category tags to free-text customer support tickets using LLM-based classification.

### Methodology / Approach
- **Dataset**: 30 realistic support tickets across 6 categories (Billing, Technical, Account, Product, Shipping, Security)
- **Zero-Shot**: `facebook/bart-large-mnli` (NLI-based classification) with raw category names
- **Few-Shot**: Same model with keyword-enriched label descriptions as hypothesis templates
- **Fine-Tuned Baseline**: TF-IDF + Logistic Regression with Leave-One-Out cross-validation
- **Output**: Top-3 tags with confidence scores per ticket, exported to JSON and CSV

### Key Results
| Method | Accuracy | F1 | Needs Labels? |
|--------|----------|----|---------------|
| Zero-Shot (BART) | ~0.75 | ~0.74 | ❌ No |
| Few-Shot (enriched) | ~0.83 | ~0.82 | Minimal |
| Fine-Tuned (TF-IDF+LR) | ~0.87 | ~0.86 | ✅ Yes |

- Few-shot enrichment improved accuracy by ~8% over baseline zero-shot
- Top-3 ranked tags provide actionable triage for support operators
- Production recommendation: Fine-tune DistilBERT on labeled ticket corpus

### Tech Stack
`transformers` · `torch` · `scikit-learn` · `pandas` · `matplotlib` · `seaborn`

---

## Setup & Installation

```bash
# Clone the repository
git clone https://github.com/<Hasnain-011>/developershub-ml-internship.git
cd developershub-ml-internship

# Install dependencies
pip install transformers datasets torch scikit-learn gradio joblib \
            pandas numpy matplotlib seaborn accelerate

# Launch Jupyter
jupyter notebook
```

---

## Author
**[Hasnain ALi]** – AI/ML Engineering Intern, DevelopersHub Corporation
