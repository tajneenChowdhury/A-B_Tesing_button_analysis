# Eniac E-Commerce: Homepage CTA Button A/B/n Test Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Executive Summary

This repository presents an **A/B/n multivariate testing case study** conducted on the homepage call-to-action (CTA) button for the e-commerce retailer **Eniac**. The primary objective was to investigate the interaction between **Button Color** (White vs. Red) and **Button Copy** ("SHOP NOW" vs. "SEE DEALS") to identify the variant that optimizes user interaction, downstream navigation, and conversion likelihood.

The analysis integrates:
* **Click-Through Rate (CTR)** calculations across all variants.
* **Omnibus Chi-Square Test of Independence** ($\alpha = 0.05$).
* **Post-hoc Pairwise Tests** with **Bonferroni Adjustment** ($\alpha_{\text{adjusted}} = 0.00833$).
* **Full-Funnel Metric Evaluation** using **Drop-off Rate** and **Homepage-Return Rate (HRR)**.

---

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
| **Version C** | 24,876 | 527 | 24,349 | **2.12%** | 🥇 1st |
| **Version A** | 25,326 | 512 | 24,814 | **2.02%** | 🥈 2nd |
| **Version B** | 24,747 | 281 | 24,466 | **1.14%** | 🥉 3rd |
| **Version D** | 25,233 | 193 | 25,040 | **0.76%** | 4th |

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

---

### 2. Post-Hoc Pairwise Tests (Bonferroni Correction)
To control family-wise error rate across $\binom{4}{2} = 6$ comparisons, the significance threshold was set to:

$$\alpha_{\text{adjusted}} = \frac{0.05}{6} \approx 0.00833$$

| Comparison | $\chi^2$ Statistic | $p$-value | Significant ($\alpha = 0.00833$)? | Interpretation |
| :---: | :---: | :---: | :---: | :--- |
| **A vs. B** | 62.4936 | $2.67 \times 10^{-15}$ | **Yes** | White button strongly outperforms Red for "SHOP NOW". |
| **A vs. C** | 0.5342 | $0.4648$ | **No** | **No significant difference** between White "SHOP NOW" and White "SEE DEALS". |
| **A vs. D** | 144.2832 | $3.08 \times 10^{-33}$ | **Yes** | White "SHOP NOW" drastically outperforms Red "SEE DEALS". |
| **B vs. C** | 74.2292 | $6.96 \times 10^{-18}$ | **Yes** | White "SEE DEALS" significantly outperforms Red "SHOP NOW". |
| **B vs. D** | 17.8763 | $2.36 \times 10^{-5}$ | **Yes** | "SHOP NOW" copy beats "SEE DEALS" under Red color styling. |
| **C vs. D** | 161.1170 | $6.45 \times 10^{-37}$ | **Yes** | White button strongly outperforms Red for "SEE DEALS". |

---

## 🧭 Downstream Funnel Metrics Analysis

Because Variants **A** and **C** tied statistically on CTR, secondary post-click metrics were evaluated to break the tie:

| Metric | Definition | Version A | Version C | Version D |
| :--- | :--- | :---: | :---: | :---: |
| **Drop-Off Rate** | $\%$ of visitors who reached landing page but bounced before any conversion event. *(Lower is better)* | **62%** 🏆 *(Best)* | **71%** *(Worst)* | 69% |
| **Homepage Return Rate (HRR)** | $\%$ of visitors who immediately clicked back to the homepage. *(Lower is better)* | 5.1% | 4.8% | **2.7%** 🏆 |

*(Note: Variant B data for downstream funnel metrics was missing due to telemetry logging failure during collection).*

---

## 💡 Key Business Insights

1. **Color Primacy:** White buttons consistently drove higher user engagement than Red buttons across all tested copy variants. Red buttons decreased CTR by up to $64\%$.
2. **The "Curiosity vs. Intent" Trap (Version C):** While "SEE DEALS" produced the highest gross clicks ($2.12\%$), it experienced a **$71\%$ drop-off rate**. This suggests users expected heavy discounts or promotional banners that were absent on the arrival page.
3. **Balanced Conversions (Version A):** Version A had an almost identical CTR ($2.02\%$) while yielding the **lowest drop-off rate ($62\%$)**, delivering qualified, purchase-ready traffic.

---

## 🎯 Final Decision & Roadmap

* **Recommended Winner:** **Deploy Version A (White "SHOP NOW")** as default across the homepage.
* **Landing Page Optimization:** If marketing campaigns necessitate using "SEE DEALS", rebuild the landing page experience to prominently display active offers above the fold.
* **Telemetry Remediation:** Audit web analytics tags to prevent missing downstream tracking data as observed with Variant B.

---

## 💻 Repository Structure & Reproduction

```text
├── A_b_testing_button_analysis.ipynb   # Main Jupyter Notebook with data and statistical tests
├── README.md                           # Project case study documentation
└── requirements.txt                    # Python environment requirements
```

### Installation

```bash
git clone https://github.com/<your-username>/eniac-ab-testing-case-study.git
cd eniac-ab-testing-case-study
pip install -r requirements.txt
```

### Requirements

```text
pandas>=1.3.0
numpy>=1.20.0
scipy>=1.7.0
matplotlib>=3.4.0
seaborn>=0.11.0
```