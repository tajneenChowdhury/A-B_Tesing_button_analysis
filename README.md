# A-B_Tesing_button_analysis
Project Overview This project analyzes the performance of four button variations on the Eniac website using Chi-Square hypothesis testing and Post-Hoc Pairwise Tests in Python.

The goal was to determine whether different button designs lead to statistically significant differences in user behavior, primarily focusing on click-through rates (CTR), while also considering user engagement metrics.

## Objective

Identify whether any button variant significantly outperforms others in terms of CTR
Use statistical testing to validate results
Support decision-making with additional behavioral metrics
Variants Tested A - White “SHOP NOW” B - Red “SHOP NOW” C - White “SEE DEALS” D - Red “SEE DEALS”

## Metrics Used

Click-Through Rate (Primary Metric)
CTR = Total Clicks / Total Visits
Measures how effectively the button drives user interaction
Used for statistical significance testing
Drop-Off Rate (Secondary Metric)
Percentage of users who start but do not complete a conversion
Indicates how well users stay engaged after clicking
Lower is better
Homepage Return Rate (HRR)
Measures how often users return to the homepage after clicking
Indicates whether users find relevant content after clicking
Lower is better

### Tested CTA Variants

| Variant | Button Text (Copy) | Color Scheme | Target Page | Purpose / Hypothesis |
|:-------:|:------------------:|:------------:|:-----------:|:---------------------|
| **A** | `SHOP NOW` | White button | Category Page | Direct transactional prompt (Neutral color) |
| **B** | `SHOP NOW` | Red button | Category Page | High-urgency transactional prompt (Vibrant color) |
| **C** | `SEE DEALS` | White button | Deals / Promo Page | Value/discount-oriented copy (Neutral color) |
| **D** | `SEE DEALS` | Red button | Deals / Promo Page | High-urgency discount prompt (Vibrant color) |

## Evaluation Metrics

Click-Through Rate (CTR): Measures initial user interaction and interest:
$$\text{CTR} = \frac{\text{Total Clicks on Button}}{\text{Total Homepage Visits}}$$

