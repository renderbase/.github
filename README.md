<p align="center">
  <img src="https://renderbase.dev/logo.svg" alt="Renderbase" width="200" />
</p>

<h1 align="center">Renderbase</h1>

<p align="center">
  <strong>Document Infrastructure for Developers</strong><br/>
  Generate pixel-perfect PDFs and Excel files from JSON templates in milliseconds.
</p>

<p align="center">
  <a href="https://renderbase.dev">Website</a> •
  <a href="https://docs.renderbase.dev">Documentation</a> •
  <a href="https://docs.renderbase.dev/api-reference">API Reference</a> •
  <a href="https://app.renderbase.dev/signup">Get Started</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/generation-200--500ms-brightgreen" alt="Generation Speed" />
  <img src="https://img.shields.io/badge/uptime-99.9%25-blue" alt="Uptime" />
  <img src="https://img.shields.io/badge/formats-PDF%20%7C%20Excel-orange" alt="Formats" />
</p>

---

## Why Renderbase?

Traditional PDF generation is slow and fragile. HTML-to-PDF libraries require headless browsers, take 3-8 seconds per document, and produce inconsistent results.

**Renderbase is different:**

- **Sub-second generation** — 200-500ms typical (10-15x faster than HTML-to-PDF)
- **Native rendering engine** — No browser overhead, no HTML parsing
- **Yoga Layout** — Facebook's Flexbox engine (same as React Native) for pixel-perfect layouts
- **Zero XSS surface** — JSON-based TextRuns instead of HTML for rich text
- **Dual output** — PDF and Excel from the same template

## Quick Start

### REST API

```bash
curl -X POST https://api.renderbase.dev/api/v1/documents/generate \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "templateId": "invoice-template",
    "format": "pdf",
    "variables": {
      "invoiceNumber": "INV-2026-001",
      "customerName": "Acme Corp",
      "items": [
        { "description": "Consulting", "quantity": 10, "price": 150.00 }
      ],
      "total": 1500.00
    }
  }'
```

### Node.js SDK

```bash
npm install @renderbase/sdk
```

```typescript
import { Renderbase } from '@renderbase/sdk';

const client = new Renderbase({ apiKey: 'YOUR_API_KEY' });

const result = await client.documents.generate({
  templateId: 'invoice-template',
  format: 'pdf',
  variables: {
    invoiceNumber: 'INV-2026-001',
    customerName: 'Acme Corp',
    items: [{ description: 'Consulting', quantity: 10, price: 150.00 }],
    total: 1500.00
  }
});

console.log(result.downloadUrl);
```

### Python SDK

```bash
pip install renderbase
```

```python
from renderbase import RenderbaseClient

client = RenderbaseClient(api_key="YOUR_API_KEY")

result = client.documents.generate(
    template_id="invoice-template",
    format="pdf",
    variables={
        "invoiceNumber": "INV-2026-001",
        "customerName": "Acme Corp",
        "items": [{"description": "Consulting", "quantity": 10, "price": 150.00}],
        "total": 1500.00
    }
)

print(result.download_url)
```

## AI-Native Workflow (MCP)

Connect Claude, Cursor, or any MCP-compatible AI agent directly to Renderbase:

```json
{
  "mcpServers": {
    "renderbase": {
      "command": "npx",
      "args": ["-y", "@renderbase/mcp-server"],
      "env": {
        "RENDERBASE_USER_TOKEN": "your-personal-access-token"
      }
    }
  }
}
```

Then just ask: *"Create an invoice template for consulting services with VAT"*

## Features

| Feature | Description |
|---------|-------------|
| **28 Component Types** | Text, tables, charts, QR codes, barcodes, form fields, and more |
| **8 Chart Types** | Bar, line, pie, doughnut, area, radar, polar area, scatter |
| **10 Barcode Formats** | Code128, Code39, EAN-13/8, UPC-A/E, ITF-14, PDF417, DataMatrix, QR |
| **9 PDF Form Fields** | Text, textarea, checkbox, radio, dropdown, date, signature, button |
| **Hybrid Logic** | Server-side JavaScript expressions + native Excel formulas |
| **Visual Designer** | Drag-and-drop template builder with live preview |
| **Batch Generation** | Generate thousands of documents in parallel |
| **Webhooks** | Real-time notifications for document events |

## Integrations

| Platform | Package | Description |
|----------|---------|-------------|
| **Node.js** | [`@renderbase/sdk`](https://github.com/renderbase/sdk-node) | Official TypeScript SDK |
| **Python** | [`renderbase`](https://github.com/renderbase/sdk-python) | Official Python SDK |
| **Java** | [`renderbase-java`](https://github.com/renderbase/sdk-java) | Official Java SDK |
| **MCP Server** | [`@renderbase/mcp-server`](https://github.com/renderbase/mcp-server) | AI agent integration |
| **Zapier** | [Renderbase for Zapier](https://github.com/renderbase/zapier-renderbase) | No-code automation |
| **Make.com** | [Renderbase for Make](https://github.com/renderbase/make-renderbase) | Visual automation |
| **n8n** | [n8n-nodes-renderbase](https://github.com/renderbase/n8n-renderbase) | Workflow automation |
| **Google Sheets** | Add-on | Generate documents from spreadsheet data |

## Pricing

| Tier | Documents/Month | Price |
|------|-----------------|-------|
| **Free** | 50 | $0/month |
| **Starter** | 500 | $19/month |
| **Growth** | 2,500 | $49/month |
| **Scale** | 10,000 | $99/month |

[View full pricing →](https://renderbase.dev/pricing)

## Resources

- **Documentation**: [docs.renderbase.dev](https://docs.renderbase.dev)
- **API Reference**: [docs.renderbase.dev/api-reference](https://docs.renderbase.dev/api-reference)
- **Template Schema**: [docs.renderbase.dev/developer-guide/template-schema](https://docs.renderbase.dev/developer-guide/template-schema)
- **Status Page**: [status.renderbase.dev](https://status.renderbase.dev)

## LLM Context Files

For AI assistants and code generation tools:

- [`llms.txt`](https://renderbase.dev/llms.txt) — Compact overview
- [`llms-full.txt`](https://renderbase.dev/llms-full.txt) — Comprehensive reference
- [`llms-templates.txt`](https://renderbase.dev/llms-templates.txt) — Template schema for AI

## Security

- **TLS 1.3** encryption for all API calls
- **Signed URLs** with configurable expiration
- **GDPR compliant** with data removal support
- **SOC 2 Type II** certification in progress

## Support

- **Email**: support@renderbase.dev
- **Documentation**: [docs.renderbase.dev](https://docs.renderbase.dev)
- **Status**: [status.renderbase.dev](https://status.renderbase.dev)

---

<p align="center">
  <sub>Built by <a href="https://renderbase.dev">Renderbase</a> — Document Infrastructure for Developers</sub>
</p>
