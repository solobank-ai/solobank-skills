---
name: solobank-mcp
description: >-
  Install and manage the Solobank MCP server for AI agent integration. Use when
  asked to install MCP, connect to Claude Desktop, set up Cursor integration,
  check MCP status, or configure agent tools.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: MCP Server

## Purpose
Install the Solobank MCP server into Claude Desktop, Cursor, or other
AI platforms that support the Model Context Protocol.

## Commands
```bash
solobank mcp install      # auto-configure Claude Desktop + Cursor
solobank mcp uninstall    # remove from all platforms
solobank mcp status       # check which platforms are configured
solobank mcp config       # print JSON snippet for manual setup
```

## Output (install)
```
Installed in Claude Desktop (~/.config/Claude/claude_desktop_config.json)
Installed in Cursor (~/.cursor/mcp.json)
```

## Available MCP Tools (15)
| Tool | Type | Description |
|------|------|-------------|
| solobank_address | read | Wallet address |
| solobank_balance | read | Token balances |
| solobank_swap_quote | read | Jupiter swap quote |
| solobank_lending_rates | read | Kamino/Marginfi APYs |
| solobank_send | write | Send SOL/USDC |
| solobank_pay | write | Pay MPP API endpoint |
| solobank_swap | write | Execute token swap |
| solobank_lend | write | Supply to lending |
| solobank_borrow | write | Borrow against collateral |
| solobank_withdraw | write | Withdraw from lending |
| solobank_repay | write | Repay loan |
| solobank_rebalance | write | Move between protocols |
| solobank_config | admin | View/set safeguards |
| solobank_lock | admin | Emergency freeze |

## Notes
- All write tools are gated by safeguards (per-tx limit, daily limit, lock)
- Lock can be triggered via MCP but only unlocked via CLI
- MCP server runs via `npx @solobank/mcp`
