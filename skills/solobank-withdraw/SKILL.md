---
name: solobank-withdraw
description: >-
  Withdraw supplied assets from a lending protocol. Use when asked to withdraw
  from savings, access deposits, pull out funds, or stop earning yield.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Withdraw from Savings

## Purpose
Withdraw previously supplied assets from Kamino or Marginfi back
to the agent's available balance.

## Command
```bash
solobank withdraw <amount> <asset>
solobank withdraw <amount> <asset> --protocol kamino
solobank withdraw <amount> <asset> --all   # withdraw everything

# Examples:
solobank withdraw 50 USDC
solobank withdraw 50 USDC --protocol marginfi
solobank withdraw 0 USDC --all
```

## Output
```
Withdrew 50 USDC from Kamino (main market)
  Signature: 2vikaMaehqtCHqRz...
  Available balance: 550 USDC
```

## Notes
- Cannot withdraw more than supplied amount
- Withdrawing collateral may affect health factor if there's an active loan
- Check health factor with `solobank balance` before large withdrawals
