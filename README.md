# Northbridge Capital Ltd. — personal portal

A complete buildless, mobile-first PWA for GitHub Pages. No installation, account, API key, database, or build step is required. The project contains all source code and four unmodified original documents.

## انتشار روی GitHub Pages

1. فایل ZIP را از حالت فشرده خارج کنید.
2. در GitHub یک مخزن جدید بسازید؛ مثلاً `northbridge-portal`.
3. **محتویات داخل پوشه پروژه** را در ریشه مخزن بارگذاری کنید؛ `index.html` باید در ریشه باشد، نه داخل یک پوشه اضافی. پوشه‌های `assets` و `documents` را هم اضافه کنید. فایل `.nojekyll` را نیز نگه دارید.
4. در مخزن به **Settings → Pages** بروید.
5. در **Build and deployment → Source** گزینه **Deploy from a branch** را انتخاب کنید.
6. شاخه **main** و پوشه **/(root)** را انتخاب و **Save** کنید.
7. پس از پایان انتشار، لینک نمایش‌داده‌شده در Pages را باز کنید. شکل معمول آدرس: `https://YOUR-USERNAME.github.io/northbridge-portal/`.
8. چهار صفحه و دانلود چهار سند را در آدرس منتشرشده بررسی کنید.

## نصب روی آیفون

لینک HTTPS منتشرشده را در Safari باز کنید. **Share → Add to Home Screen** را بزنید. اگر گزینه **Open as Web App** نمایش داده شد آن را روشن کنید و **Add** را بزنید. لوگوی N به‌عنوان آیکون ظاهر می‌شود. داشبورد پس از اولین بارگذاری موفق آفلاین هم در دسترس است. اسناد اصلی را برای استفاده آفلاین جداگانه دانلود کنید.

## What is included

- Overview with €35,000 contractual principal, €1,050 monthly interest, 14 selected monthly payments totaling €14,700, and €35,000 initial bank credit on 22 August 2025.
- Searchable activity, year filters, selected-view CSV exports, and source-page links with the bank's counterparty and reference details.
- The exact 24-month schedule from the original contract, separate from actual bank value dates.
- €39,200 contractual settlement: €35,000 principal + €1,050 final interest due 20 November 2026; €3,150 early termination charge due 30 November 2026.
- Original contract, settlement PDF, signed photo and user-designated corrected ING statement ending `.pdf.pdf.pdf`.
- Header logo, SVG mark, iPhone touch icon, 192px/512px app icons, manifest, scoped offline service worker.

## Evidence and calculations

The bank snapshot ends 16 November 2026. All 14 selected monthly records are −€1,050 and carry the bank's loan number 1130960. The contract and settlement PDF carry 98127456. Their relationship is recorded as user-declared; it is not independently established by the portal. Northbridge is the only portal brand, while bank provenance is preserved in record details and exports.

The original contract describes a purchase agreement / structured financial arrangement and explicitly says it is not a traditional loan. It specifies interest-only payments with a final principal balloon. Historical monthly interest is **not** deducted from principal or from the €39,200 settlement. The agreement's planned dates are preserved exactly; they are not replaced with a universal 25th-of-month schedule.

Other transfers, including large additional payments, are excluded only from the selected UI view. They remain in the complete original bank statement. The selected payment dataset is not a complete bank ledger. No payment is initiated by this project; no settlement receipt, clearance, lender validation, discharge, or live balance is fabricated. Signed acceptance alone does not establish clearance.

## Source files

| File | Purpose |
|---|---|
| `index.html` | Application shell, navigation, dialog, metadata |
| `styles.css` | Responsive visual design and accessibility states |
| `app.js` | Four pages, filtering, CSV, provenance, install guidance |
| `data.json` | Document-backed figures, payment records, schedule, hashes |
| `manifest.webmanifest` | Installable app settings, relative start URL and scope |
| `sw.js` | Network-first offline shell, limited to this project path |
| `assets/` | Vector logo and app icons |
| `documents/` | Unchanged user originals |
| `verify.mjs` | Integrity and data checks; run `node verify.mjs` |

## Local preview

Serve this directory over HTTP, for example `python -m http.server 8080` if Python is installed, then open `http://localhost:8080`. Opening `index.html` directly as a local file cannot load the JSON or register the service worker. Production PWA installation requires HTTPS; GitHub Pages supplies this.

The app uses relative links and hash navigation, so it also works under a GitHub repository subpath without route rewrites. No third-party fonts, scripts, analytics, or network services are used.

## Updating records

Edit `data.json` using verified source records. Preserve original documents and counterparty names. Add the original file, byte length and SHA-256 for any new document. Update snapshot date and source page references. Bump `CACHE` in `sw.js` whenever shipping an update so the offline shell is refreshed consistently. Run `node verify.mjs`, review all four screens, then upload changes. Never relabel a filtered export as a complete statement.

This is the public static archive requested by the owner. It has no login or access controls; published documents are downloadable by visitors. It is not connected to ING or to a lender system. No deployment has been performed by the delivery ZIP itself.

## Official setup references

- [GitHub: Configure a Pages publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Apple: Turn a website into an app in Safari on iPhone](https://support.apple.com/en-az/guide/iphone/iphea86e5236/26/ios/26)
