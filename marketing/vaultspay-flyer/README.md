# VaultsPay Corporate Flyer

2-page marketing flyer for VaultsPay (The Vaults International Payment L.L.C.), built from `VaultsPayPaymentsSolutions060726.docx`.

- `VaultsPay-Corporate-Flyer.pdf` — print-ready PDF, US Letter (8.5in × 11in), 2 pages.
- `source.html` — the HTML/CSS source (fonts and logo embedded as data URIs, self-contained).
- `preview-page-1.png` / `preview-page-2.png` — page previews.

## Design

- Type: Space Grotesk (display), Inter (body), IBM Plex Mono (labels/data).
- Color: cobalt `#1490EB` and green `#50B83F`, taken directly from the VaultsPay logo, on an ink `#0B1B2E` / paper `#F6F7F9` base.
- Signature motif: a fanned payment-card stack on page 1, echoed by card-shaped bullet chips on page 2 — grounded in VaultsPay's actual card issuing/acquiring business.

## Regenerating

`source.html` is self-contained (no external requests). To re-export the PDF:

```
node -e "
const { chromium } = require('playwright');
(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.goto('file://' + process.cwd() + '/marketing/vaultspay-flyer/source.html');
  await page.pdf({ path: 'VaultsPay-Corporate-Flyer.pdf', printBackground: true, width: '8.5in', height: '11in', margin: {top:0,bottom:0,left:0,right:0} });
  await browser.close();
})();
"
```
