### PR Title

feat: add settlerskills - local-first sovereign payment infrastructure

---

### PR Description

This Pull Request introduces **settlerskills**, a novel, local-first configuration and progressive rule engine optimized for the Solana AI Kit. While existing ecosystem skills focus primarily on cloud-dependent protocol actions (such as remote swaps), `settlerskills` targets a critical unaddressed gap: enabling AI agents (e.g., Claude Code, Cursor) to securely architect self-hosted, zero-dependency non-custodial payment rails and transaction monitoring infrastructure inside restricted local host environments.

The full standalone implementation, reference templates, and engineering specifications can be reviewed here: **[https://github.com/nathfavour/settlerskills](https://github.com/nathfavour/settlerskills)**

#### Key Capabilities Contributed

* **Token-Efficient Progressive Layout:** Follows the exact `solana-game-skill` layout pattern. Uses an optimized `SKILL.md` root router that lazy-loads modular context files (`rules/`) sequentially, preventing LLM token blowouts.
* **Modern Functional RPC Hardening:** Trains AI runtimes to enforce Anza's modern tree-shakeable functional primitives (`createSolanaRpc()`, `pipe()`) and aggressively bans legacy `@solana/web3.js` v1 anti-patterns.
* **Local E2EE Vault Safety:** Outlines rigid guidelines for WebCrypto AES-GCM-256 local configuration state handling and ephemeral `Uint8Array` allocations that are zeroed out immediately post-signature execution to prevent heap retention exploits.
* **Agentic Drain Protection Engine:** Interposes a mandatory risk-evaluation state engine requiring automated block simulation (`simulateTransaction`), transaction volume limits, and strict local address whitelists before broadcasting payload transactions.
* **Pure Sandbox Linker:** Includes an idempotent, non-destructive `install.sh` script built explicitly to honor local agent workspace boundaries (`./.claude/rules/` or `./.agents/rules/`) without mutating global system files.

#### Repository Blueprint

```
settlerskills/
├── README.md                      # Architecture, installation, and usage matrix
├── LICENSE                        # Explicit MIT License for upstream ingestion
├── ARCHITECTURE.md                # System engineering invariants and quality gates
├── install.sh                     # Idempotent local workspace configuration linker
└── skill/
    ├── SKILL.md                   # Token-efficient context router
    ├── rules/
    │   ├── 01_functional_rpc.md   # Functional code style rules for SVM interactions
    │   ├── 02_local_e2ee_vault.md # Invariants for local key encapsulation and storage
    │   └── 03_drain_protection.md # Risk verification logic and execution boundaries
    └── templates/
        ├── loop.go                # Reference low-allocation WebSocket event listener
        └── sign.ts                # Reference modern transaction compilation pipeline

```

Closes the community requirement for autonomous, edge-compatible payment routing frameworks. Ready for review and upstream integration.
