# Decision Tree Classification — Airline Customer Satisfaction Prediction

## Project Summary
This project builds an optimized Decision Tree classifier to predict airline passenger satisfaction (satisfied vs dissatisfied) using the Invistico Airline survey dataset (129,880 passengers, 22 features). GridSearchCV tuned `max_depth`, `min_samples_split`, `min_samples_leaf`, and `criterion` across 108 combinations, selecting the model that maximizes F1-score for the "Satisfied" class. Feature importance scores provide airline management with a prioritized service-improvement roadmap.

## How to Run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook decision_tree_airline.ipynb
```

## Best Hyperparameters (GridSearchCV, 5-fold CV, scoring=f1)
| Parameter | Best Value |
|-----------|-----------|
| criterion | gini |
| max_depth | 15 |
| min_samples_split | 10 |
| min_samples_leaf | 1 |
| Best CV F1 | 0.9434 |

## Final Performance (32,470-record test set)

| Metric | Decision Tree | Logistic Regression |
|--------|--------------|---------------------|
| Accuracy | **0.9386** | 0.8287 |
| **F1-Score (Satisfied)** | **0.9432** | 0.8436 |
| Precision | **0.9553** | 0.8433 |
| Recall | **0.9314** | 0.8438 |
| ROC-AUC | **0.9748** | 0.9028 |

## Top 5 Feature Importance Scores
| Rank | Feature | Importance |
|------|---------|-----------|
| 1 | Inflight entertainment | 0.4429 |
| 2 | Seat comfort | 0.1976 |
| 3 | Ease of Online booking | 0.0659 |
| 4 | Departure/Arrival time convenient | 0.0309 |
| 5 | Customer Type | 0.0288 |

**Key insight**: Inflight entertainment drives 44% of the model's decisions — the single highest-leverage investment for satisfaction improvement.

## Files
- `decision_tree_airline.ipynb` — fully executed notebook
- `Invistico_Airline.csv` — source dataset
- `README.md` — this file
