## Project Overview 
This project analyzes the performance of four button variations on the Eniac website using Chi-Square hypothesis testing in Python.

The goal was to determine whether different button designs lead to statistically significant differences in user behavior, primarily focusing on click-through rates (CTR), while also considering user engagement metrics.

### Objective

Identify whether any button variant significantly outperforms others in terms of CTR
Use statistical testing to validate results
Support decision-making with additional behavioral metrics
Variants Tested A - White “SHOP NOW” B - Red “SHOP NOW” C - White “SEE DEALS” D - Red “SEE DEALS”


## 🔘 Tested CTA Variants (2×2 Factorial Design)

The experiment followed a $2 \times 2$ factorial structure across 4 variants over a 14-day test period:

### Visual Button Preview
* **Variant A:** ![Variant A](https://img.shields.io/badge/SHOP_NOW-FFFFFF?style=for-the-badge&logoColor=000000&color=E0E0E0) *(White button, dark copy)*
* **Variant B:** ![Variant B](https://img.shields.io/badge/SHOP_NOW-D32F2F?style=for-the-badge&logoColor=FFFFFF) *(Red button, white copy)*
* **Variant C:** ![Variant C](https://img.shields.io/badge/SEE_DEALS-FFFFFF?style=for-the-badge&logoColor=000000&color=E0E0E0) *(White button, dark copy)*
* **Variant D:** ![Variant D](https://img.shields.io/badge/SEE_DEALS-D32F2F?style=for-the-badge&logoColor=FFFFFF) *(Red button, white copy)*

---

### Variant Specifications & Design Rationale

| Variant | Button Copy (Text) | Button Color | Target URL | Strategic Hypothesis |
| :---: | :---: | :---: | :---: | :--- |
| **A** | `SHOP NOW` | White | `/index-a.php` | Direct transactional intent paired with clean, low-contrast visual design. |
| **B** | `SHOP NOW` | Red | `/index-b.php` | Direct transactional intent paired with high-contrast, urgency-driven color. |
| **C** | `SEE DEALS` | White | `/index-c.php` | Value/incentive-oriented copy targeting bargain-seeking users with clean aesthetics. |
| **D** | `SEE DEALS` | Red | `/index-d.php` | Value-oriented promotional copy combined with high-urgency red styling. |

---

## 📈 Summary of Experiment Traffic & CTR

| Variant | Total Visits ($N$) | Button Clicks | No-Clicks | CTR (%) | Rank |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **Version C** | 24,876 | 527 | 24,349 | **2.12%** |  1st |
| **Version A** | 25,326 | 512 | 24,814 | **2.02%** |  2nd |
| **Version B** | 24,747 | 281 | 24,466 | **1.14%** |  3rd |
| **Version D** | 25,233 | 193 | 25,040 | **0.76%** |  4th |

---

## 🔬 Statistical Analysis & Testing

### 1. Overall Omnibus Chi-Square Test
To determine whether click-through rates across variants showed genuine behavioral variance:

* **Null Hypothesis ($H_0$):** All button variants share an identical CTR ($\text{CTR}_A = \text{CTR}_B = \text{CTR}_C = \text{CTR}_D$).
* **Alternative Hypothesis ($H_1$):** At least one button variant produces a significantly different CTR.
* **Significance Level ($\alpha$):** $0.05$

```text
Chi-Square Statistic: 224.0188
Degrees of Freedom (df): 3
p-value: 2.65e-48 (p < 0.0001)
Outcome: Reject H0 (Statistically Significant)
```

## Methodology

Conducted Chi-Square Test of Independence
Performed post-hoc analysis with Bonferroni correction
Analysis implemented in Python
## Key Insights

A and C perform similarly in CTR (not statistically different)
C attracts more clicks but loses users quickly
A provides better overall user engagement
D significantly underperforms across key metrics
## Conclusion

No single statistically dominant winner was identified
Versions A and C belong to the top performance tier
Version A is more balanced, while C is more attention-grabbing but less effective post-click
Next Steps

To identify a definitive winner, further actions are recommended:

Consider additional metrics beyond CTR
Incorporate qualitative user research
Consult subject-matter experts
Redesign and rerun the experiment

## Tools & Technologies

Python
NumPy
SciPy (chi2_contingency)
Statistical Hypothesis Testing
