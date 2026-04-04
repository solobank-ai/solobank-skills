---
name: solobank-save
description: >-
  Supply assets to a lending protocol to earn yield. Use when asked to save
  money, earn interest, deposit to savings, earn yield, lend USDC, or put
  funds to work. Supports Kamino and Marginfi protocols on Solana.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Save (Lend/Supply)

## Purpose
Supply USDC or SOL to a DeFi lending protocol (Kamino or Marginfi)
to earn yield on idle assets.

## Commands
```bash
solobank lend <amount> <asset>                     # auto-selects best protocol
solobank lend <amount> <asset> --protocol kamino   # force Kamino
solobank lend <amount> <asset> --protocol marginfi # force Marginfi
solobank lend-rates <asset>                        # compare rates first

# Examples:
solobank lend 100 USDC
solobank lend 0.5 SOL --protocol kamino
solobank lend-rates USDC
```

## Recommended flow
1. `solobank lend-rates USDC` — compare APYs across protocols
2. `solobank lend 100 USDC` — supply to best rate (auto)

## Output (lend-rates)
```
Protocol    Market          APY      APR
kamino      main            8.21%    7.89%
marginfi    main            7.05%    6.81%
```

## Output (lend)
```
Supplied 100 USDC to Kamino (main market)
  APY: 8.21%
  Signature: 5ScEUtUfzq4SdDti...
  Earning ~$0.022/day
```

## Notes
- `auto` protocol picks the highest APY
- Supplied funds can be withdrawn anytime with `solobank withdraw`
- Supplied funds can serve as collateral for borrowing
