# Payment Verification Checklist for Merchants & Cashiers

Use this operational checklist before opening the till, during each customer checkout, and when closing out at the end of the day.

<p align="center">
  <img src="../assets/checkout-verification-flow.svg" alt="Payment Verification Stages" width="100%" />
</p>

---

## 1. Pre-Shift Setup Checklist (2 Minutes)

- [ ] **Wallet / Till Synced:** Confirm the till tablet or wallet shows **Synced (100%)** against the current Monero mainnet height.
- [ ] **Mainnet Confirmed:** Verify the active network is **Mainnet** (addresses start with `4` or `8`), not Stagenet (`5` or `7`) or Testnet (`9` or `B`).
- [ ] **Watch-Only / View-Only Mode Active on Counter Devices:** Ensure the shared counter tablet cannot spend funds (either opened as a view-only wallet or locked appropriately).
- [ ] **Unique Till Account Configured (Multi-Register Shops):** If running more than one counter tablet with the same wallet, verify each tablet uses its own till number / wallet account (for example, Till 1 = Account 1, Till 2 = Account 2 in [MonkStash POS](https://monkstash.com/monero-pos)) so two registers never display the same subaddress.

---

## 2. Per-Sale Verification Checklist

- [ ] **Generate a Fresh Subaddress per Order:** Never reuse the same address for two simultaneous customers, and never match payments by guessing from the XMR amount alone.
- [ ] **Do Not Trust Customer Phone Screenshots:** A payment link, QR code, or "Sent" screen on the customer's phone is **not** proof of payment. Always verify on the merchant's own till or wallet.
- [ ] **Check Amount Received vs. Amount Due:**
  - If `received == due`: Proceed to confirmation check below.
  - If `received < due` (**Partial Payment**): Keep the invoice open and show the remaining XMR balance due before the price hold expires.
  - If `received > due` (**Overpayment**): Complete the sale and record the surplus XMR for refund or credit according to the [Refund Runbook](../refunds-runbook/README.md).
- [ ] **Apply Your Confirmation Policy Preset:**
  - **Quick Preset (In-person counter sales where goods are handed over physically):**
    - Up to `0.1 XMR`: Paid as soon as seen in mempool (`0-conf`).
    - `0.1 XMR` to `1.0 XMR`: Wait for **1 confirmation** (~2 minutes).
    - Above `1.0 XMR`: Wait for **10 confirmations** (~20 minutes).
  - **Standard Preset (Everyday retail & online physical orders):**
    - Up to `5.0 XMR`: Wait for **1 confirmation**.
    - Above `5.0 XMR`: Wait for **10 confirmations**.
  - **Safe Preset (High-value goods, instant digital downloads, gift cards):**
    - Always wait for **10 confirmations** before fulfilling.
- [ ] **Watch for Reverted / Dropped 0-Conf Transactions:** If an unconfirmed (`0-conf`) transaction drops from the mempool before being mined into a block, stop fulfillment immediately.

---

## 3. End-of-Shift Closeout Checklist

- [ ] **Review Open / Late / Partial Sales:** Mark any unresolved partial or late payments as `accepted`, `refund`, or `cancelled` in your till or ledger.
- [ ] **Export Daily CSV Records:** Export the day's sales (`monkstash-sales-YYYY-MM-DD.csv` or wallet CSV export) and archive it in your accounting folder.
- [ ] **Check Subaddress Lookahead Gap (For High-Volume Stores):** Ensure the number of consecutive unpaid invoices has not exceeded your backup wallet's subaddress lookahead window (200 by default in standard Monero wallets).
