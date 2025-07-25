# 🛡️ Wallet Risk Scoring from On-Chain Transactions

This project assigns **risk scores (0–1000)** to a set of Ethereum wallet addresses based on their historical transactions with the **Compound V2/V3 DeFi protocol**. It includes data fetching, feature engineering, scoring logic, and final output as a CSV.

---

## 📌 Problem Statement

Given 100+ wallet addresses, the objective is to:

1. Fetch on-chain transaction history from a lending protocol (Compound V2/V3).
2. Extract meaningful features related to risk (borrows, repayments, liquidations, etc.).
3. Build a scoring mechanism to assign a **wallet risk score between 0 and 1000**.
4. Submit the result as a CSV file and explain the approach.

---

## 📁 Folder Contents

| File Name | Description |
|-----------|-------------|
| `wallet_id.xlsx` | Input file containing list of wallet addresses |
| `wallet_score.ipynb` | Jupyter notebook with code for data collection, feature engineering, and scoring |
| `wallet_risk_score.csv` | Output file containing wallet IDs and their respective risk scores |
| `analysis.md` | Documentation explaining data source, feature selection, and scoring methodology |
| `README.md` | This file |

---

## 🛠️ Technologies Used

- **Python**
- **Pandas & NumPy** – Data manipulation and analysis
- **Requests** – Fetching API data from [Covalent API](https://www.covalenthq.com/docs/api/)
- **tqdm** – Progress bar while looping through wallet addresses
- **Jupyter Notebook** – Code execution and visualization

---

## 🔍 Risk Scoring Methodology

We extracted features from Compound protocol-related transactions like:

- Number of **borrow** events
- Number of **repayments**
- Number of **liquidations**
- Length of activity (days between first and last tx)

Based on these, we applied a **rule-based scoring** logic where:

- More borrows = higher risk  
- More repayments = reduces risk  
- Liquidation events = very high risk  
- Wallets with zero DeFi activity get a low score  

All scores were scaled and capped between **0 and 1000**.

---

## 📈 Sample Output

| wallet_id | score |
|-----------|-------|
| 0x0039f22efb07a647557c7c5d17854cfd6d489ef3 | 100 |
| 0x06b51c6882b27cb05e712185531c1f74996dd988 | 0 |
| ...       | ...   |

---

## 🤝 Author

**Poornima KC**  

