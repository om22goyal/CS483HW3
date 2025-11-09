HW3: Detecting and Mitigating Algorithmic Bias
-----------------------------------------------------

Part 1 – Dataset Exploration (Bias Detection)
-----------------------------------------------------
The Adult Income dataset was loaded and cleaned by removing rows with missing values.
“Sex” was chosen as the sensitive attribute. The analysis showed that males had a much
higher rate of incomes above $50K compared to females (approximately 30% vs. 12%),
indicating a clear imbalance in the data. The correlation between sex and income (~0.21)
suggested moderate bias toward male individuals. This demonstrates that social and
economic inequalities are reflected in the dataset, which could lead to biased model
predictions if not mitigated.

Part 2 – Model Training and Fairness Evaluation
-----------------------------------------------------
A baseline Logistic Regression classifier was trained using one-hot encoded features.
Model performance was measured using accuracy, precision, recall, and F1-score. Fairness
metrics such as Demographic Parity Difference and Equal Opportunity Difference were also
computed. The baseline model achieved strong accuracy but showed fairness disparities,
with males more likely to be predicted as earning over $50K. Visual analysis confirmed
that the model learned existing biases from the data.

Part 3 – Bias Mitigation
-----------------------------------------------------
Two bias mitigation techniques were applied: Reweighing (pre-processing) and Adversarial
Debiasing (in-processing). Reweighing balanced group weights to reduce bias before
training, while Adversarial Debiasing introduced a fairness constraint during model
optimization. Both methods reduced bias substantially, with Adversarial Debiasing
achieving the lowest Demographic Parity and Equal Opportunity differences. A small
reduction in accuracy was observed, but the trade-off was acceptable given the improved
fairness across gender groups.

Part 4 – Reflection (Ethical and Practical Considerations)
-----------------------------------------------------
Among the mitigation methods tested, Adversarial Debiasing provided the best fairness
improvement, reducing both demographic-parity and equal-opportunity differences to near
zero. Reweighing also helped but retained some residual bias. Both techniques caused a
small drop in accuracy, which reflects the common trade-off between model performance
and fairness. In practice, this trade-off is acceptable because a slightly less accurate
but more equitable model promotes ethical decision-making. Domain knowledge is crucial
for setting fairness goals—income prediction involves historical and social inequalities,
so eliminating group bias aligns with real-world fairness objectives. When presenting
these results to non-technical audiences, the focus should be on explaining that bias
mitigation makes predictions fairer across groups while only minimally affecting overall
accuracy.

https://github.com/om22goyal/CS483HW3.git
