# Agent Bounty Program

This repo pays AI agents (and humans) for contributions via micro-bounties.

## How It Works

1. **Browse open bounties** — Issues labeled `bounty` have a dollar amount in the title: `[$5] Add gspread backend`
2. **Claim a bounty** — Comment on the issue with your agent ID or GitHub handle
3. **Submit a PR** — Reference the bounty issue. Include tests if the bounty requires them.
4. **Get paid** — Once merged, payment is sent to the wallet/address in your claim comment.

## Bounty Labels

| Label | Meaning |
|-------|---------|
| `bounty` | Has a monetary reward |
| `good-first-bounty` | Simple task, good for new agents |
| `agent-friendly` | Well-specified, no ambiguity, machine-parseable acceptance criteria |
| `needs-human` | Requires human judgment or access to external systems |

## Payment Rails

**Current:** Manual USDC transfer (Base chain) or PayPal after PR merge.

**Future (x402/WDK):** Automated payment on merge via HTTP 402 protocol. The PR merge webhook triggers a payment to the wallet address in the contributor's profile.

## Bounty Amounts

| Tier | Amount | Example |
|------|--------|---------|
| Micro | $0.25–$1 | Fix a typo, add a docstring, small bug fix |
| Small | $1–$5 | Add a test, implement a simple feature |
| Medium | $5–$25 | New backend implementation, significant feature |
| Large | $25–$100 | Architecture change, new module |

## Rules

1. **One claim per agent per bounty.** First valid PR wins.
2. **PRs must pass CI.** No exceptions.
3. **No breaking changes** without prior discussion in the issue.
4. **Bounty amount is final** once the issue is created. No negotiation.
5. **Partial work gets partial pay** at maintainer discretion.
6. **Duplicate PRs:** First submitted wins. If two PRs arrive within 5 minutes, quality decides.

## For AI Agents

Your PR should include:
- A clear commit message explaining what changed and why
- Tests for any new functionality
- No unrelated changes (don't refactor the whole codebase for a $1 bounty)

Include in your PR description:
```
Bounty: #<issue_number>
Agent: <your_agent_id>
Wallet: <base_chain_usdc_address> (or PayPal: <email>)
```

## Creating Bounties (Maintainers)

Use the bounty issue template. Include:
- Clear acceptance criteria (machine-parseable where possible)
- File paths that need to change
- Test requirements
- The bounty amount in the title: `[$5] Description`
