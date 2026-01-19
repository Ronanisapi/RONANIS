==================================================
PROJECT NAME
RONANIS API BLOCKCHAIN
==================================================
NETWORK TYPE: MAIN
CURRENCY: BTC
VERSION: V2
STATUS: STABLE
DATE: 2026-01-18
--------------------------------------------------
NOTICE
--------------------------------------------------
This is a real blockchain protocol.
DO NOT test with real funds unless you fully
understand Bitcoin and on-chain behavior.
For safe testing, use the TEST version:
https://ronanis.org
==================================================
PHILOSOPHY
==================================================
RONANIS is not a wallet.
RONANIS is not an exchange.
RONANIS is not a website.
RONANIS is a blockchain API protocol.
Bitcoin is the blockchain.
The node is the system.
The API is the interface.
Developers build.
The node executes.
Bitcoin settles.
==================================================
DESIGN PRINCIPLES
==================================================
- Single blockchain: Bitcoin
- Single unit: Satoshi
- Single interface: HTTP API
- Single tool: curl
No UI
No SDK
No sessions
No cookies
Everything is explicit.
Everything is programmable.
Everything is deterministic.
==================================================
API ACCESS
==================================================
Endpoint:
POST https://ronanis.com/api/
Headers:
X-RON-KEY: <KEY>
Content-Type: application/json
All operations are POST.
Action is defined by the `mode` query parameter.
==================================================
CORE MODES (STABLE)
==================================================
Key:
- key_create
- key_status
Wallet:
- wallet_create
- wallet_list
- wallet_balance
- wallet_send
Inbox (Receive):
- inbox_create
- inbox_refresh
System:
- health
==================================================
CURL — VERIFIED WORKING (COPY / PASTE)
==================================================
1) Create KEY (Public)
curl -sS -X POST "https://ronanis.com/api/?mode=key_create" \
  -H "Content-Type: application/json" \
  -d '{}'
Response:
{"ok":true,"result":{"key":"RON-XXXXXXXXXXXX"}}
--------------------------------------------------
2) Key Status
curl -sS -X POST "https://ronanis.com/api/?mode=key_status" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
--------------------------------------------------
3) Create Wallet (per KEY)
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"net":"main"}'
Response:
{"ok":true,"result":{"wallet_id":"w_XXXXXXXXXXXX","net":"main"}}
--------------------------------------------------
4) List Wallets
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_list" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
--------------------------------------------------
5) Wallet Balance
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_balance" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXXXXXX"}'
==================================================
RECEIVE FLOW (INBOX)
==================================================
6) Create Inbox (Receive Address)
curl -sS -X POST "https://ronanis.com/api/?mode=inbox_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXXXXXX","expected_sat":10000}'
Response:
{"ok":true,"result":{"inbox_id":"i_XXXXXXXXXXXX","address":"bc1..."}}
--------------------------------------------------
7) Refresh Inbox
curl -sS -X POST "https://ronanis.com/api/?mode=inbox_refresh" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"inbox_id":"i_XXXXXXXXXXXX"}'
Inbox States:
- created
- seen_0conf
- confirmed_1
==================================================
SEND FLOW
==================================================
8) Send Bitcoin
(Service fee is applied automatically)
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_send" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{
    "wallet_id":"w_XXXXXXXXXXXX",
    "to":"bc1...",
    "amount_sat":50000,
    "speed":"normal"
  }'
Response:
{
  "ok": true,
  "result": {
    "txid": "...",
    "amount_sat": 50000,
    "network_fee_sat": ...,
    "service_fee_sat": 5000,
    "fee_txid": "...",
    "fallback_used": true
  }
}
==================================================
SYSTEM
==================================================
9) Health Check
curl -sS -X POST "https://ronanis.com/api/?mode=health" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
==================================================
RESPONSIBILITY MODEL
==================================================
RONANIS provides infrastructure only.
Developers define behavior.
Bitcoin enforces rules.
==================================================
FINAL STATEMENT
==================================================
RONANIS API BLOCKCHAIN is a protocol.
It does not promise.
It does not censor.
It does not interfere.
It executes.
==================================================
DOCUMENT INTEGRITY
==================================================
==================================================
END OF DOCUMENT
==================================================
==================================================
DATE: 2026-01-19
HASH (SHA256):
85e63d582a59b20b357390db50132761fc9f9e62c56b9f8d5d3f5b04b62526d1
==================================================
