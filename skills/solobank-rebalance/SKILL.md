---
name: solobank-rebalance
description: >-
  Move supply from one lending protocol to another for better yield. Use when
  asked to rebalance, optimize yield, move funds to better APY, or switch
  lending protocol. Compares Kamino and Marginfi rates automatically.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Rebalance

## Purpose
Withdraw supply from one lending protocol and deposit to another
that offers a higher APY. Atomic two-step operation.

## Command
```bash
solobank rebalance <amount> <asset>
solobank rebalance <amount> <asset> --target-protocol kamino
solobank rebalance <amount> <asset> --min-apy-delta 0.5

# Examples:
solobank rebalance 100 USDC
solobank rebalance 100 USDC --target-protocol kamino --min-apy-delta 1.0
```

## Recommended flow
1. `solobank lend-rates USDC` — compare current rates
2. `solobank rebalance 100 USDC` — move to best rate (auto)

## Output
```
Rebalanced 100 USDC: Marginfi (7.05%) -> Kamino (8.21%)
  APY improvement: +1.16%
  Extra earnings: ~$0.003/day
  Signature: LborpWqqCS7aGJES...
```

## Notes
- Will not rebalance if APY delta is below `--min-apy-delta` threshold
- Requires existing supply position in a protocol
- Both withdraw and deposit happen in the same session
