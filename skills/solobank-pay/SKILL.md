---
name: solobank-pay
description: >-
  Pay for an MPP-protected API endpoint using SOL or USDC on Solana. Use when
  asked to call a paid API, access a gated service, pay for an LLM call,
  or use any service behind the Solobank payment gateway. Do NOT use for
  person-to-person transfers — use solobank-send instead.
license: MIT
metadata:
  author: solobank
  version: "1.0"
  requires: Solobank CLI (npx @solobank/cli init)
---

# Solobank: Pay for API

## Purpose
Call an MPP-protected API endpoint. The agent automatically handles
the 402 Payment Required challenge, pays on-chain, and returns the
API response.

## Command
```bash
solobank pay <url> --method POST --data '<json>' --max-price <usd>

# Examples:
solobank pay https://gateway.solobank.app/openai/v1/chat/completions \
  --method POST \
  --data '{"model":"gpt-4","messages":[{"role":"user","content":"hello"}]}' \
  --max-price 0.05
```

## Flow (automatic)
1. POST to endpoint -> receives 402 + payment challenge
2. Builds and signs SOL/USDC transfer to gateway recipient
3. Sends transaction on-chain, waits for confirmation
4. Retries request with `x-payment-signature` header
5. Returns upstream API response

## Output
```
Paid $0.01 -> gateway (OpenAI)
  Response: {"choices":[{"message":{"content":"Hello! ..."}}]}
  Signature: 4BFGYc6o3kUMswsn...
```

## Notes
- `--max-price` protects against overpaying (default: maxAmountPerTx)
- Devnet uses SOL, mainnet uses USDC
- 40+ API services available: OpenAI, Anthropic, Gemini, Brave, etc.
- Use `solobank balance` to ensure sufficient funds before calling
