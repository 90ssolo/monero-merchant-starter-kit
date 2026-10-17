# Monero Accounting & Tax Recordkeeping Guide

Operating a retail or e-commerce business with Monero requires clean recordkeeping for bookkeeping, sales reconciliation, and tax compliance (such as capital gains or gross receipts accounting).

---

## 1. Core Fields to Record for Every Sale

Because Monero amounts are private and unsearchable by external auditors on a block explorer, merchants maintain their own internal sales ledger.

Every transaction should record:
1. **Date & UTC Timestamp**
2. **Order / Invoice Number** (matching internal POS or e-commerce ID)
3. **Transaction Type:** `sale`, `refund`, or `fee`
4. **Amount in XMR:** Recorded in full 12-decimal atomic precision
5. **Prevailing Exchange Rate:** Spot rate in local accounting currency (USD/EUR/GBP) at timestamp
6. **Fiat Equivalent Value:** Total amount billed
7. **Transaction Hash (TXID):** Proof of block inclusion
8. **Subaddress Used:** For internal reconciliation against the invoice

A ready-to-use CSV template is provided in [`monero-daily-sales-ledger.csv`](monero-daily-sales-ledger.csv).

---

## 2. Generating View-Only Transaction Exports

To generate external accounting records without touching private spend keys:

* **Official Monero CLI / RPC:** Run `export_transfers` or `get_transfers` on your view-only wallet.
* **Feather Wallet:** Go to `History -> Select All -> Export to CSV`.
* **MonkStash Pay:** Use the administrative `/api/invoices/export` endpoint or review the invoice ledger in your dashboard.

---

## 3. Handling Capital Gains vs. Trading Revenue

* **Direct Fiat Conversion:** If you immediately convert received XMR to fiat via an exchange or OTC desk, the taxable gross sales amount is typically fixed at the sale timestamp value.
* **Holding XMR on Balance Sheet:** If your company holds received XMR in treasury, treat each subsequent expenditure or conversion as a disposal event for capital gains reporting according to your local jurisdiction's tax guidance.
