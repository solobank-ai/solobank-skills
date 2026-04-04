# Solobank Agent Skills

Agent Skills for the Solobank AI bank account on Solana. Install once and your AI agent gains the ability to check balances, send payments, earn yield, borrow, swap tokens, and pay for MPP API services.

## Install

```bash
npx skills add decentrathon/solobank-skills
```

Works with Claude Code, Cursor, VS Code, GitHub Copilot, and any platform supporting the [Agent Skills](https://github.com/anthropics/agent-skills) standard.

### Manual install

**Cursor / VS Code:**
```bash
git clone https://github.com/decentrathon/solobank-skills.git .cursor/skills/solobank-skills
```

**Claude Code / Devin:**
```bash
git clone https://github.com/decentrathon/solobank-skills.git
```

## Prerequisites

```bash
npx @solobank/cli init
```

## Available Skills

| Skill | Triggers |
|-------|----------|
| `solobank-check-balance` | "check balance", "how much SOL do I have" |
| `solobank-send` | "send 10 USDC to...", "transfer SOL" |
| `solobank-save` | "earn yield", "deposit to savings", "lend USDC" |
| `solobank-withdraw` | "withdraw from savings", "access my deposits" |
| `solobank-borrow` | "borrow 40 USDC", "take out a loan" |
| `solobank-repay` | "repay my loan", "pay back debt" |
| `solobank-pay` | "call that paid API", "pay for MPP service" |
| `solobank-swap` | "swap SOL to USDC", "exchange tokens" |
| `solobank-rebalance` | "optimize yield", "move to better APY" |
| `solobank-safeguards` | "set spending limit", "lock agent" |
| `solobank-mcp` | "install MCP server", "connect to Claude" |

## About Solobank

Solobank provides DeFi banking infrastructure for AI agents on Solana:

- **Checking** — send and receive SOL/USDC
- **Savings** — earn yield via Kamino and Marginfi
- **Credit** — borrow against deposits
- **Swap** — exchange tokens via Jupiter (20+ DEXs)
- **Payments** — pay for 40+ APIs via MPP gateway

**Resources:**
- SDK: `npm install @solobank/sdk`
- CLI: `npx @solobank/cli init`
- MCP: `solobank mcp install`
- GitHub: [github.com/decentrathon](https://github.com/decentrathon)

## License

MIT
