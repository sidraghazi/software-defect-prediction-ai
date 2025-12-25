# Software Defect Prediction for Software Systems

## Overview
This project applies machine learning techniques to predict defect-prone software modules using historical software metrics. The objective is to support **software quality assurance (QA)** and **sustainable software development** by enabling early identification of high-risk components and more efficient allocation of testing resources.

The project emphasizes **interpretable and lightweight AI models**, making it suitable for practical QA workflows and academic analysis.

---

## Problem Statement
Software defects increase maintenance costs, lead to repeated testing cycles, and consume significant human and computational resources. Identifying defect-prone modules early can help reduce rework and improve software sustainability.

This project explores how machine learning can be used to predict defect-prone software modules based on static code and design metrics.

---

## Dataset
This project uses datasets from the **PROMISE Software Engineering Repository**, a widely recognized academic resource for software quality research.

- The datasets originate from **NASA software projects**
- Each instance represents a software module
- Metrics describe size, complexity, and coupling characteristics
- The target variable indicates whether a module is **defect-prone**
- In PROMISE datasets:
  'defects' = 1 means defect-prone
  'defects' = 0 means non-defect

### Dataset Source
PROMISE Software Engineering Repository (NASA datasets):  
🔗 https://www.kaggle.com/datasets/radowanulhaque/software-defect?resource=download 


In this project, the **CM1 dataset** was used for training and evaluation.

---

## Methodology
The following machine learning pipeline was implemented:

1. Data loading and preprocessing  
2. Train-test split with class stratification  
3. Feature scaling using standardization  
4. Logistic Regression with class-weight balancing  
5. Model evaluation using accuracy, precision, recall, F1-score, and confusion matrix  

This approach was selected to balance **performance, interpretability, and computational efficiency**.

---

## Results
The model achieves high recall for defect-prone modules, ensuring that high-risk components are successfully identified. While some false positives are introduced, this trade-off is acceptable in software quality assurance contexts where missing defects is more costly than additional inspections.

The results demonstrate the practical usefulness of the model for **test prioritization** rather than defect automation.

---

## Practical Usage in Software Testing
The defect prediction model is intended as a **decision-support tool** for QA teams:

- High-risk modules can be prioritized for deeper testing  
- Low-risk modules may receive lighter regression testing  
- Testing effort is allocated more efficiently  

This supports early defect detection and reduces unnecessary rework.

---

## Sustainability Impact
Early defect prediction contributes to sustainable software systems by:
- Reducing repeated testing cycles  
- Lowering maintenance and debugging effort  
- Improving long-term software maintainability  
- Optimizing the use of computational and human resources  

---

## Ethical Considerations
- The model does not replace human judgment  
- Predictions should be used to support, not automate, QA decisions  
- Dataset imbalance may influence prediction behavior  
- Transparency and acknowledgment of limitations are essential  

---

## Limitations and Future Work
- Class imbalance affects prediction confidence  
- The model relies on static software metrics  
- Future work may explore:
  - Ensemble learning methods  
  - Cross-project validation (e.g., CM1 → JM1)  
  - Cost-sensitive learning approaches  

---

## Technologies Used
- Python  
- pandas  
- numpy  
- scikit-learn  
- matplotlib  

---
## How to Run

To reproduce the software defect prediction experiment:

1. Clone the repository; https://github.com/sidraghazi/software-defect-prediction-ai
2. Navigate into the project directory: cd software-defect-prediction-ai
3. Create a virtual environment (recommended):  cd software-defect-prediction-ai
4. Activate the environment:
- Windows:
  ```
  venv\Scripts\activate
  ```
- macOS/Linux:
  ```
  source venv/bin/activate
  ```
5. Install dependencies
6. Run the model

---
## Sample Output

Example model performance on the CM1 dataset:
Accuracy: 0.93

Classification Report:
precision recall f1-score support

Non-Defective 1.00 0.92 0.96 90
Defective 0.59 1.00 0.74 10

accuracy 0.93 100
macro avg 0.79 0.96 0.85 100
weighted avg 0.96 0.93 0.94 100


The model achieves **perfect recall (1.00) for defect-prone modules**, ensuring that no defective components are missed.  
Although precision for defect prediction is lower, this trade-off is acceptable in software testing contexts where identifying all potential defects is more important than minimizing false positives.

The model is intended to support **test prioritization** rather than fully automated defect classification.








