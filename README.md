# 💼 DeFi Wallet Risk Scoring — Compound V2

A risk scoring system for Ethereum wallets interacting with the **Compound V2** DeFi protocol. Assigns each wallet a score from 0 to 1000 based on on-chain transaction behavior — distinguishing reliable users from risky or bot-like activity.

---

## What It Does

- Analyzes on-chain transaction history for 100 Ethereum wallets on Compound V2
- Engineers behavioral features from supply, borrow, repay, and liquidation events
- Applies a weighted scoring formula to produce a 0–1000 risk score per wallet
- Higher scores = reliable, low-risk users; Lower scores = risky or exploitative behavior
- Outputs scored results to CSV for downstream use

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python |
| Data Source | Compound V2 Protocol (via Covalent / Etherscan / DeFiLlama APIs) |
| Environment | Google Colab |
| Output | CSV |

---

## Feature Engineering

| Feature | Description |
|---|---|
| `total_borrowed` | Total amount borrowed by the wallet |
| `total_repaid` | Total repaid amount |
| `borrow_count` | Number of borrow actions |
| `repay_count` | Number of repay actions |
| `liquidation_count` | Times the wallet was liquidated |
| `supply_frequency` | Number of supply actions |
| `asset_diversity` | Number of unique assets interacted with |
| `repayment_ratio` | total_repaid / total_borrowed |

---

## Scoring Formula

```python
score = (
    (repayment_ratio * 300)
    + (supply_frequency * 10)
    + (asset_diversity * 20)
    - (liquidation_count * 100)
)
score = min(max(score, 0), 1000)
```

---

## Project Files

```
Wallet-Scores/
├── wallet_scores.csv          # Final scored output for 100 wallets
├── Wallet id - Sheet1.csv     # Input wallet addresses
├── analysis.md                # Methodology and scoring explanation
└── README.md
```

---

## Run in Colab

[Open in Google Colab](https://colab.research.google.com/drive/15XXu9IETP3ajVE-TJJt2GtEZ_gVePyZh?usp=drive_link)

---

## Skills Demonstrated

`Python` `DeFi / Web3` `Feature Engineering` `Data Analysis` `Compound V2` `On-chain Data` `Risk Scoring` `CSV Processing`

---

**Author:** Siddhi Mudgal · [LinkedIn](https://linkedin.com/in/https://www.linkedin.com/in/siddhi-mudgal/) · [GitHub](https://github.com/Siddhimudgal1417)
