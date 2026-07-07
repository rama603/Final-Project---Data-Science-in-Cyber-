# Final Project-Data Science in Cyber
# Supervised Machine Learning for Phishing URL Detection: A Reproduction & Audit Study
# Studint Name: Rama Kadi
# ID Number: 213821580

# Project Description
This repository contains a rigorous reproduction study and critical software engineering audit of an open-source machine learning pipeline designed to detect phishing URLs using static structural feature parsing.

While the original tutorial claimed that complex ensemble models like XGBoost offered the premier framework for this deployment, our study engineered a strict data hygiene layer that uncovered a massive data-integrity flaw: 9,229 rows contained identical structural feature patterns (data loops).

By stripping these duplicate arrays, the dataset was reduced to 771 unique feature vectors. We evaluated six distinct classification architectures under strict non-leakage parameters using a Stratified 5-Fold Cross-Validation harness. This completely flipped the original author's performance hierarchy and exposed major operational vulnerabilities regarding False Positive floods in live enterprise networks.

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
The XGBoost Illusion Dismantled: The original author's conclusion that XGBoost was the superior architecture was an artifact of unmitigated data leakage. Once duplicate feature patterns are stripped, the Support Vector Machine (SVM) emerges as the top-performing global classifier, capturing a 90.53\% CV Accuracy and a dominant 0.7088 CV MCC, far outperforming XGBoost’s 0.6875 MCC.
The Label-Conflict Vulnerability Explored: Our updated data hygiene pipeline introduces an active label-conflict audit. This analysis proves that compressing continuous web properties into brittle binary thresholds causes completely distinct domains to collapse into identical structural feature signatures with conflicting ground-truth targets (0 and 1 mapping simultaneously), introducing high mathematical ambiguity into the feature space.Operational Conclusion: In an enterprise setting, triggering constant false alarms out of small pools of unique, everyday link clicks causes severe administrative denial-of-service and immediate alert fatigue within the Security Operations Center (SOC).


