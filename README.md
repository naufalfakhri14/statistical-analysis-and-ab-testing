# Applied Statistical Analysis

## Probability, Naive Bayes, and A/B Testing

This project is part of my **One Day One Project** series, where I practice solving different data problems by applying concepts that I have learned.

In this project, I focused on statistical analysis and how it can be used to support data-driven decisions. The project contains three different case studies covering probability distributions, Naive Bayes classification, A/B testing, and user retention.

All datasets in this repository are simulated and created for learning and analytical purposes.

---

## Project Overview

The project consists of three case studies:

| Case Study | Main Topic | Method | Main Result |
|---|---|---|---|
| 01 | Bird Type Classification | Probability Distribution + Naive Bayes | 99.61% accuracy |
| 02 | Article Recommendation | A/B Testing + Welch's t-test | Significant difference |
| 03 | User Retention | Sample Size + Two-Proportion z-test | Significant difference |

---

# Case Study 01 — Probability & Naive Bayes

## Problem

The first case study focuses on classifying birds into three different types based on several characteristics.

The dataset is generated using different probability distributions for each bird type. This allows the analysis to demonstrate how probability distributions can be used to represent data before applying a classification method.

## Features

The dataset contains four features:

- `wingspan_cm` — bird wingspan
- `weight_g` — bird weight
- `sing_days` — number of days the bird sings
- `beak_head_ratio` — ratio between beak size and head size

Different distributions are used for the features:

- **Gaussian distribution** for wingspan and weight
- **Binomial distribution** for singing days
- **Uniform distribution** for beak-to-head ratio

## Approach

The analysis follows these steps:

1. Generate simulated data for three bird types.
2. Split the dataset into training and testing data.
3. Estimate the distribution parameters from the training data.
4. Calculate the class probability for each bird type.
5. Calculate the probability of each feature given the class.
6. Apply Naive Bayes to predict the bird type.
7. Evaluate the predictions using accuracy and a confusion matrix.

## Result

The Naive Bayes classifier achieved:

**Test Accuracy: 99.61%**

The confusion matrix also shows that only four observations were incorrectly classified from 1,035 testing observations.

Because the dataset is simulated, the high accuracy is mainly influenced by the different distributions used to generate each class. Therefore, this result should not be considered representative of real-world bird classification performance.

---

# Case Study 02 — A/B Testing: Article Recommendation

## Problem

The second case study evaluates an article recommendation feature on a technology blog.

The goal is to determine whether showing article recommendations at the end of an article can encourage users to read more articles.

Two groups are compared:

- **Origin** — users who do not see the recommendation feature
- **Varian** — users who see the recommendation feature

The main metric is the number of articles read by each user in one session.

## Analysis

The experiment is analyzed using descriptive statistics and hypothesis testing.

The hypotheses are:

- **H0:** There is no difference in the average number of articles read between the two groups.
- **H1:** There is a difference in the average number of articles read between the two groups.

A significance level of **5% (α = 0.05)** is used.

Because the two groups are independent, the comparison is performed using **Welch's t-test**.

## Result

The average number of articles read was:

| Group | Average Articles Read |
|---|---:|
| Origin | 4.72 |
| Varian | 5.38 |

The p-value from the test was:

**4.31 × 10⁻²¹**

Since the p-value is smaller than 0.05, the null hypothesis is rejected.

This means there is a statistically significant difference in the average number of articles read between the two groups.

Based on the simulated experiment, the recommendation feature is associated with higher user engagement.

---

# Case Study 03 — A/B Testing: User Retention

## Problem

The third case study focuses on user retention.

An education technology company is testing a new feature with the goal of increasing retention from around **69% to 72%**.

The experiment compares:

- **Control** — users using the current version
- **Treatment** — users using the new feature

The main metric is the proportion of users who remain active after the defined retention period.

## Experiment Design

Before running the experiment, the required sample size is estimated using:

- Significance level: **0.05**
- Statistical power: **0.80**
- Current retention rate: **69%**
- Expected retention rate: **72%**

The calculation resulted in approximately:

**3,627 users per group**

With an estimated 997 users available per day, the experiment would require approximately:

**8 days**

to reach the required sample size for both groups.

## Hypothesis Testing

The hypotheses are:

- **H0:** There is no difference in retention rate between the Control and Treatment groups.
- **H1:** There is a difference in retention rate between the Control and Treatment groups.

A **two-proportion z-test** is used because the analysis compares retention proportions between two independent groups.

## Result

The simulated experiment produced:

| Group | Retention Rate |
|---|---:|
| Control | 70.11% |
| Treatment | 72.59% |

The test produced:

- **z-statistic:** -2.3373
- **p-value:** 0.0194

Since the p-value is below 0.05, the null hypothesis is rejected.

The Treatment group has a higher retention rate than the Control group, and the difference is statistically significant.

Based on the simulated experiment, the new feature has the potential to improve user retention.

---

# Key Takeaways

Through these three case studies, I practiced several statistical techniques and their application to data problems:

- Working with probability distributions
- Estimating distribution parameters from data
- Applying Naive Bayes classification
- Designing and analyzing A/B tests
- Defining hypotheses and significance levels
- Comparing group means using Welch's t-test
- Comparing proportions using a two-proportion z-test
- Calculating sample size for an experiment
- Interpreting statistical results from a business perspective

The main takeaway from this project is that statistical analysis is not only about calculating probabilities or p-values, but also about using those results to understand a problem and support a decision.

---

# Tools & Libraries

The project was developed using Python and Jupyter Notebook.

Main libraries used:

- Python
- NumPy
- Pandas
- SciPy
- Statsmodels
- Matplotlib
- Seaborn
- Jupyter Notebook

---

# Project Structure

```text
applied-statistical-analysis/
│
├── README.md
├── requirements.txt
│
└── notebooks/
    ├── 01_probability_naive_bayes.ipynb
    ├── 02_ab_testing_recommendation.ipynb
    └── 03_ab_testing_user_retention.ipynb