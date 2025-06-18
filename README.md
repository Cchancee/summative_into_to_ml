# Career Path Prediction Using AI
## Deliverables:
  - Video link: `https://drive.google.com/file/d/1bM_2jnHQgW39AbO4x7Z3O9M4tm5xgLbx/view?usp=drive_link`


## Problem Statement
In Rwanda, many youth struggle to find clear career paths in the creative sector due to limited access to guidance.  
This project aims to build an AI-powered solution that suggests career options based on a person’s education, skills, and interests.  
We used a dataset of 300 records with fields including Age, Education Level, Skills, Interests, and Recommended Career.  
The goal was to test traditional ML models vs Neural Networks in classification performance.

## Dataset
- Total Records: 300  
- Features: Age, Education, Skills, Interests  
- Target: Recommended_Career (multi-class)
- Link: `https://www.kaggle.com/datasets/adilshamim8/ai-based-career-recommendation-system?resource=download`

## Findings

| Model                   | Optimizer | Regularizer | Dropout | Learning Rate   | Epochs | Accuracy | Precision | Recall | F1 Score |
|-------------------------|-----------|-------------|---------|-----------------|--------|----------|-----------|--------|----------|
| Simple NN               | Adam      | None        | None    | Default         | 20     | 0.29     | 0.18      | 0.20   | 0.17     |
| First Model             | Adam      | L2 (0.001)  | 0.3     | 0.01            | 100    | 0.14     | 0.0095    | 0.067  | 0.017    |
| Second Model            | RMSprop   | L1 (0.001)  | 0.5     | 0.0005          | 50     | 0.14     | 0.0095    | 0.067  | 0.017    |
| Third Model             | SGD       | None        | 0.2     | 0.01            | 30     | 0.14     | 0.0095    | 0.067  | 0.017    |
| Logistic Regression     | -         | L1/L2       | -       | -               | -      | 0.43     | 0.338     | 0.411  | 0.364    |



## Summary of Best Combo
The **Logistic Regression** model with **hyperparameter tuning** gave the best results with  
**43% accuracy** and **F1 score of 0.36**, outperforming all neural network combinations.

## Classical ML vs Neural Net
While neural networks with tuned hyperparameters (various optimizers, regularizers, and dropout) struggled — topping at an F1 score of **0.17** —  
logistic regression clearly did better across all metrics.

Hyperparameters used in the ML model:  
- `C = [0.01, 0.1, 1, 10]`  
- `penalty = ['l1', 'l2']`
- `solver = 'saga'`  
- `max_iter = [500, 1000]`  
- `cv = 5` 

