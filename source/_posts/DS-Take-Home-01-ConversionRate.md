---
title: 01 Conversion Rate
date: 2023-12-12
tags: DS Challenge
---

_Since the courses are needed to be purchased to get the dataset, I will study all the projects in this series from JifuZhao who shared the relative ipynb works on github. Reference link for this one: https://github.com/JifuZhao/DS-Take-Home/blob/master/01.%20Conversion%20Rate.ipynb_

Some usual structure for data analysis works:

- 1 State the Issues/Target
- 2 Collect the Data
- 3 Data cleaning and preprocessing
- 4 Do the Exploratory Data Analysis
- 5 Feature Engineering
- 6 Build Model to Solve the Issue
- 7 Model Evaluation
- 8 Explain and Report

## 1.Issue/Goal

Optimizing conversion rate.  
Build a model that predicts conversion rate and, based on the model, come up with ideas to improve revenue.  
This challenge has no dates, no tables to join, no feature engineering required.

## 2.Collect Data

We have data about users who hit our site: whether they converted or not, as well as some of their characteristics.  
The table is "conversion_data". It has information about signed-in users during one session. Each row is a user session.

**Columns:**

- **country**: user country based on the IP address
- **age**: user age. Self-reported at sign-up step
- **new_user**: whether the user created the account during this session or had already an account and simply came back to the site.
- **source**: marketing channel source.
  - **Ads**: came to the site by clicking on advertisement
  - **Seo**: came to the site by clicking on search results
  - **Direct**: came to the site by directly typing the URL on the browser.
- **total_pages_visited**: number of total pages visited during the session. This is a proxy for time spent on site and engagement during the session.
- **converted**: this is our label. 1 - they converted within the session, 0 - they left without buying anything. The company goal is to increase **conversion rate: # conversions / total sessions.**

```Python
head(conversion_data, 1)
```

| Field                | Value |
| -------------------- | ----- |
| country:             | UK    |
| age:                 | 25    |
| new_user:            | 1     |
| source:              | Ads   |
| total_pages_visited: | 1     |
| converted:           | 0     |

## 3.Data cleaning and preprocessing

```Python
data = pd.read_csv("./conversion_data.csv")

// breif view of table
data.head()

// info table
// give info of data numbers and datatype of each var.
data.info()

// get the statistical info of each var.
data.describe()

// get unique "levels" of each var.
for column in data.columns:
  uniques = sorted(data[column].unique*())
  print("{0:20s}{1:5d}\t".format(column, len(uniques)), uniques[:5])

// remove outliers - age
// age is typically < 100
// check
data[data["age"] > 100]

// delete
data = data[data["age"] < 100]
```

## 4.Do the Exploratory Data Analysis
