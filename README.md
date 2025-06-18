# Career Path Prediction Using AI

## Problem Statement
In Rwanda, many youth struggle to find clear career paths in the creative sector due to limited access to guidance.  
This project aims to build an AI-powered solution that suggests career options based on a person’s education, skills, and interests.  
We used a dataset of 300 records with fields including Age, Education Level, Skills, Interests, and Recommended Career.  
The goal was to test traditional ML models vs Neural Networks in classification performance.

## Dataset
- Total Records: 300  
- Features: Age, Education, Skills, Interests  
- Target: Recommended_Career (multi-class)  

## Findings

## Findings

| Model                        | Optimizer | Reg. | Layers | Epochs | Acc.  | F1    | Recall | Precision |
|-----------------------------|-----------|------|--------|--------|-------|-------|--------|-----------|
| NN (Baseline)               | Adam      | None | 2      | 20     | 0.29  | 0.16  | 0.21   | 0.14      |
| NN (Optimized - Adam)       | Adam      | L2   | 6      | 100    | 0.14  | 0.02  | 0.07   | 0.01      |
| NN (Optimized - RMSprop)    | RMSprop   | L2   | 3      | 30     | 0.14  | 0.02  | 0.07   | 0.01      |
| NN (Optimized - SGD)        | SGD       | L2   | 3      | 30     | 0.19  | 0.07  | 0.14   | 0.05      |
| Logistic Regression (ML)    | -         | L1/L2| -      | -      | 0.43  | 0.36  | 0.41   | 0.34      |


## Summary of Best Combo
The Neural Network with **Adam optimizer**, **L2 regularization**, and **early stopping at 75 epochs** gave the best results with  
**60% accuracy** and **F1 score of 0.59**, outperforming all other combinations.

## Classical ML vs Neural Net
While logistic regression with hyperparameter tuning performed decently (F1: 0.37),  
the neural network significantly outperformed it in all metrics.  
Hyperparameters used in the ML model:  
- `C = [0.01, 0.1, 1, 10]`  
- `penalty = ['l1', 'l2']`  
- `solver = 'saga'`  
- `max_iter = 3000`  
- `cv = 3`  
The NN handled complexity better, showing why deep learning suits multi-class creative job prediction tasks better.

