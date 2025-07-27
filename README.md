# 💼 Wallet Risk Scoring from On-chain Compound V2 Data

This project builds a risk scoring system for Ethereum wallets interacting with the Compound V2 protocol. Each wallet is assigned a risk score from 0 to 1000 based on historical DeFi activity.

---

## 📌 Objective

To analyze transaction behavior and assign a **risk score (0–1000)** to wallets, where:
- **Higher scores** imply **reliable, low-risk** users
- **Lower scores** imply **risky, bot-like, or exploitative** behavior

---

## 📥 Data Collection

- Source: Compound V2 Protocol
- Wallets: 100 wallet addresses provided in [this Google Sheet](https://docs.google.com/spreadsheets/d/1ZzaeMgNYnxvriYYpe8PE7uMEblTI0GV5GIVUnsP-sBs/edit?usp=sharing)
- Method: Used simulated or publicly available data from APIs like Covalent, Etherscan, or DeFiLlama to fetch:
  - `supply`, `borrow`, `repay`, `liquidation`, and `redeem` events
  - asset amounts and timestamps

---

## 🧠 Feature Engineering

From raw transaction data, we computed the following features:

| Feature | Description |
|--------|-------------|
| `total_borrowed` | Total amount borrowed by the wallet |
| `total_repaid` | Total repaid amount |
| `borrow_count` | Number of borrow actions |
| `repay_count` | Number of repay actions |
| `liquidation_count` | Times the wallet was liquidated |
| `supply_frequency` | Number of supply actions |
| `asset_diversity` | Number of unique assets interacted with |
| `repayment_ratio` | Total repaid / Total borrowed |

---

## ⚖️ Scoring Methodology

We used a weighted scoring formula combining these features:

```python
score = (
    (repayment_ratio * 300)
    + (supply_frequency * 10)
    + (asset_diversity * 20)
    - (liquidation_count * 100)
)

score = min(max(score, 0), 1000)

## Project Link - https://colab.research.google.com/drive/15XXu9IETP3ajVE-TJJt2GtEZ_gVePyZh?usp=drive_link
