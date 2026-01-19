RONANIS API BLOCKCHAIN
=====================
Single protocol.
Multiple environments.
Same commands.
Different policies.
--------------------------------------------------
ENVIRONMENTS
--------------------------------------------------
ronanis.com  -> MAINNET (Production, real Bitcoin)
ronanis.org  -> TESTNET (Testing, no value)
ronanis.net  -> COMPUTE (AI / API only, NO SEND)
--------------------------------------------------
COMMON RULES (ALL)
--------------------------------------------------
- HTTP POST only
- JSON only
- curl only
- No UI
- No SDK
- No sessions
- No cookies
- Satoshi unit
- Deterministic behavior
==================================================
ronanis.com  (MAINNET)
==================================================
REAL BITCOIN
REAL SATOSHI
SEND MAY BE ENABLED
------------------------
Create Key
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=key_create" \
  -H "Content-Type: application/json" \
  -d '{}'
------------------------
Create Wallet (main)
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"net":"main"}'
------------------------
Wallet Balance
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_balance" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXX"}'
------------------------
Create Inbox (Receive)
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=inbox_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXX","expected_sat":10000}'
------------------------
Refresh Inbox
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=inbox_refresh" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"inbox_id":"i_XXXXXXXX"}'
------------------------
Send Bitcoin (if enabled)
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=wallet_send" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXX","to":"bc1...","amount_sat":50000,"speed":"normal"}'
------------------------
Health
------------------------
curl -sS -X POST "https://ronanis.com/api/?mode=health" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
==================================================
ronanis.org  (TESTNET)
==================================================
TEST BITCOIN
NO VALUE
NO RISK
------------------------
Create Key
------------------------
curl -sS -X POST "https://ronanis.org/api/?mode=key_create" \
  -H "Content-Type: application/json" \
  -d '{}'
------------------------
Create Wallet (test)
------------------------
curl -sS -X POST "https://ronanis.org/api/?mode=wallet_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"net":"test"}'
------------------------
Wallet Balance
------------------------
curl -sS -X POST "https://ronanis.org/api/?mode=wallet_balance" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXX"}'
------------------------
Create Inbox (Receive)
------------------------
curl -sS -X POST "https://ronanis.org/api/?mode=inbox_create" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"wallet_id":"w_XXXXXXXX","expected_sat":10000}'
------------------------
Refresh Inbox
------------------------
curl -sS -X POST "https://ronanis.org/api/?mode=inbox_refresh" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{"inbox_id":"i_XXXXXXXX"}'
------------------------
Health
------------------------
curl -sS -X POST "https://ronanis.org/api/?mode=health" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
==================================================
ronanis.net  (COMPUTE / AI)
==================================================
NO BLOCKCHAIN SEND
NO BITCOIN TRANSFER
COMPUTE ONLY
------------------------
Create Key
------------------------
curl -sS -X POST "https://ronanis.net/api/?mode=key_create" \
  -H "Content-Type: application/json" \
  -d '{}'
------------------------
Key Status
------------------------
curl -sS -X POST "https://ronanis.net/api/?mode=key_status" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
------------------------
Health
------------------------
curl -sS -X POST "https://ronanis.net/api/?mode=health" \
  -H "X-RON-KEY: RON-XXXXXXXXXXXX" \
  -H "Content-Type: application/json" \
  -d '{}'
--------------------------------------------------
FINAL NOTES
--------------------------------------------------
- Same protocol
- Same curl structure
- Different policies
- Machines and humans are equal
- Bitcoin settles
- Nodes execute
- APIs expose
END
==================================================
DATE: 2026-01-19
HASH (SHA256):
a757f900a9a1add606f4ae3e9386a87566204e2a6871320e2b50ca78d4e1cc1d
==================================================
END OF DOCUMENT
