# Monero Merchant Starter Kit [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> A practical, open-source operational toolkit for small businesses, freelancers, market stalls, and e-commerce stores accepting **Monero (XMR)**.

Accepting Monero eliminates credit card chargeback fraud, avoids 2–4% payment processor interchange fees, and provides complete financial privacy for both merchant and customer.

This starter kit contains **production-ready templates, printable counter cards, staff training sheets, and accounting runbooks** designed to get any business accepting Monero within minutes.

---

## What is in this Toolkit

| Asset / Tool | Location | Description |
|---|---|---|
| **Printable Counter Card** | [`counter-cards/`](counter-cards/) | Vector `.svg` template (5" x 7" acrylic standee format) with official Monero logo and custom QR slot. |
| **Cashier Cheat Sheet** | [`cashier-guide/`](cashier-guide/) | 1-page operational guide for front-of-house staff: 0-conf vs block confirmations, mempool detection, and troubleshooting. |
| **Refunds & Dispute Runbook** | [`refunds-runbook/`](refunds-runbook/) | SOP explaining how Monero's stealth addresses impact returns, how to verify payment keys (`tx_key`), and how to issue refunds. |
| **Daily Sales Ledger** | [`accounting-templates/`](accounting-templates/) | Bookkeeping guide and ready-to-use CSV template for tracking XMR rates, fiat totals, and tax reporting. |

---

## 2 Operational Paths to Accept Monero

Depending on your store's setup, choose the operational model that matches your business:

### Path A: The Direct Wallet Path (Zero Server Setup)
* **Best for:** Freelancers, market vendors, pop-up shops, and food trucks.
* **How it works:**
  1. Open your Monero wallet (e.g. Feather, Cake Wallet, Monero.com, or official Monero GUI).
  2. Generate a dedicated subaddress (begins with `8`).
  3. Export the QR code and insert it into the [Printable Counter Card](counter-cards/monero-counter-card-portrait.svg).
  4. Display on your counter. When a customer scans and pays, you will hear a ping and see the incoming transaction in your wallet within 3 seconds.

### Path B: The Lightweight Web Till / E-Commerce Path
* **Best for:** Retail stores needing dynamic totals per order, or WooCommerce web stores.
* **How it works:**
  1. Use a browser-based till or self-hosted gateway such as **[MonkStash Web POS / Payment Links](https://monkstash.com/pay)** or **[MoneroPay](https://moneropay.eu)**.
  2. The cashier enters the total order price in USD/EUR on a phone or tablet.
  3. A dynamic QR code appears with exact XMR pricing and real-time exchange rates.
  4. The web till monitors the mempool and turns green automatically when paid.

---

## Staff Training & Operational Rules

1. **Never share seed phrases:** Legitimate software, customers, and technicians will never ask for your 14, 16, or 25 recovery words.
2. **Understand Confirmations:**
   - **0-conf (Mempool):** Sufficient for low-value retail (coffee, groceries, lunch). Instant settlement.
   - **1–2 Confirmations (approx. 2–4 mins):** Recommended for high-value merchandise (jewelry, electronics) before handing over goods.
3. **Refunds Require Destination Addresses:** Because Monero uses one-time stealth addresses, merchants cannot "refund to sender". Always collect a fresh customer subaddress for returns.

---

## License

All templates, guides, and vector graphics in this repository are released under the [MIT License](LICENSE). You are free to print, modify, rebrand, and distribute them for commercial and personal use.
