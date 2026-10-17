# Cashier & Staff Quick-Reference Cheat Sheet

A concise 1-page operational guide designed to be printed and kept at the cash register, counter, or staff tablet.

---

## 3-Step Checkout Workflow

```text
[ Step 1: Present Bill ]  --->  [ Step 2: Customer Broadcasts ]  --->  [ Step 3: Verify & Complete ]
Present total in fiat &         Customer scans QR and slides           Wait for Mempool Alert (0-conf)
calculated XMR amount           to broadcast payment                   or 1-10 confirmations by policy
```

### 1. Presenting the Amount
- Calculate the total in local currency and convert to XMR using the current rate.
- Display the dynamic payment QR or have the customer scan your static till QR.
- **Always specify the exact amount in XMR** so the customer does not underpay due to exchange slippage.

### 2. Monitoring the Transaction
When the customer clicks "Send" on their phone:
- **Instant Mempool Detection (0-conf):** Within **2 to 5 seconds**, an unconfirmed transaction will appear on your till terminal or wallet interface with a "Pending" or "Incoming (0/10)" badge.
- The transaction has been propagated across the peer-to-peer Monero network.

### 3. Confirmation Policy (When to Hand Over Goods)

| Transaction Type | Recommended Policy | Rationale |
|---|---|---|
| **Low Value** (Coffee, snacks, bakeries, casual dining < $50) | **0-conf (Mempool detection)** | Double-spend risk is near zero for low-value retail in-person purchases. Handing over goods immediately ensures fast counter throughput. |
| **Medium Value** ($50 - $300) | **0-conf + Valid TX Hash check** | Confirm that fee is standard and transaction appears in connected node's pool. |
| **High Value** ($300+, luxury items, electronics, gift cards) | **1 to 2 Confirmations (approx. 2-4 mins)** | Wait for the transaction to be minted into at least one block to guarantee finality. |

---

## Exception Handling: What to Do If...

### Scenario A: "Customer says they sent, but nothing appears on screen"
1. **Check customer's wallet status:** Ensure their wallet has finished syncing blocks and shows a green "Connected" indicator.
2. **Verify network:** Ask if they are on Monero Mainnet (not testnet/stagenet).
3. **Verify destination address:** Confirm the first 4 characters and last 4 characters match the invoice subaddress.
4. **Internet connection:** Ensure the till device and merchant node/relay have active internet access.

### Scenario B: "Customer sent the wrong amount (Underpayment)"
- In Monero, an invoice can receive multiple payments.
- If a customer underpays by 0.05 XMR, show them the remaining balance.
- Once the secondary transaction arrives, the invoice marks as fully settled.
- **Never mark an order completed until the total requested amount is fulfilled.**

### Scenario C: "Customer accidentally sent too much (Overpayment)"
- Record the overpaid amount and the order ID in your [Accounting Sheet](../accounting-templates/monero-daily-sales-ledger.csv).
- Follow the [Merchant Refund Runbook](../refunds-runbook/README.md) to return the excess balance to an address provided by the customer.

---

## Cashier Security Rules

* **Rule #1: Never share seed words.** No customer, technician, or manager will ever ask for your 14, 16, or 25 recovery words.
* **Rule #2: The till terminal is view-only.** The point-of-sale device should only hold a view-only wallet or payment link session. No private spend keys should reside on cash register hardware.
* **Rule #3: Do not rely solely on customer's screen.** Always verify payment receipt on the merchant's till screen or merchant notification device.
