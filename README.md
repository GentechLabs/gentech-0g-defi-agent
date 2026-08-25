# 🤖 GenTech AI DeFi Agent — "The Agency of Traders"

**An autonomous AI DeFi agent where every layer is decentralized and agent-native.** Built for the **0G Bridge Buildathon by AKINDO**.

The agent analyzes markets with **0G Compute** (decentralized LLM inference), reads on-chain state via **Goldsky** (pay-per-call JSON-RPC), persists a Merkle-verified trade log to **0G Storage**, and settles decisions through **Kite AI** (agentic-payment L1) on the machine-money loop.

---

## The Stack

| Layer | Tech | Role |
|-------|------|------|
| **AI Compute** | **0G Compute** | Decentralized LLM inference (qwen2.5-omni-7b, TEE-verified) for market analysis |
| **Storage** | **0G Storage** | Persistent agent memory + trade log, Merkle root hash = verifiable integrity |
| **Chain** | **0G Chain** | EVM-compatible L1, agent identity (ERC-7857) |
| **Identity** | **GenTechAgentIdentity.sol** | On-chain agent identity contract (Agentic ID) |
| **RPC** | **Goldsky** (via Circle for Agents) | Pay-per-call multi-chain JSON-RPC, x402 v2, $0.005/call |
| **Settlement** | **Kite AI** | Agentic-payment L1 — Agent Passport identity, stablecoin rails |

## The Loop

```
0G Compute (analyze market)
        │
        ▼
Goldsky RPC (read on-chain state, multi-chain)
        │
        ▼
Kite AI (settle the agent's decision — stablecoin payment)
        │
        ▼
0G Storage (persist trade log, Merkle-verified)
```

---

## Quick Start

```bash
npm install
cp .env.example .env        # fill in PRIVATE_KEY, PROVIDER_ADDRESS
npm run agent               # run the loop
```

**Scripts:**
- `npm run agent` — the full agent loop (0G Compute → Goldsky → Kite dry-run → Storage)
- `npm run analyze` — 0G Compute market analysis
- `npm run deploy` — deploy GenTechAgentIdentity to 0G Chain

**Tooling:**
- `npx tsx src/discover.ts` — discover available 0G Compute providers (read-only, free)

---

## Verified (as of Wave 3, Aug 2026)

- [x] 0G SDK wired (`@0glabs/0g-serving-broker`, `@0glabs/0g-ts-sdk`)
- [x] Goldsky x402 rail — returns proper x402 v2 challenge (USDC, $0.005/call)
- [x] Agent scaffold — 0G Compute analysis + Goldsky RPC read + Kite settlement
- [x] 0G testnet RPC live — chain ID 16602
- [x] 0G Compute provider discovered + TEE-verified — `qwen2.5-omni-7b` @ `compute-network-6.integratenetwork.work`
- [x] `src/discover.ts` runs live — lists TEE-verified chatbot providers
- [ ] Wallet funded + real 0G Compute inference call (in progress)
- [ ] Real 0G Storage upload (root hash) + mainnet deploy
- [ ] Wave 3 submission

---

## Judging alignment (0G Bridge Buildathon criteria)

| Criteria | Weight | How we hit it |
|----------|--------|---------------|
| **Progress & Momentum** | 40% | Real, runnable code — full agent loop ~70%→100% across the wave |
| **0G Integration** | 30% | **Compute + Storage + Chain + Agentic ID** — multi-component depth |
| **Technical Quality** | 20% | Clean TypeScript, ethers v6, `evmVersion: cancun`, TEE-verified provider |
| **Traction & Communication** | 10% | Public repo, demo video, docs, X updates |

---

## Buildathon

Built for **0G Bridge by AKINDO — Wave 3** ($7,500 USDC + $7,500 0G credits, paid in stablecoins).
Progress is paid, no fixed milestones. Demo Day at Token2049 Singapore (Oct 2026).

**License:** MIT
