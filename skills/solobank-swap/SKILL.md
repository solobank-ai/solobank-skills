---
name: solobank-swap
description: >-
  Swap tokens on Solana via Jupiter aggregator. Use when asked to exchange
  tokens, convert SOL to USDC, swap assets, trade tokens, or get a swap
  quote. Jupiter aggregates 20+ Solana DEXs for best pricing.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Swap Tokens

## Purpose
Exchange one token for another via Jupiter, Solana's leading DEX aggregator.

## Commands
```bash
solobank swap-quote <amount> <from> <to>           # preview without executing
solobank swap <amount> <from> <to>                  # execute swap
solobank swap <amount> <from> <to> --slippage-bps 50  # custom slippage (0.5%)

# Examples:
solobank swap-quote 1 SOL USDC
solobank swap 100 USDC SOL
solobank swap 0.5 SOL USDC --slippage-bps 100   # 1% slippage tolerance
```

## Recommended flow
1. `solobank swap-quote 1 SOL USDC` — check price and route
2. `solobank swap 1 SOL USDC` — execute if quote is acceptable

## Output (swap-quote)
```
Quote: 1 SOL -> 125.42 USDC
  Price impact: 0.01%
  Route: SOL -> USDC (Raydium)
  Slippage: 50 bps (0.5%)
```

## Output (swap)
```
Swapped 1 SOL -> 125.42 USDC
  Price impact: 0.01%
  Signature: uj9VaWXry7F3xwB1...
  Explorer: https://solscan.io/tx/uj9Va...
```

## Notes
- Default slippage is 50 bps (0.5%)
- Supports any SPL token by mint address: `solobank swap 100 USDC EPjFWdd5...`
- Known symbols: SOL, USDC, USDT, JUP
