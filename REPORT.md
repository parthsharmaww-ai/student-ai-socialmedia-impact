# AI & Social Media Impact on Student Health & Grades — Final Report

## Problem Statement

As a data science student, I've observed the rapid rise of AI tools and increasing daily engagement with social media among students, often without a clear understanding of their broader effects. This project investigates whether this growing usage — measured through daily social media hours and AI usage hours — correlates with student outcomes, specifically academic performance, mental and physical health, social isolation, and burnout levels. By analyzing patterns across 15,000 student records, this project aims to surface whether these increasingly normalized habits carry measurable risks worth paying attention to.

## Data

[Kaggle: AI and Social Media Impact on Student Health and Grades](https://www.kaggle.com/datasets/debayank2024/ai-and-social-media-impact-student-health-and-grades?resource=download)

The data contains 15,000 records of students across 14 columns: student id, age, gender, education level, daily social media hours, daily AI usage hours, sleep hours, physical activity hours, mental health score, physical health score, social isolation score, burnout level, academic performance score, and academic failure risk.

## Methodology

This project uses correlational analysis and hypothesis testing (Spearman correlation, Kruskal-Wallis, Mann-Whitney U) to examine relationships between variables, rather than building a predictive model. Data inspection revealed no cleaning was required. Normality testing (Shapiro-Wilk, supported by histogram inspection) determined that Spearman correlation was appropriate over Pearson for all continuous-continuous pairs, due to non-normal distributions (spike-at-zero and ceiling-effect patterns) in most variables.

## Hypotheses

### Confirmatory (predicted in advance, with reasoning)

- **H1:** Higher daily social media hours is associated with lower sleep hours.
- **H2:** Higher daily social media hours is associated with worsening mental health score.
- **H3:** Higher daily AI tool usage hours is associated with worsening academic performance score.

### Exploratory (tested without a predicted direction)

All remaining Daily_Social_Media_Hours / Daily_AI_Tool_Usage_Hours pairings against the other outcome variables were tested exploratorily, without a predicted direction. Given the number of tests run, significant results here are treated as suggestive rather than confirmed, due to the increased chance of false positives across multiple comparisons.

## Findings & Conclusions

### Confirmatory Hypotheses — Summary

Across the three confirmatory hypotheses, daily social media hours showed a consistent negative association with student outcomes — higher usage was linked to lower sleep hours, lower mental health scores, and lower academic performance scores. Daily AI tool usage told a more nuanced story: at low levels (under roughly 2–2.5 hours), it was associated with a slight improvement in academic performance, while beyond that threshold, higher usage was associated with declining performance. AI usage showed no strong relationship with sleep hours and only a weak relationship with mental health scores. Taken together, these results suggest social media use is consistently associated with worse student outcomes, while AI tool usage appears more usage-dependent — potentially beneficial in moderation, but associated with worse outcomes when usage climbs higher.

### Notable Exploratory Findings

- Social media hours showed the strongest exploratory correlation with social isolation score (r≈0.42) — the more time spent on social media, the higher the reported isolation.
- Social media hours rose in a clear step-wise pattern across burnout levels: Low≈3.5 hrs → Moderate≈5.5 → High≈6.8 → Severe≈8.2 hrs.
- Students flagged with academic failure risk reported notably higher daily social media hours (≈7.6) than those without (≈4.33).

### Limitations

- **Correlational design:** This project uses correlational analysis, which can show that two variables move together but cannot establish that one causes the other. Alternative explanations remain possible — for example, reverse causation (struggling students may turn to more social media use, rather than social media use causing the struggle) or a third, unmeasured factor influencing both variables at once.

- **Multiple comparisons problem:** Since 13 exploratory hypotheses were tested without any pre-defined predictions, some of the statistically significant findings may have occurred by chance due to the multiple comparisons issue. These results should be considered indicative rather than definitive.

- **Limitations of group-comparison tests:** The Kruskal-Wallis and Mann-Whitney tests used for Burnout_Level and Academic_Failure_Risk comparisons can confirm that a statistically significant difference exists across groups, but cannot identify which specific groups differ or by how much. A follow-up post-hoc test (e.g., Dunn's test) would be needed to answer that.

- **Dataset origin:** The dataset's unusually clean state — zero missing values, zero duplicate rows, and a filename indicating it was pre-cleaned — makes it impossible to verify whether it reflects real student responses, a cleaned version of real data, or entirely synthetic data generated to resemble realistic patterns.

### Practical Implications

Based on these findings, students may benefit from monitoring their daily social media use, given its consistent association with lower sleep hours, lower mental health scores, and lower academic performance scores. Daily AI tool usage appears less consistently linked to negative outcomes — light usage (roughly under 2–2.5 hours a day) was associated with a slight improvement in academic performance, while usage beyond that threshold was associated with a decline. This suggests AI tools are not inherently harmful in moderation, but heavier reliance may carry the same kind of risk associated with excessive social media use.

These implications are drawn from correlational evidence and should be read as patterns worth further attention, not as proven cause-and-effect relationships.

## Tools & Technologies

- Python, Pandas, Scipy, Statsmodels, Seaborn/Matplotlib, Jupyter