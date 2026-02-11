# Fraud Detection - Model Evaluation (Recall & F1 Focus)

## Context
Fraud detection is a highly imbalanced classification problem where accuracy is not a reliable performance metric.

This project evaluates classification models with emphasis on Recall and F1 Score, which are more appropriate for fraud detection scenarios.

## Objective
- Train classification models
- Evaluate performance using:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
- Interpret results from a business perspective

## Why Recall Matters
In fraud detection, false negatives (missed fraud cases) are typically more costly than false positives.
Therefore, Recall is prioritized over Accuracy.

## Key Concepts Demonstrated
- Handling imbalanced datasets
- Model evaluation beyond accuracy
- Confusion matrix interpretation
- Precision vs Recall trade-off

## Business Insight
Model selection should prioritize Recall when fraud loss impact is high, even if Precision slightly decreases.
