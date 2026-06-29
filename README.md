# Final Project-Data Science in Cyber
# Supervised Machine Learning for Phishing URL Detection: A Reproduction & Audit Study

# Project Description
This project is a rigorous academic reproduction study and critical security audit of a supervised machine learning pipeline designed to classify URLs as phishing (1) or legitimate (0). Utilizing a dataset of 10,000 balanced observations, we evaluate and compare a non-linear ensemble architecture (Random Forest) against a linear baseline (Logistic Regression). Moving past mechanical accuracy metrics, this project audits the pipeline through a cybersecurity lens, exposing critical vulnerabilities regarding False Negatives, data pre-compression, and the operational trade-offs of feature selection choices.

---

# Project References & Sources
* **Original GitHub Repository:** [https://github.com/shreyagopal/Phishing-Website-Detection-by-Machine-Learning-Techniques]
* **Dataset Source:** Standardized `5.urldata.csv` repository file consisting of 5,000 legitimate and 5,000 phishing samples.

---

# Execution Instructions

# Prerequisites
Ensure you have Python installed along with the following data science libraries:
```bash
pip install pandas numpy scikit-learn
