# RONANIS
RONANIS API BLOCKCHAIN 
==================================================
PROJECT NAME
RONANIS API BLOCKCHAIN
==================================================

A minimal, deterministic blockchain API protocol.

RONANIS is not a wallet.
RONANIS is not an exchange.
RONANIS is not a website.

RONANIS is a blockchain infrastructure protocol.

==================================================
PHILOSOPHY
==================================================

Bitcoin is the blockchain.
The node is the system.
The API is the interface.

Developers build.
Nodes execute.
Bitcoin settles.

RONANIS removes UI, accounts, sessions, and abstractions
and exposes blockchain execution directly via HTTP.

==================================================
WHAT RONANIS IS
==================================================

- Protocol-level API
- Blockchain-native execution
- Deterministic and explicit
- curl-first by design
- Pay-per-use (on-chain)

==================================================
WHAT RONANIS IS NOT
==================================================

- No UI
- No SDK
- No browser flows
- No cookies
- No sessions
- No off-chain credits

==================================================
ARCHITECTURE (ABSTRACT)
==================================================

[ Client ]
    |
    | HTTP API (KEY-authenticated)
    v
[ RONANIS Protocol ]
    |
    | On-chain settlement
    v
[ Bitcoin Network ]

Compute layers (AI) are value-gated and abstracted.
Implementation details are not part of the protocol.

==================================================
SUPPORTED NETWORKS
==================================================

ronanis.com  → MAINNET  → Bitcoin API (production)
ronanis.org  → TESTNET  → Bitcoin API (testing)
ronanis.net  → MAINNET  → AI Compute (paid)

==================================================
QUICK START (CURL)
==================================================

Create KEY:
curl -X POST "https://ronanis.org/api/?mode=key_create" \
  -H "Content-Type: application/json" \
  -d '{}'

Create Wallet:
curl -X POST "https://ronanis.org/api/?mode=wallet_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"net":"test"}'

Receive Bitcoin:
curl -X POST "https://ronanis.org/api/?mode=inbox_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXXXXXX","expected_sat":10000}'

Run AI (Paid):
curl -X POST "https://ronanis.net/api/?mode=ai_run" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXXXXXX","input":"your task"}'

==================================================
DESIGN PRINCIPLES
==================================================

- Single blockchain: Bitcoin
- Single unit: Satoshi
- Single interface: HTTP
- Single tool: curl

Everything is explicit.
Everything is programmable.
Everything is deterministic.

==================================================
SECURITY MODEL
==================================================

- No admin access
- No shared wallets
- No shared balances
- Each KEY owns isolated resources
- All value movement is on-chain

RONANIS provides infrastructure.
Developers define behavior.
Bitcoin enforces rules.

==================================================
STATUS
==================================================

- BTC API (MAIN / TEST)        → Stable
- Inbox receive flow           → Stable
- On-chain send                → Stable
- AI pay-per-use               → Stable
- Additional blockchains       → Planned (layered)

==================================================
LICENSE
==================================================

MIT License

==================================================
FINAL NOTE
==================================================

RONANIS is a protocol, not a product.

It does not promise.
It does not censor.
It does not interfere.

It executes.

==================================================
END OF FILE
==================================================
