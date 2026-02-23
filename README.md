# Credit_Risk-Assessment_-_Statistical-Inference
An end-to-end Data Science project applying Inferential Statistics (Bayes, T-Tests, Chi-Square) on 1.6M+ banking records to optimise credit risk assessment and uncover operational bottlenecks.

Credit Risk Assessment & Statistical Inference 🏦
📌 Project Overview
This project is an end-to-end Data Science and Statistical Analysis pipeline designed to evaluate credit risk and uncover hidden operational bottlenecks within a bank's loan application process.

By transitioning from basic averages and guesswork to mathematically proven inferential statistics (Bayes' Theorem, Welch's T-Test, and Chi-Square Tests), this project demonstrates how deep statistical probability can optimize a bank's underwriting strategy, redefine risk profiles, and drastically improve channel-specific operations.

🗄️ Dataset
Source: Kaggle (Home Credit Default Risk / Previous Applications)

Description: A massive, real-world banking dataset containing over 1.6 million rows of historical loan applications. It includes continuous financial metrics (loan amounts requested) and categorical data (client types, application channels, and final contract statuses).

🛠️ Tech Stack & Libraries
Language: Python

Data Manipulation: pandas, numpy

Statistical Modeling & Probability: scipy (stats.ttest_ind, stats.chi2_contingency)

Visualisation: matplotlib, seaborn

🚀 Methodology & Pipeline
1. Data Triage & Setup
Ingested and optimised a 1.6M+ row dataset to run heavy statistical calculations efficiently.

Isolated crucial variables for testing: AMT_CREDIT, NAME_CONTRACT_STATUS, NAME_CLIENT_TYPE, and CHANNEL_TYPE.

Cleaned the subset by handling missing values in critical continuous columns to prevent skewed mathematical means.

2. Bayesian Probability (Risk Management)
The Goal: Calculate the exact probability of a loan being refused based on specific customer evidence.

The Math: Applied Bayes' Theorem manually to update the bank's risk beliefs.

The Result: The baseline probability (Prior) of any loan being refused was 17.40%. However, given the evidence that a client is "New", the risk (Posterior) plummeted to just 4.79%. Proved mathematically that "New" clients are drastically underrepresented in the rejection pile (only 4.96% likelihood).

<img width="1300" height="550" alt="Bayesian" src="https://github.com/user-attachments/assets/c2084731-8366-4d06-87e3-456451690291" alt="Bayesian Probability Update"/>

3. Inferential Statistics (A/B Testing with T-Tests)
The Hypothesis: Do "Repeater" clients ask for statistically significantly higher loan amounts than "New" clients, or is the difference random noise?

The Math: Conducted a Welch's Independent T-Test to destroy the Null Hypothesis.

The Result: Generated a massive T-Statistic of -268.5 and a P-Value of 0.0. This definitely proved that the difference is not random. Repeaters ask for an average of 218,560 AZN compared to New clients' 106,273 AZN. Visualised the "Fat Right Tail" of Repeater clients using KDE distribution plots.

<img width="1300" height="600" alt="T-Test" src="https://github.com/user-attachments/assets/2b14ca56-7bca-41f8-ac5c-b8ccf336d6f1" alt="T-Test Results and KDE Plot"/>

4. Categorical Dependency (Chi-Square Test)
The Hypothesis: Does the physical or digital location where a customer applies (CHANNEL_TYPE) mathematically dictate their risk of rejection (NAME_CONTRACT_STATUS)?

The Math: Built a contingency table and ran a Chi-Square Test of Independence to compare Observed reality vs. Expected probability.

The Result: The test returned a staggering Chi-Square Statistic of ~550,551 (P-Value: 0.0). The application channel completely alters the outcome. Created a normalised Seaborn Heatmap to pinpoint the exact toxic pipelines.

<img width="1135" height="783" alt="5" src="https://github.com/user-attachments/assets/66ce90b8-f1b7-45e4-95de-8937c4d751f1" alt="Chi-Square Heatmap"/>

💡 Key Business Takeaways
"New" is Safer: Counter-intuitively, new clients present significantly lower underwriting risk than the general population. The bank can afford to be more aggressive in approving entry-level loans for new user acquisition.

The "Fat Tail" of Repeaters: While the majority of all clients ask for small loans, the "Repeater" category contains a highly lucrative sub-population seeking massive loans (400k - 1M+). Dedicated VIP pipelines should be created for this demographic.

Operational Bottlenecks Exposed: The Chi-Square heatmap revealed that "Corporate Sales" has a toxic 54.7% rejection rate, wasting immense underwriting resources. Furthermore, "Contact Centres" and "Credit/Cash Offices" suffer from massive cancellation rates (~40%). The bank must audit the UX and processes of these specific channels immediately.

💻 How to Run This Project
Clone this repository.

Download the dataset from Kaggle: <a src='https://www.kaggle.com/datasets/mishra5001/credit-card?select=previous_application.csv' />

Ensure you have the required libraries installed (pip install pandas numpy scipy matplotlib seaborn).

Run the Jupyter Notebook credit_risk_detection.ipynb sequentially to view the raw mathematical proofs, statistical outputs, and visualisations.
