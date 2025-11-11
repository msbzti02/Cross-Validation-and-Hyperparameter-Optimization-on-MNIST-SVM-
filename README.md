##  Overview

This project demonstrates model validation and optimization techniques using the **MNIST handwritten digits dataset** .

The focus is on applying **cross-validation**, **RandomizedSearchCV**, and **GridSearchCV** to improve model generalization and select the optimal hyperparameters for a **Support Vector Machine** (SVM) classifier.

The project highlights the workflow of evaluating model robustness, searching hyperparameters efficiently, and comparing multiple optimization strategies — key skills in modern ML experimentation

---
##  Machine Learning Focus
###  Objective

  To train and optimize an SVM classifier for digit recognition using:
  - Cross-validation for model reliability
  - RandomizedSearchCV for efficient parameter exploration
  - GridSearchCV for fine-tuned optimization
---
##  Techniques & Methods
### 1. Dataset

- Dataset: MNIST (70,000 grayscale 28×28 images) from fetch_openml('mnist_784')
- Reduced sample size: 35,000 images for faster experimentation
- Split: 80% train / 20% test
- Labels: 10 classes (0–9)
---
### 2. Model

- Algorithm: Support Vector Machine (sklearn.svm.SVC)
- Reasoning :
 SVM is robust for high-dimensional data and small-to-medium datasets.
It is commonly used as a benchmark for image recognition tasks like MNIST.
---
### 3. Cross-Validation

Used 5-fold Cross-Validation to measure model performance consistency.

Splits training data into 5 subsets and averages accuracy.

<img width="494" height="31" alt="image" src="https://github.com/user-attachments/assets/c86913bb-86a4-4fb3-b41b-9f487d47b666" />

Purpose:
To reduce overfitting risk and ensure the model generalizes well to unseen data.

---
## 4. Hyperparameter Optimization
###  RandomizedSearchCV

- Randomly samples parameter combinations from a defined distribution.
- Efficient when search space is large.

Parameters searched:

<img width="776" height="135" alt="image" src="https://github.com/user-attachments/assets/2ba9de6c-40fc-4358-ba9c-d66ac12c9565" />


Purpose:
To identify promising hyperparameter regions quickly.
--- 
###  GridSearchCV

- Performs exhaustive search over a smaller, refined hyperparameter grid.
- Builds on the best region found by RandomizedSearchCV.

<img width="533" height="138" alt="image" src="https://github.com/user-attachments/assets/80b4f942-ece6-4b85-8b93-003f26095d64" />

Purpose:
To fine-tune hyperparameters for the best-performing model.

--- 
## 5. Model Evaluation

<img width="501" height="441" alt="image" src="https://github.com/user-attachments/assets/3da3aea7-f467-44d0-95fa-4b378ababc42" />

<img width="749" height="478" alt="image" src="https://github.com/user-attachments/assets/116fd5e1-fc32-4924-8418-d5ff5c69ec44" />

--- 

##  Results Summary

| Method | Description | Accuracy |
|:--|:--|:--:|
| **5-Fold Cross Validation** | Baseline SVM with default hyperparameters | 0.970 |
| **RandomizedSearchCV** | Random search across parameter space | ~0.975 |
| **GridSearchCV** | Fine-tuned best region from RandomizedSearchCV | ~0.978 |


✅ Best model: SVM (RBF kernel, C=10, gamma=‘scale’)

✅ Test Accuracy: ≈ 97.8%

✅ Consistent Cross-Validation Performance (min: 0.9688, max: 0.9718)

--- 

##  Key Concepts

| Concept | Explanation |
|:--|:--|
| **Cross-Validation** | Reduces overfitting and provides a stable estimate of model performance. |
| **Bias–Variance Tradeoff** | Observed by comparing train/test performance across folds. |
| **RandomizedSearchCV** | Efficient hyperparameter search using random sampling. |
| **GridSearchCV** | Precise, exhaustive parameter tuning. |
| **Model Selection** | Choosing the best estimator based on validation accuracy. |
| **Confusion Matrix Analysis** | Evaluates per-class classification strengths and weaknesses. |



--- 

Mourad Sleem

mouradbshina@gmail.com
