---
name: solobank-borrow
description: >-
  Borrow assets against supplied collateral from a lending protocol. Use when
  asked to borrow USDC, take out a loan, get credit, or leverage deposits.
  Requires existing supply position as collateral.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Borrow

## Purpose
Borrow USDC or SOL against collateral already supplied to Kamino or Marginfi.

## Command
```bash
solobank borrow <amount> <asset>
solobank borrow <amount> <asset> --protocol kamino

# Examples:
solobank borrow 40 USDC
solobank borrow 0.1 SOL --protocol marginfi
```

## Pre-flight checks
1. Sufficient collateral supplied to the protocol
2. Health factor remains above liquidation threshold after borrow
3. Amount within safeguard limits

## Output
```
Borrowed 40 USDC from Kamino (main market)
  Borrow APR: 12.5%
  Health factor: 2.15
  Signature: csaQC2HN69e3pei6...
```

## Notes
- Must supply collateral first (`solobank lend`)
- Monitor health factor — if it drops below 1.0, position may be liquidated
- Repay with `solobank repay`
- Interest accrues continuously
