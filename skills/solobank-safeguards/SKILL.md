---
name: solobank-safeguards
description: >-
  Manage spending limits and emergency lock for the Solobank wallet. Use when
  asked to set spending limit, lock the agent, unlock the wallet, check config,
  set daily limit, or manage transaction safeguards.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Safeguards

## Purpose
Configure per-transaction limits, daily send limits, and emergency
lock/unlock to protect the wallet from excessive spending.

## Commands
```bash
solobank config get                          # view all safeguards
solobank config get maxAmountPerTx           # view specific setting
solobank config set maxAmountPerTx 5         # max $5 per transaction
solobank config set maxDailySend 100         # max $100 per rolling 24h
solobank lock                                # emergency freeze all writes
solobank unlock                              # re-enable transactions
```

## Output (config get)
```
{
  "maxAmountPerTx": 5,
  "maxDailySend": 100,
  "locked": false
}
```

## Notes
- Lock can be activated via MCP (`solobank_lock` tool) but can ONLY be
  unlocked via CLI (`solobank unlock`) for security
- Safeguard config is stored at `~/.solobank/config.json`
- Default per-tx limit is 1.0 (conservative)
- Daily limit uses a rolling 24-hour window
- Read-only operations (balance, rates, quotes) work even when locked
