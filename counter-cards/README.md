# Counter Display Cards: Customization & Printing Guide

This directory contains clean, vector-based printable counter cards (`.svg`) for physical storefronts, retail counters, event kiosks, and market stalls.

---

## Files in this Directory

* [`monero-counter-card-portrait.svg`](monero-counter-card-portrait.svg): 5" x 7" portrait standee format (standard acrylic photo/table display size).

---

## How to Customize for Your Business

You can customize this vector template in **2 minutes** using any free vector editor (such as Inkscape, Figma, or Adobe Illustrator) or a simple text editor.

### Option A: Static Merchant Subaddress QR
If you prefer a static counter display where customers type the total amount manually:
1. Generate an unused **Monero Subaddress** (starts with `8`) in your wallet (e.g. MonkStash, Feather, Cake Wallet, or Official Monero GUI).
2. Generate a QR code using standard URI formatting:
   ```text
   monero:8xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx?recipient_name=YourStoreName
   ```
3. Open `monero-counter-card-portrait.svg` in Inkscape/Figma, replace the placeholder box (`x="200" y="410" width="400" height="400"`) with your generated QR image, and save.

### Option B: Dynamic Web Till / Payment Link
If you use a lightweight web point-of-sale till (such as [MonkStash Web POS / Payment Links](https://monkstash.com/pay)):
1. Create your merchant till URL or store checkout link.
2. Generate a QR code pointing directly to your till or web invoice page.
3. Replace the placeholder box with your QR code. Customers can scan to open the invoice or pay directly on mobile.

---

## Recommended Printing Specifications

| Attribute | Recommended Setting |
|---|---|
| **Paper Stock** | 300–350 gsm heavy cardstock or matte photo paper |
| **Finish** | Matte or soft-touch laminate (avoids QR glare under store lighting) |
| **Display Mount** | 5" x 7" clear T-shape acrylic table stand |
| **Color Profile** | CMYK (Monero Orange: `#FF6600` / `C0 M75 Y100 K0`) |
