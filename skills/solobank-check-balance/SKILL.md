---
name: solobank-check-balance
description: >-
  Check the Solobank agent wallet balance on Solana. Use when asked about wallet
  balance, how much SOL or USDC is available, lending positions, or total funds.
  Also use before any send, swap, or lend operation to confirm sufficient funds.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Check Balance

## Purpose
Fetch the current balance of the agent's Solana wallet: SOL, USDC,
and other SPL token holdings.

## Commands
```bash
solobank balance            # human-readable summary
solobank balance --json     # machine-parseable JSON
```

## Output (default)
```
SOL:   1.250000000 ($150.00)
USDC:  500.000000
───────────────────────
Total: ~$650.00
```

## Notes
- SOL balance includes rent-exempt reserve (~0.00089 SOL)
- USDC uses 6 decimals, SOL uses 9 decimals
- If balance shows 0, fund the wallet via transfer or airdrop (devnet: `solana airdrop`)
- Use `solobank address` to get the wallet address for funding
