# qrcodefyi-embed

[![npm](https://img.shields.io/npm/v/qrcodefyi-embed)](https://www.npmjs.com/package/qrcodefyi-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/qrcodefyi-embed)
[![Size](https://img.shields.io/badge/size-~11--16KB_gzipped-green)](https://bundlephobia.com/package/qrcodefyi-embed)

Embed **QRCodeFYI** specification widgets — qr code types, technical standards, glossary terms, and interactive tools — on any website. **8 widget types**, zero dependencies, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and live data from the [QRCodeFYI](https://qrcodefyi.com) database.

Every widget includes a "Powered by QRCodeFYI" backlink directing readers to the full technical reference.

> **Try the interactive widget builder at [widget.qrcodefyi.com](https://widget.qrcodefyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-qrcodefyi="spec" data-slug="types" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the QRCodeFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `spec` | `<div data-qrcodefyi="spec" data-slug="..."></div>` | Technical specification card — protocol, range, data rate, standards |
| `compare` | `<div data-qrcodefyi="compare" data-slug="..."></div>` | Side-by-side comparison of two technologies or standards |
| `features` | `<div data-qrcodefyi="features" data-slug="..."></div>` | Feature list card — capabilities, supported modes, variants |
| `glossary` | `<div data-qrcodefyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `faq` | `<div data-qrcodefyi="faq" data-slug="..."></div>` | FAQ accordion for common technical questions |
| `guide` | `<div data-qrcodefyi="guide" data-slug="..."></div>` | Implementation guide — setup, code examples, best practices |
| `search` | `<div data-qrcodefyi="search" data-slug="..."></div>` | Search box linking to the full technology database |
| `qr-decoder` | `<div data-qrcodefyi="qr-decoder" data-slug="..."></div>` | Client-side QR code decoder — paste URL or data string |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-qrcodefyi` | spec, compare, features, glossary, faq, guide, search, [tools] | required | Widget type |
| `data-slug` | e.g. "types" | — | Entity slug from the QRCodeFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style` | technical, modern | technical | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search QR Code Types…" | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-qrcodefyi="spec" data-slug="types" data-theme="light"></div>

<!-- Dark -->
<div data-qrcodefyi="spec" data-slug="types" data-theme="dark"></div>

<!-- Sepia -->
<div data-qrcodefyi="spec" data-slug="types" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-qrcodefyi="spec" data-slug="types" data-theme="auto"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<qrcodefyi-spec slug="types" theme="light"></qrcodefyi-spec>
<qrcodefyi-compare slug-a="types" slug-b="other-slug"></qrcodefyi-compare>
<qrcodefyi-search placeholder="Search QR Code Types…"></qrcodefyi-search>

<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Specification Card

```html
<div data-qrcodefyi="spec" data-slug="types" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

### Side-by-Side Comparison

```html
<div data-qrcodefyi="compare" data-slug-a="types" data-slug-b="other-slug"></div>
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-qrcodefyi="search" data-placeholder="Search QR Code Types…"></div>
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-qrcodefyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/qrcodefyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install qrcodefyi-embed
```

```javascript
import 'qrcodefyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **JetBrains Mono**: Code blocks use JetBrains Mono loaded from jsDelivr
- **System fonts**: Body text uses system-ui — no extra font requests
- **CORS**: QRCodeFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Bundle size**: ~11–16KB gzipped (per-site build — only includes tools available on QRCodeFYI)

## Learn More About QR Code Types

Visit [qrcodefyi.com](https://qrcodefyi.com) — QRCodeFYI is a comprehensive qr code types technical reference with specifications, standards, interactive tools, and implementation guides.

- **API docs**: [qrcodefyi.com/developers/](https://qrcodefyi.com/developers/)
- **Widget builder**: [widget.qrcodefyi.com](https://widget.qrcodefyi.com)
- **npm package**: [npmjs.com/package/qrcodefyi-embed](https://www.npmjs.com/package/qrcodefyi-embed)
- **GitHub**: [github.com/fyipedia/qrcodefyi-embed](https://github.com/fyipedia/qrcodefyi-embed)

## Tag FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Tag FYI covers identification, tagging, and wireless communication technologies.

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| BarcodeFYI | [barcodefyi.com](https://barcodefyi.com) | Barcode formats, EAN, UPC, ISBN, QR, Code 128 standards | [npm](https://www.npmjs.com/package/barcodefyi-embed) |
| **QRCodeFYI** | [qrcodefyi.com](https://qrcodefyi.com) | QR code generation, scanning, error correction, encoding modes | **[npm](https://www.npmjs.com/package/qrcodefyi-embed)** |
| NFCFYI | [nfcfyi.com](https://nfcfyi.com) | NFC tags, NDEF records, contactless payments, ISO 14443 | [npm](https://www.npmjs.com/package/nfcfyi-embed) |
| BLEFYI | [blefyi.com](https://blefyi.com) | Bluetooth Low Energy, GATT profiles, beacons, iBeacon, Eddystone | [npm](https://www.npmjs.com/package/blefyi-embed) |
| RFIDFYI | [rfidfyi.com](https://rfidfyi.com) | RFID tags, frequency bands, EPC Gen 2, ISO 18000 standards | [npm](https://www.npmjs.com/package/rfidfyi-embed) |
| SmartCardFYI | [smartcardfyi.com](https://smartcardfyi.com) | Smart cards, EMV, APDU commands, Java Card, ISO 7816 | [npm](https://www.npmjs.com/package/smartcardfyi-embed) |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
