# Renderbase

**Document generation platform for developers.** Generate PDFs and Excel files from templates with a simple API.

## What We Build

- **Rendering Engine** - High-performance document generation with Yoga layout
- **Template Designer** - Visual editor for PDF and Excel templates
- **SDKs** - Node.js, Python, and Java libraries
- **Integrations** - Zapier, Make, n8n, Google Sheets

## Repositories

### SDKs

| SDK | Package | Description |
|-----|---------|-------------|
| [sdk-node](https://github.com/renderbase/sdk-node) | `@renderbase/sdk` | Node.js/TypeScript SDK |
| [sdk-python](https://github.com/renderbase/sdk-python) | `renderbase` | Python SDK with async support |
| [sdk-java](https://github.com/renderbase/sdk-java) | `io.renderbase:sdk` | Java SDK for JVM applications |

### Tools

| Repository | Description |
|------------|-------------|
| [mcp-server](https://github.com/renderbase/mcp-server) | Model Context Protocol server for AI assistants |
| [developer-resources](https://github.com/renderbase/developer-resources) | Sample templates, code examples, and tutorials |

### No-Code Integrations

| Repository | Description |
|------------|-------------|
| [zapier-renderbase](https://github.com/renderbase/zapier-renderbase) | Official Zapier integration |
| [make-renderbase](https://github.com/renderbase/make-renderbase) | Official Make.com (Integromat) integration |
| [n8n-renderbase](https://github.com/renderbase/n8n-renderbase) | Official n8n community node |

### Quick Links

| Resource | Link |
|----------|------|
| Documentation | [docs.renderbase.dev](https://docs.renderbase.dev) |
| Website | [renderbase.dev](https://renderbase.dev) |
| API Reference | [docs.renderbase.dev/api-reference](https://docs.renderbase.dev/api-reference) |

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
