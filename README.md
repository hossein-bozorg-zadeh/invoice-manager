# مدیریت فاکتور — Invoice Manager

A fully client-side Persian (RTL) invoice & finance manager, inspired by the
mechanics of catstester.ir — rebuilt from scratch as a single static file with
zero dependencies and zero backend.

**How it works:** everything runs in the browser. All data (people, items,
cheques, invoices, profile) lives in `localStorage`; nothing is ever sent to a
server. Invoices are shared by encoding the invoice itself into the URL, so the
customer-facing payment page works even though there is no backend.

## Features

- **داشبورد** — جمع دریافتی / جمع هزینه / مانده حساب, recent items, cheques due in 14 days
- **آیتم‌ها** — income (`دریافتی`) and expense (`هزینه`) entries in Rials with
  date, person, auto-generated tracking code (`کد پیگیری`), CSV export
  (Excel-compatible with UTF-8 BOM)
- **کارمندان و کارفرما** — manage employers and employees
- **چک‌ها** — cheque registry with due dates and live status badges
  (روز مانده / روز گذشته / امروز)
- **فاکتور** — build invoices from line items, save with a tracking code, copy
  a shareable customer payment link, print, mark paid/unpaid
- **صفحه پرداخت مشتری** — read-only invoice view (encoded in the URL hash) with
  the payment guide: شماره شبا, شماره کارت, account name and receipt note
- **تنظیمات** — profile (name, phone, IBAN, card, payment note), JSON
  backup/restore, full data reset

## Run it

It is one file — `index.html`. Open it, or serve it:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

A server is only needed so `localStorage` is scoped to a proper origin; any
static host works. Live: https://hossein-bozorg-zadeh.github.io/invoice-manager/

## Privacy

No network calls except the Vazirmatn webfont. No analytics. No backend.
Clearing your browser data clears the app; use تنظیمات → خروجی JSON for backups.

MIT License.
