# Langclaw AI Sui

Langclaw is a Sui-first AI alpha, data, and strategy workspace with private,
verifiable agent memory. It helps users analyze smart-money activity, liquidity
anomalies, protocol momentum, and holder flows, then records source-backed agent
decisions and strategy proofs on Sui.

Private memories are encrypted with Seal, stored on Walrus, and linked to
metadata-only proofs on Sui. The current product is analysis-first: it does not
custody user assets, sign swaps, or execute live-funds trades.

## Repositories

**Organization:** [Langclaw-AI-SUI-Ecosystem](https://github.com/Langclaw-AI-SUI-Ecosystem)

**Live app:** [langclaw-sui-walrus.vercel.app](https://langclaw-sui-walrus.vercel.app)

| Repository | Stack | Purpose |
| --- | --- | --- |
| [frontend](https://github.com/Langclaw-AI-SUI-Ecosystem/frontend) | Next.js, React, Sui dApp Kit, AI SDK | User workspace, Sui wallet flow, Intelligence, Usage, Watchlist, Strategy Lab, Proof Center, and private memory controls |
| [backend](https://github.com/Langclaw-AI-SUI-Ecosystem/backend) | Node.js, TypeScript, Supabase, OpenAI, OpenClaw | Agent research workflow, wallet/API auth, provider orchestration, usage ledger, automation, Walrus and Seal integration, and Sui proof anchoring |
| [move](https://github.com/Langclaw-AI-SUI-Ecosystem/move) | Sui Move | Decision registry, trading journal, usage vault, memory registry, and Seal access policy |
| [langclaw-sui-walrus](https://github.com/Langclaw-AI-SUI-Ecosystem/langclaw-sui-walrus) | Project index | Public entry point and mainnet deployment summary for the split codebase |

## Product Coverage

| Area | What users get |
| --- | --- |
| Sui Intelligence | Smart-money summaries, holder-flow analysis, liquidity anomaly detection, protocol momentum, risk notes, and transparent source gaps |
| Alpha Watchlist | Saved Sui intelligence signals for follow-up analysis |
| Strategy Lab | Dune-backed Sui liquidity momentum backtests and deterministic paper-trade proofs |
| Proof Center | On-chain agent decisions and strategy journal records |
| Private Memory | Wallet-owned memories encrypted with Seal, stored on Walrus, and recalled only after on-chain access-policy approval |
| SUI Usage Credits | SUI-backed application credits with verifiable deposits and authorized withdrawal requests |
| Automation | Scheduled monitoring, run history, in-app notifications, and Telegram integration |

## Sui, Walrus, and Seal Proof Layer

Langclaw separates private data from public verification:

1. Agent memory is encrypted for the wallet owner using Seal.
2. The encrypted artifact is stored on Walrus.
3. Only content hashes, storage references, policy identifiers, and ownership
   metadata are recorded on Sui.
4. Recall requires the Seal access policy to approve the requesting wallet.

| Item | Mainnet value |
| --- | --- |
| Product chain | Sui mainnet |
| Langclaw Move package | [`0x7f3578ebe174b0343cd96391b2a1c75d5db4ad82c793650b3950bdb5634192e5`](https://suivision.xyz/package/0x7f3578ebe174b0343cd96391b2a1c75d5db4ad82c793650b3950bdb5634192e5) |
| Usage Vault shared object | [`0x816064d45dfe06194a973bce4b38a137365bbd6979c61b0d09435b7a443f3eff`](https://suivision.xyz/object/0x816064d45dfe06194a973bce4b38a137365bbd6979c61b0d09435b7a443f3eff) |
| Usage Vault AdminCap | [`0x21314b9534ca673cac1c79d6d1a63b9b0469d684504c974d3e8a5588873e8d09`](https://suivision.xyz/object/0x21314b9534ca673cac1c79d6d1a63b9b0469d684504c974d3e8a5588873e8d09) |
| Agent ID | `133` |
| Agent owner / recorder | [`0x4b635af81752a2bcdaeb908bd522173ad1c86a859a9c56ee59d3089c35e0a622`](https://suivision.xyz/account/0x4b635af81752a2bcdaeb908bd522173ad1c86a859a9c56ee59d3089c35e0a622) |
| Seal KeyServer | `0x86b608dcb3fcb9c629cfe6d865681977d1decb219a2eb98eb6058b87377feaf3` |
| Walrus Site object | `0x423a0cf7bfa109ed48ae6fae63eead7b7eae751b0885925b137bfd1d9e597d2b` |
| Package publish transaction | [`6kmuA94JsgM7uJ7MN32WEbWFMkF5rBuLUrUwFT4eTKED`](https://suivision.xyz/txblock/6kmuA94JsgM7uJ7MN32WEbWFMkF5rBuLUrUwFT4eTKED) |
| Vault setup transaction | [`ALvypw6EvadDXo4MCzgNEPgLJ8jES3rVLsWZHCnnqYVH`](https://suivision.xyz/txblock/ALvypw6EvadDXo4MCzgNEPgLJ8jES3rVLsWZHCnnqYVH) |

The Move package contains the `decision_registry`, `trading_journal`,
`usage_vault`, `memory_registry`, and `access_policy` modules.

## Demo Prompts

```text
Find smart-money accumulation on Sui
```

```text
Detect liquidity anomalies on Sui DEX pairs
```

```text
Rank Sui protocols by TVL and yield momentum
```

```text
Analyze holder flow and smart-money signals for a Sui token
```

## Safety and Scope

- Langclaw does not execute live trades or move user funds for trading.
- Strategy Lab paper trades are deterministic proof records, not exchange
  orders.
- SUI deposits fund internal application usage credits.
- Private memory content is never written to Sui in plaintext.
- Provider failures and unavailable evidence are surfaced as source gaps.
- Strong agent decisions and strategy outcomes can be anchored on Sui for
  public verification.

## Verification

Backend:

```bash
npm run typecheck
npm test
```

Frontend:

```bash
node --test tests/sui-wallet.test.mjs
pnpm typecheck
pnpm lint
pnpm build
```

Move:

```bash
sui move build
sui move test
```

Public entry point:

```text
https://langclaw-sui-walrus.vercel.app
```
