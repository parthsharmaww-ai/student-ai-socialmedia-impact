# AI & Social Media Impact: Student Health & Grades

How AI & Social Media affecting student's health and their grades?

## Problem Statement

As a data science student, I've observed the rapid rise of AI tools and increasing daily engagement with social media among students, often without a clear understanding of their broader effects. This project investigates whether this growing usage — measured through daily social media hours and AI usage hours — correlates with student outcomes, specifically academic performance, mental and physical health, social isolation, and burnout levels. By analyzing patterns across 15,000 student records, this project aims to surface whether these increasingly normalized habits carry measurable risks worth paying attention to.

## Data

[Kaggle: AI and Social Media Impact on Student Health and Grades](https://www.kaggle.com/datasets/debayank2024/ai-and-social-media-impact-student-health-and-grades?resource=download)

The data contains 15,000 records of students. The record contains 14 columns which gives us the student id, age, gender, education level, daily social media hours, daily AI usage hours, sleep hours, physical activity hours, mental health score, physical health score, social isolation score, burnout level, academic performance score and academic failure risk.

## Methodology

This project uses correlational analysis and hypothesis testing (Pearson/Spearman correlation, t-tests) to examine relationships between variables, rather than building a predictive model. Data inspection revealed no cleaning was required.

## Tools & Technologies

- Python
- Pandas
- Sklearn
- Statsmodels
- Jupyter

## Project Structure
```
student-ai-socialmedia-impact/
├── data/
│   └── AI_SocialMedia_Student_Health_Dataset_clean.csv   # raw dataset from Kaggle
├── notebooks/
│   └── 01_data_inspection_and_cleaning.ipynb             # inspection + cleaning conclusion
├── output/                                               # (empty for now — will hold charts/results)
├── README.md
└── .gitignore
```
## Status

In progress - data cleaned

