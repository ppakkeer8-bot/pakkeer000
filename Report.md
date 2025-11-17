Executive Summary (SHAP Global Insights)
This project investigates credit default risk using an ensemble model (XGBoost), with a focus on interpretability through SHAP and LIME. After training and validating the model, SHAP summary plots were used to identify the top five globally influential features driving predictions across the dataset.

Top 5 Global Features (SHAP Summary)
Loan-to-Income Ratio This feature consistently showed the highest SHAP values. A high ratio indicates that the loan amount is large relative to the applicant’s income, increasing default risk. SHAP values were strongly positive for high ratios, pushing predictions toward default.
Loan Grade Loan grade, a proxy for creditworthiness, was the second most influential feature. Lower grades (e.g., 5 or 6) had high positive SHAP values, indicating elevated risk. Higher grades contributed negatively, reducing default likelihood.

Person Home Ownership Applicants who rent or have no ownership showed higher SHAP values toward default. Homeowners had negative SHAP values, suggesting greater financial stability.

Person Income Income had a protective effect. Higher income levels were associated with negative SHAP values, reducing the probability of default. However, its impact was nonlinear and interacted with other features like loan amount and grade.
Loan Interest Rate Higher interest rates contributed positively to default predictions. SHAP values revealed that even moderate increases in interest rate significantly shifted the model’s output toward default.

These insights were derived from SHAP summary plots, which visualize both the magnitude and direction of feature influence across thousands of predictions. The model’s behavior aligns with financial intuition, reinforcing trust in its decisions.

Local Explanation Comparison: SHAP vs LIME
To assess individual predictions, three loan applications were selected: one low-risk, one high-risk, and one borderline. Each case was explained using both SHAP and LIME to compare interpretability methods.

Case 1: Low-Risk (Predicted No Default, 0.82)
SHAP: Highlighted low loan-to-income ratio, high income, and good loan grade as protective factors.

LIME: Agreed on key features but slightly underweighted income’s influence.

Difference: SHAP provided more nuanced interaction effects; LIME was simpler but aligned.
Case 2: High-Risk (Predicted Default, 0.76)
SHAP: Emphasized high loan-to-income ratio, poor loan grade, and prior default history.

LIME: Focused on loan grade and default history but gave less weight to income and credit history.

Difference: SHAP captured compound risk factors better; LIME offered a clear but less detailed view.

Case 3: Borderline (Predicted No Default, 0.52)
SHAP: Showed balanced push-pull between income, interest rate, and loan grade.

LIME: Overemphasized interest rate and underrepresented income’s stabilizing effect.

Difference: SHAP revealed the model’s uncertainty; LIME gave a binary interpretation.
Summary
SHAP excels in capturing feature interactions and directionality, making it ideal for global and nuanced local explanations. LIME offers fast, intuitive approximations but may oversimplify complex relationships. Together, they provide complementary insights for risk assessment.
