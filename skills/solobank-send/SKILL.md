---
name: solobank-send
description: >-
  Send SOL or USDC from the Solobank agent wallet to another address on Solana.
  Use when asked to pay someone, transfer funds, send money, or make a payment
  to a specific Solana address. Do NOT use for API payments — use solobank-pay
  for MPP-protected services.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Send Tokens

## Purpose
Transfer SOL or USDC from the agent's wallet to any Solana address.

## Command
```bash
solobank send <amount> <address> --asset <SOL|USDC>

# Examples:
solobank send 10 9xQeWvG816bUx9EPfEZsM5qadwG4m1K4vK6TfGsDz3jS --asset USDC
solobank send 0.5 FooBar111111111111111111111111111111111111 --asset SOL
solobank send 5 FooBar111111111111111111111111111111111111   # defaults to SOL
```

## Pre-flight checks (automatic)
1. Sufficient balance for amount + gas
2. Valid Solana address (base58, 32-44 chars)
3. Amount within safeguard limits (maxAmountPerTx, maxDailySend)

## Output
```
Sent 10 USDC -> 9xQeWvG...Dz3jS
  Signature: 3k1i2eiRwCnc49bh...
  Explorer: https://solscan.io/tx/3k1i2e...
  Balance: 490 USDC remaining
```

## Error handling
- `Insufficient balance`: not enough SOL/USDC
- `Invalid address`: not a valid Solana address
- `Exceeds per-transaction limit`: amount > maxAmountPerTx safeguard
- `Wallet is locked`: emergency lock is active
