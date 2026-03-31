# 🌸 Iris — Permutation Test Classification

> An individual data analysis project exploring whether Multinomial Logistic Regression genuinely captures meaningful patterns in the Iris dataset, validated through Permutation Testing.
> Conducted as part of coursework (DSA3361) at the National University of Singapore (NUS).

---

## 📌 Project Overview

The central question addressed in this project is:

> **Does Logistic Regression genuinely capture meaningful relationships in the Iris dataset, or could similar classification accuracy arise due to random chance?**

Using the framework proposed by Ojala and Garriga (2009), permutation testing is conducted by permuting species labels to test whether flower measurements and species labels are independent.

---

## 🔍 Methodology

### 1. Exploratory Data Analysis (EDA)
- Summarised all 4 features (sepal length, sepal width, petal length, petal width) across 3 species (*setosa*, *versicolor*, *virginica*)
- Generated box plots and scatter plots to evaluate feature separability across species
- **Key finding:** Petal measurements provide the strongest distinction between species

### 2. Multinomial Logistic Regression
- Fitted a Multinomial Logistic Regression model using all 4 features, with *setosa* as the reference class
- Evaluated performance using a confusion matrix
- **Baseline accuracy: 98.67%**

### 3. Permutation Testing
- **Null Hypothesis (H0):** Features and species labels are independent
- **Alternative Hypothesis (H1):** Features and labels are dependent
- Shuffled species labels 10,000 times and re-fitted the model each time
- Computed p-value based on how many permuted models matched or exceeded baseline accuracy

---

## 📊 Results

| Metric | Value |
|--------|-------|
| Baseline Accuracy | 98.67% |
| Mean Permuted Accuracy | 41.2% |
| p-value | 0.00009999 |
| Conclusion | Reject H0 at 95% confidence level |

The extremely small p-value provides overwhelming evidence that the classifier has learned genuine patterns rather than random noise — flower measurements contain meaningful information about species identity.

---

## 📈 Visualisations

### EDA — Box Plots
Distribution of all four features across species.

### EDA — Scatter Plots
Petal and sepal dimensions plotted against species.

### Permutation Test — Histogram
Distribution of classification accuracies under the null hypothesis, with baseline accuracy marked.

---

## 🧰 Tools & Libraries

- **Language:** R
- **Libraries:** `ggplot2`, `gridExtra`, `nnet`, `caret`, `knitr`

---

## 📁 Files

| File | Description |
|------|-------------|
| `Iris.Rmd` | Full R Markdown source with all code and analysis |
| `Iris.pdf` | Rendered report with visualisations and writeup |
| `packages.R` | Script to install all required R packages |

---

## 📚 References

Ojala, M., & Garriga, G. C. (2009). Permutation Tests for Studying Classifier Performance. *2009 Ninth IEEE International Conference on Data Mining*, 908–913.
