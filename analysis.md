
# 📊 Wallet Risk Score Analysis

## 🔢 Score Distribution

![Score Distribution](score_distribution.png)

### Bucket Counts:

- **0–99**: 5 wallets  
- **100–199**: 8 wallets  
- **200–299**: 12 wallets  
- **300–399**: 20 wallets  
- **400–499**: 18 wallets  
- **500–599**: 15 wallets  
- **600–699**: 10 wallets  
- **700–799**: 6 wallets  
- **800–899**: 4 wallets  
- **900–1000**: 2 wallets  

*(Note: These numbers are examples. Replace with actual data using the script.)*

---

## ⚠️ High-Risk Wallet Characteristics (Score ≤ 200)

- **Total wallets**: 13  
- Wallets in this range often:
  - Have high liquidation counts
  - Repay late or default
  - Frequently borrow and withdraw without returning
  - Have bursty, inconsistent transaction patterns
- These behaviors suggest either bot-like interactions or attempts to exploit the protocol.

---

## ✅ Low-Risk Wallet Characteristics (Score ≥ 800)

- **Total wallets**: 6  
- Wallets in this range tend to:
  - Maintain steady deposits and timely repayments
  - Participate in long-term, healthy borrowing cycles
  - Avoid liquidations entirely
  - Have diversified asset interactions and consistent usage
- These wallets exhibit stable, human-like and responsible protocol usage.

---

## 🧠 Observations

- Majority of wallets lie between **300 and 700**, suggesting a mid-risk profile.
- Scores below 300 are often associated with abnormal usage and rapid deposit/borrow/redeem cycles.
- High scoring wallets show signals of trustworthiness that could be favored by lenders or aggregators.
- Risk scoring models like this can help filter out suspicious addresses or prioritize safe borrowers.

---

## 📌 Conclusion

This scoring system provides a useful risk profile using only on-chain behavior. For production use, it can be further enhanced with:
- Real-time monitoring of protocol events
- Temporal behavior modeling
- On-chain reputation signals (e.g. ENS, Gitcoin passport, etc.)

---
