# Supervised Learning Algorithms Comparison  
**STAT 542 Final Project** | University of Illinois Urbana-Champaign  
**Team Members**: Zibo Gong, Jiayi Yu, Hanqi Tang, Hao Liang  
**Date**: May 10, 2025  

---

## 📌 Problem Statement  
We benchmark six supervised learning models under constrained computational resources. 
Using the **CIFAR-10 dataset** (60k 32×32 RGB images across 10 classes), we evaluate:  
- **Primary Metric**: Test accuracy (target ≥ 0.65)  
- **Secondary Metrics**: Log-loss, per-class F1 scores  
- **Constraints**: Google Colab T4 GPU (8GB VRAM), ≤5 epochs for deep/Bayesian models  

---

## 🎯 Goals  
1. Compare model families (LR, Random forest, KNN, etc.) under identical hardware limits  
2. Identify the best accuracy-efficiency tradeoff for low-resolution image classification  
3. Provide reproducible Colab implementations for each approach  

---

## 🛠 Methodology

| Model                              | Key Setup                                                                 | Accuracy | Log-loss |
|------------------------------------|---------------------------------------------------------------------------|----------|----------|
| **Logistic Regression (With PCA)** | PCA=200, default(C=1, solver='lbfgs'), max_iter=500                       | 0.41     | 1.71     |
| **Logistic Regression**            | No PCA, default(C=1, solver='lbfgs'), max_iter=500 (convergence warning)  | 0.39     | 1.79     |
| **Random Forest**                  | 50 trees, random_state=42                                                 | 0.41     | 1.90     |
| **KNN**                            | PCA=200, k=5, metric='euclidean'                                          | 0.36     | 12.28    |
| **MLP (With PCA)**                 | PCA=200, hidden_layer=1000, max_iter=20, random_state=42                  | 0.56     | 1.75     |
| **MLP**                            | No PCA, hidden_layer=1000, max_iter=20, random_state=42                   | 0.50     | 1.42     |


---

## 📂 Repository Structure 
- experiment implementation/ # Colab implementation (.ipynb)
- report/ # Final paper (LaTeX/PDF)
- Project overview.md
