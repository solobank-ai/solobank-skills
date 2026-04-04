---
name: solobank-repay
description: >-
  Repay borrowed assets to a lending protocol. Use when asked to repay a loan,
  pay back debt, reduce borrow position, or clear outstanding balance.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Repay Loan

## Purpose
Repay previously borrowed assets to Kamino or Marginfi to reduce
debt and improve health factor.

## Command
```bash
solobank repay <amount> <asset>
solobank repay <amount> <asset> --protocol kamino
solobank repay <amount> <asset> --all   # repay full debt

# Examples:
solobank repay 20 USDC
solobank repay 0 USDC --all
```

## Output
```
Repaid 20 USDC to Kamino (main market)
  Remaining debt: 20 USDC
  Health factor: 4.30
  Signature: eaceRMotCWs3Lvm6...
```

## Notes
- Repaying improves health factor
- Use `--all` to clear the entire debt position
- Must have sufficient available balance to repay
