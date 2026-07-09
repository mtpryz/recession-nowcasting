# Can Machine Learning Models Nowcast U.S. Recessions?

**Academic Context:** This repository contains the code and findings for a research project completed for FIN*4000: Advanced Topics in Finance at the University of Guelph. The project received a final grade of 99%.

## Objective
The National Bureau of Economic Research (NBER) officially dates U.S. business cycle turning points with a significant time lag, which complicates risk management for investors and policymakers. This project investigates whether machine learning algorithms can accurately nowcast U.S. recessions by analyzing contemporary macroeconomic indicators, aiming to match or surpass traditional econometric benchmarks. 

## Data Source
The analysis uses "first-release" (unrevised) quarterly data from 1967 to 2025 to replicate the information available to an analyst at a given time. Data was retrieved using the FRED API and includes eight key economic series:
* Real Gross Domestic Product (GDP)
* Real Gross Domestic Income (GDI)
* Employment Level
* Industrial Production Index
* Nonfarm Payrolls
* Personal Income Less Transfers
* Real Personal Consumption Expenditures
* Manufacturing and Trade Sales

## Methodology
The project tests 16 different algorithms to determine which best suits the research question. To address the scarcity of recessions versus expansions, class balancing was implemented across the models. 

The architectures tested include:
1. **Traditional Benchmark:** A Chauvet-Piger (2008) replication using Principal Component Analysis (PCA) and a Markov Switching model.
2. **Penalized Logistic Regression:** Standard, Ridge, Lasso, and Elastic Net.
3. **Ensemble Tree Methods:** Decision Tree, Random Forest, Gradient Boosting, and XGBoost.
4. **Support Vector Machines (SVM):** Linear and RBF kernels.
5. **Neural Networks:** Vanilla NN, Recurrent Neural Network (RNN), Long Short-Term Memory (LSTM), and Gated Recurrent Unit (GRU).

## Key Findings
Neural networks outperformed traditional benchmarks and regression models in capturing the non-linearities of the research problem. 

* **Top Performing Model:** The Gated Recurrent Unit (GRU) model achieved the highest performance with an F1 score of 0.89.
* **Impact:** The GRU demonstrated strong nowcasting ability with high precision and recall, successfully predicting recessions without generating frequent false positives or missing recessionary periods.

<img width="975" height="557" alt="image" src="https://github.com/user-attachments/assets/3fda067b-985a-4a33-8b72-ae875136e7d5" />
