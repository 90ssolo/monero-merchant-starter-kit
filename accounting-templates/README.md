# Monero Accounting & End-of-Day Recordkeeping Guide

Because Monero amounts and stealth addresses are private on the blockchain, external block explorers cannot reconstruct your store's sales history. Maintaining clean internal sales records and end-of-day closeout files ensures accurate bookkeeping, staff reconciliation, and tax reporting.

> **Disclaimer:** Accounting and tax rules (such as VAT/GST invoicing, fiat valuation timestamps, and record retention periods) differ by country and state. Confirm specific reporting requirements with a qualified accountant in your jurisdiction.

---

## Templates in This Directory

1. **[`monero-daily-sales-ledger.csv`](monero-daily-sales-ledger.csv):**
   Per-transaction ledger recording date, time, order ID, type (`sale` or `refund`), 12-decimal XMR amount, fiat exchange rate at the time of sale, fiat total, transaction hash (`txid`), receiving subaddress, and confirmation count.
2. **[`end-of-day-reconciliation.csv`](end-of-day-reconciliation.csv):**
   End-of-shift summary per register (`till_id` and Monero `wallet_account`), tracking opening/closing subaddress indices, paid vs. expired invoice counts, gross XMR received, refunds dispatched, and net fiat value.

---

## How to Export Records from Monero Software

### 1. MonkStash Browser Till & Wallet (`wallet.monkstash.com`)
- Exports CSV files directly in the browser from local encrypted state (`monkstash-sales-YYYY-MM-DD.csv`, `monkstash-payment-requests-YYYY-MM-DD.csv`, and `monkstash-history-YYYY-MM-DD.csv`) with a UTF-8 byte-order mark so spreadsheet software opens them cleanly.
- Nothing is uploaded to a server during export.
- Cashier sales CSV columns:
  `created_at,reference,price,currency,xmr_due,rate,rate_source,status,decision,xmr_received,xmr_overpaid,expires_at,subaddress_index,address,tx_hashes`

### 2. Desktop & Mobile Wallets (Monero GUI, Feather, Cake Wallet)
- **Feather Wallet:** `History -> Right-click -> Export to CSV`.
- **Official Monero GUI / CLI:** Use `History -> Export` or run `export_transfers` in `monero-wallet-cli`.
- **Note:** Wallet-level exports record blockchain arrival timestamps and XMR amounts, so pair them with your point-of-sale order references and fiat exchange rates at the time of sale.

### 3. Self-Hosted Payment Servers
- **MonkStash Pay (v0.1 in testing):** Stores full invoice records (including locked fiat rate, rate source, subaddress index, and `txHashes`) in `invoices.json` (with `invoices.json.bak` backup) and exposes `GET /api/invoices/:id`.
- **BTCPay Server (Monero Plugin):** Exports CSV and JSON invoice reports from the back-office Invoices view.
