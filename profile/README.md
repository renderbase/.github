# Renderbase

**Document generation platform for developers.** Generate PDFs and Excel files from templates with a simple API.

## What We Build

- **Rendering Engine** - High-performance document generation with Yoga layout
- **Template Designer** - Visual editor for PDF and Excel templates
- **SDKs** - Node.js, Python, and Java libraries
- **Integrations** - Zapier, Make, n8n, Google Sheets

## Quick Links

| Resource | Link |
|----------|------|
| Documentation | [docs.renderbase.dev](https://docs.renderbase.dev) |
| Website | [renderbase.dev](https://renderbase.dev) |
| Node.js SDK | [sdk-node](https://github.com/renderbase/sdk-node) |
| Python SDK | [sdk-python](https://github.com/renderbase/sdk-python) |

## Get Started

```bash
npm install @renderbase/sdk
```

```javascript
import { Renderbase } from '@renderbase/sdk';

const client = new Renderbase({ apiKey: 'your-api-key' });
const pdf = await client.documents.generatePdf({
  templateId: 'invoice-template',
  data: { customerName: 'Acme Corp', amount: 150.00 }
});
```

## Contributing

We welcome contributions! See our [Contributing Guide](https://github.com/renderbase/.github/blob/main/CONTRIBUTING.md).

## License

Our SDKs are open source under the MIT License.
