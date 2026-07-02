# Final Project-Data Science in Cyber
# Supervised Machine Learning for Phishing URL Detection: A Reproduction & Audit Study
# Studint Name: Rama Kadi
# ID Number: 213821580

# Project Description
This repository contains a rigorous reproduction study and critical software engineering audit of an open-source machine learning pipeline designed to detect phishing URLs using static structural feature parsing. 

While the original tutorial claimed that complex ensemble models like XGBoost offered the premier framework for this deployment, our study engineered a strict data hygiene layer that uncovered a massive data-integrity flaw: 9,120 rows contained identical structural feature patterns (data loops).

By stripping these duplicate arrays, we evaluated six distinct classification architectures under strict non-leakage parameters, completely flipping the original author's performance hierarchy and exposing major operational vulnerabilities regarding False Positive floods in live enterprise networks.

Moving past mechanical accuracy metrics, this project audits the pipeline through a cybersecurity lens, exposing critical vulnerabilities regarding False Positives, data pre-compression, and the operational trade-offs of feature selection choices.

---

# Project References & Sources
* **Original GitHub Repository:** [https://github.com/shreyagopal/Phishing-Website-Detection-by-Machine-Learning-Techniques]
* **Dataset Source:** Standardized `5.urldata.csv` repository file consisting of 5,000 legitimate and 5,000 phishing samples.

---

# Execution Instructions
git clone https://github.com/rama603/Final-Project---Data-Science-in-Cyber-.git

cd Final-Project---Data-Science-in-Cyber-

jupyter notebook phishing_detection.ipynb

run the code

# Prerequisites
Ensure you have Python installed along with the following data science libraries:

pip install pandas numpy scikit-learn

---

# Dependency Installation
Install the exact library ecosystem configurations required to run the notebook without version depreciation warnings:
pip install -r requirements.txt

# Executing the Pipeline
Launch your local notebook server or open the workspace within VS Code:
jupyter notebook notebook/phishing_detection.ipynb

# Detailed Critical Findings & Cybersecurity Implications
The XGBoost Illusion Dismantled: The original author's conclusion that XGBoost was the superior architecture was an artifact of data leakage. Once duplicate feature patterns are stripped, the Support Vector Machine (SVM) emerges as the top-performing model, capturing a 90.40% Accuracy and a 0.4300 MCC.

The False Positive Bottleneck: While the SVM achieves an elite threat catch rate (99.61% Recall, missing only 3 total phishing links), it achieves this by over-learning the malicious signature due to severe post-deduplication class skewing. It generates 81 False Positives out of 875 everyday link clicks.

Operational Conclusion: In an enterprise setting, blocking 81 clean business links causes severe administrative denial-of-service and immediate alert fatigue. Therefore, this architecture is not recommended for production firewalls without applying our engineered Decision Threshold Tuning Optimization (Tuned to 0.3) to re-align the model with an enterprise risk-averse posture. True modernization requires abandoning static rule matrices in favor of character-level Natural Language Processing (NLP) text vectorization.


