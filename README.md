# ponsmcp-docs

> Official documentation for PonsMCP — autonomous AI agent payments on the Machine Payments Protocol, settled on Robinhood Chain.

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## Documentation Structure (planned)

```
docs/
├── concepts/
│   ├── mpp-protocol.md          # What is MPP and HTTP 402
│   ├── rh-settlement.md         # How on-chain escrow works on Robinhood Chain
│   └── agent-integration.md     # Autonomous payment workflows
├── guides/
│   ├── typescript-sdk.md        # Full TypeScript SDK guide
│   ├── openclaw-setup.md        # Configure OpenClaw agents
│   ├── merchant-integration.md  # Accept MPP payments
│   └── security.md              # Wallet security and policies
└── api/
    ├── sdk-reference.md         # SDK API reference
    └── contracts.md             # Smart contract ABIs
```

---

## Core Concepts

### Machine Payments Protocol (MPP)

MPP is a standard by Stripe that enables AI agents to discover and pay for services autonomously via HTTP 402 responses. When an agent hits a 402, PonsMCP automatically negotiates and executes the payment.

### Robinhood Chain Settlement

All payments are settled on-chain via Robinhood Chain — an EVM-compatible Arbitrum Orbit L2 (chainId 4663) with USDG (Global Dollar, 6 decimals) as the settlement asset. Funds are held in escrow and released only after cryptographic proof of delivery.

| Setting | Value |
|---------|-------|
| Chain ID | `4663` |
| RPC | `https://rpc.mainnet.chain.robinhood.com` |
| Explorer | `https://robinhoodchain.blockscout.com` |
| $PONS | `0x39dBED3a2bd333467115dE45665cC57F813C4571` |
| USDG | `0x5fc5360D0400a0Fd4f2af552ADD042D716F1d168` |

### Agent Integration

Agents discover MPP-enabled services through directory APIs and MCP manifests, then negotiate and settle payments without human intervention.

---

## License

MIT — see [LICENSE](LICENSE).
