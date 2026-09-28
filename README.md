# QR Code Generator

A self-contained, offline QR code generator that runs entirely in the browser. No server, no API calls, no external dependencies.

## How to launch

Open index.html in any modern browser. No build steps, no install.

## How it works

1. Paste a URL or any text into the input field.
2. Click Generate QR Code or press Ctrl+Enter.
3. The QR code renders on-screen. Text, input, and buttons never move (a reserved placeholder prevents layout jumps).
4. Choose a download format (PNG, JPEG, SVG) and click Download.

Everything runs locally. The QR library (qrcode-generator v1.4.4, MIT) is embedded inline so the page runs fully offline with no network requests.

## Formats

| Format | Details |
| --- | --- |
| PNG | Canvas raster at full intrinsic resolution |
| JPEG | Same resolution, 92 percent quality |
| SVG | Vector graphic from the QR library, infinitely scalable |

## Codebase

The entire app is one file:

`index.html` contains three sections, in order:

| Section | What it does |
| --- | --- |
| **CSS** (inline styles) | Dark theme, centered layout, responsive sizing, anti-flicker wrapper |
| **HTML** (body) | Text input, generate button, format dropdown, download button, QR display area |
| **JS** (inline scripts) | UTF-8 encoder, QR generation via `qrcode-generator` v1.4.4 (MIT, embedded), canvas rendering, PNG/JPEG/SVG export |

The QR library is embedded directly in the script block so the page works fully offline. No CDN, no frameworks, no build tools.
