# Renderbase Brand Assets

Official logo and brand assets for Renderbase - the document generation platform.

## Logo Files

| File | Size | Use Case |
|------|------|----------|
| `icon.svg` | 64x64 | App icons, large favicons |
| `favicon.svg` | 32x32 | Browser favicons |
| `logo.svg` | 200x200 | Primary logo mark (circular) |
| `logo-horizontal.svg` | 280x60 | Headers, light backgrounds |
| `logo-horizontal-dark.svg` | 280x60 | Headers, dark backgrounds |

## Design Concept

### Symbol
- **Layered documents** - Represents templates and generated documents
- **Content lines** - Represents document structure/content
- **Clean geometric shapes** - Modern, professional look

### Color Palette

| Color | Hex | Tailwind | Usage |
|-------|-----|----------|-------|
| Violet 500 | `#8B5CF6` | `violet-500` | Primary brand color |
| Violet 600 | `#7C3AED` | `violet-600` | Gradient end (dark) |
| Violet 400 | `#A78BFA` | `violet-400` | Dark mode accent |
| Zinc 900 | `#18181B` | `zinc-900` | Light mode text |
| Zinc 50 | `#FAFAFA` | `zinc-50` | Dark mode text |

### Gradient
```css
/* Light mode */
background: linear-gradient(135deg, #8B5CF6 0%, #7C3AED 100%);

/* Dark mode */
background: linear-gradient(135deg, #A78BFA 0%, #8B5CF6 100%);
```

## Usage Guidelines

### Do
- Use SVG format for web (scalable, small file size)
- Maintain aspect ratio when scaling
- Use appropriate variant for background color
- Provide adequate spacing around logo (min 16px)

### Don't
- Stretch or distort the logo
- Change the gradient colors
- Add effects (shadows, glows)
- Place on busy/conflicting backgrounds
- Use low-resolution raster versions for large displays

## Implementation

### HTML
```html
<!-- Favicon -->
<link rel="icon" href="/favicon.svg" type="image/svg+xml">

<!-- Header logo -->
<img src="/logo-horizontal.svg" alt="Renderbase" width="280" height="60">

<!-- Dark mode -->
<picture>
  <source srcset="/logo-horizontal-dark.svg" media="(prefers-color-scheme: dark)">
  <img src="/logo-horizontal.svg" alt="Renderbase" width="280" height="60">
</picture>
```

### React/Next.js
```tsx
import Image from 'next/image';

// With theme detection
const { theme } = useTheme();
const logoSrc = theme === 'dark'
  ? '/logo-horizontal-dark.svg'
  : '/logo-horizontal.svg';

<Image src={logoSrc} alt="Renderbase" width={280} height={60} />
```

## Converting to Other Formats

### PNG (using ImageMagick)
```bash
# 512x512 PNG
convert -background none -density 300 logo.svg -resize 512x512 logo-512.png

# Favicon sizes
convert -background none favicon.svg -resize 16x16 favicon-16.png
convert -background none favicon.svg -resize 32x32 favicon-32.png
```

### ICO (Windows favicon)
```bash
convert favicon.svg -define icon:auto-resize=16,32,48,64 favicon.ico
```

### Apple Touch Icon
```bash
convert -background none -density 300 icon.svg -resize 180x180 apple-touch-icon.png
```

## File Locations by App

Copy these assets to the appropriate locations:

| App | Location | Files |
|-----|----------|-------|
| website | `public/` | All |
| webapp | `public/` | All |
| admin | `public/` | All |
| docs | `static/img/` | All |
| wiki | `static/img/` | All |
| n8n | `nodes/Renderbase/` | `icon.svg` → `renderbase.svg` |
| zapier | (upload to platform) | `icon.svg` |
| make | (upload to platform) | `icon.svg` |

---

**Version**: 2.0
**Updated**: January 2026
**Design**: Minimal/Geometric
**Primary Color**: Violet (#8B5CF6)
