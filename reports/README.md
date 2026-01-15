
## Results

### Model Performance Overview

The final model selected for this project was **Logistic Regression**, evaluated against a Random Forest baseline using identical preprocessing, train/test splits, and evaluation metrics.

| Model | ROC-AUC | PR-AUC |
|------|--------|--------|
| Logistic Regression | **0.60** | **0.38** |
| Random Forest | 0.59 | 0.35 |

Logistic Regression outperformed the Random Forest on both ROC-AUC and PR-AUC, indicating stronger overall ranking performance and better concentration of no-show cases. Given its superior performance, interpretability, and stability, Logistic Regression was selected as the final model.

---

### Decision Threshold Optimization

Rather than using the default 0.5 probability threshold, the decision threshold was **explicitly tuned to prioritize recall**, reflecting a real-world objective of identifying as many potential no-shows as possible for reminder outreach.

A threshold of **0.40** was selected to achieve a recall of at least **70%**, balancing coverage of no-shows with an acceptable increase in false positives.

---

### Final Evaluation Metrics (Threshold = 0.40)

At the recall-optimized threshold, the model achieved:

- **Recall (No-show): ~76%**
- **Precision (No-show): ~33%**
- **ROC-AUC: ~0.60**
- **PR-AUC: ~0.38**

These results indicate that the model successfully identifies the majority of missed appointments, while accepting additional false positives, an appropriate tradeoff given the low cost of reminder interventions compared to the operational impact of missed appointments.

---

### Confusion Matrix Interpretation

At the selected threshold, the confusion matrix demonstrates:

- **3,119** true no-shows correctly identified  
- **985** no-shows missed  
- **6,473** appointments flagged that ultimately showed  
- **3,815** correct non-flagged shows  

Approximately **two-thirds of appointments** would be flagged for outreach, resulting in coverage of roughly **three-quarters of all no-shows**. This behavior aligns with the project’s recall-first objective and reflects realistic performance for human behavioral data.

---

### Model Selection Rationale

Although Random Forest models are capable of capturing nonlinear interactions, they did not improve performance in this setting. The results suggest that the dominant predictive signals in the data such as appointment lead time and reminder behavior—are largely linear. Logistic Regression provided stronger generalization while remaining interpretable and operationally stable.

---

### Summary

This project demonstrates that even relatively simple, interpretable models can provide meaningful value when paired with thoughtful feature engineering, leakage aware evaluation, and business aligned decision thresholds. The final model offers a practical and deployable approach to reducing missed medical appointments through targeted intervention.
