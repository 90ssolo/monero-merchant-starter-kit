# Editable Monero Invoice & Post-Payment Receipt Templates

Copy and adapt the templates below for freelance work, B2B billing, or manual customer orders.

> **Disclaimer:** Invoice and receipt formatting requirements (such as VAT/GST registration numbers, sequential invoice IDs, and local currency equivalents) vary by jurisdiction. Adapt these fields to meet your local tax and accounting laws.

---

## Template 1: Payment Request / Unpaid Invoice

```markdown
# INVOICE (UNPAID PAYMENT REQUEST)

**Merchant / Business Name:** [Your Business Name]
**Business Address / Tax ID:** [Optional: Your Address & Local Tax/VAT ID]
**Contact:** [billing@example.com]

- **Invoice Number:** INV-2026-0001
- **Issue Timestamp (UTC):** 2026-10-17 14:00 UTC
- **Price Quote Valid Until (UTC):** 2026-10-17 14:30 UTC
- **Bill To:** [Client / Customer Name]

---

### Itemized Summary

| Description | Qty | Unit Price (EUR) | Line Total (EUR) |
|---|---:|---:|---:|
| Consulting / Product Item | 1 | €150.00 | €150.00 |
| Tax / VAT (if applicable) | - | €0.00 | €0.00 |
| **Total Due (Fiat)** | | | **€150.00 EUR** |

---

### Monero (XMR) Payment Instructions

- **Exchange Rate Applied:** `1 XMR = €150.00 EUR` (Source: [Kraken / Bitfinex median at 14:00 UTC])
- **Exact Amount Due:** `1.000000000000 XMR`
- **Dedicated Invoice Subaddress:**
  `888tNkZrPN6JsEgekjMnABU4TBWoKf6vn57g6o24iGzTqGq6V7Z7VqN54zM7JmPzQhC2jX9fDq2VjX9mPzQhC2jX9fDq2V`
- **Monero URI:**
  `monero:888tNkZrPN6JsEgekjMnABU4TBWoKf6vn57g6o24iGzTqGq6V7Z7VqN54zM7JmPzQhC2jX9fDq2VjX9mPzQhC2jX9fDq2V?tx_amount=1.0&tx_description=INV-2026-0001`
- **Confirmation Policy:** Order is marked paid after **1 confirmation** (~2 minutes) on the Monero mainnet.

> **Important Notice:** This payment request is **not** proof of payment. Please send the exact XMR amount before the quote expiry time and retain your Transaction ID (`txid`) and Transaction Key (`tx_key`). If a refund is ever required, you will need to provide a Monero refund address because Monero does not expose sender addresses on-chain.
```

---

## Template 2: Post-Settlement Payment Receipt (Issued After Confirmation)

Issue this receipt **only after** your own wallet or payment server has verified the required confirmations on the invoice's dedicated subaddress.

```markdown
# PAYMENT RECEIPT (PAID & CONFIRMED)

- **Receipt for Invoice:** INV-2026-0001
- **Settlement Status:** PAID IN FULL
- **Confirmed Timestamp (UTC):** 2026-10-17 14:06 UTC
- **Amount Received:** `1.000000000000 XMR`
- **Fiat Value at Settlement:** `€150.00 EUR` (`1 XMR = €150.00 EUR`)
- **Receiving Subaddress:** `888tNkZrPN6J...fDq2V`
- **Transaction Hash(es) (TXID):** `d1a498b3f2e1c75b8a0e8d7f6c5b4a3e2d1c0b9a8f7e6d5c4b3a2e1f0d9c8b7a`
- **Confirmations at Verification:** 10 confirmations
```
