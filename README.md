# ParceLock MVP prototype

Clickable MVP for **ParceLock**, a self-service parcel room for condos and apartments (TU109 group project).

Open `index.html` in a browser, or use the GitHub Pages link. There's no install, no login and no backend.

## Views

| Link | What it is |
|---|---|
| `#overview` | What the MVP covers and a 2-minute demo script |
| `#demo` | Resident phone and door panel side by side (best for presenting) |
| `#resident` | Resident app: register tracking codes, COD wallet top-up, one-time pickup QR |
| `#door` | Door panel: courier drop-off (weigh, scan, bay guidance, COD payout, proof of delivery) and resident pickup (QR, lit bays, weight check) |
| `#office` | Juristic office: alerts, bay occupancy, parcels, overtime fees, activity log with CSV export |

## Flows (from the proposal)

1. **Registration:** the resident registers the tracking code and tops up the wallet for COD.
2. **Courier drop-off:** the courier weighs the parcel and scans its code. Unregistered codes and COD that the wallet doesn't cover are refused. The LED shows the assigned bay and the bay scale confirms the weight. A mismatch locks the room and alerts the office. Then COD payout and a digital proof of delivery.
3. **Resident pickup:** the one-time QR lights up the resident's bays. The bay scales check each parcel taken, and a wrong parcel triggers an alarm and an office alert. An overtime fee applies after 3 days.

## What is simulated

- The smart lock, LED strips, scales and cameras are shown on screen; there's no hardware.
- QR and label scanning are buttons or typed codes.
- Payments and wallets are simulated.
- Data is kept in the browser's localStorage, so open the views as tabs in the same browser to keep them in sync. **Reset demo data** in the office view restores the starting state.

## Demo rooms

| Room | Starting state |
|---|---|
| 1204 | Two registered parcels (one COD ฿359), wallet ฿500 |
| 1240 | One parcel with almost the same weight as 1204's, plus a COD ฿590 parcel with an empty wallet (refused at the door) |
| 0815 | One parcel already in Bay C, plus a COD ฿1,290 parcel with a ฿1,000 wallet (top up to deliver) |
| 2107 | Envelope stored 4 days ago (overtime fee ฿10) |

Uses [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) (MIT), inlined.
