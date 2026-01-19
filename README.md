<div align="center">
  <h1>Sanity Lucide Icon Picker (Sanity v4 compatibility)</h1>
  <h3>A Lucide icon picker plugin for Sanity Studio v4 with 1,600+ icons.</h3>
  <p><em>Fork maintained by @fredcorr</em></p>

  <img src="https://img.shields.io/npm/v/@fredcorr/sanity-plugin-lucide-icon-picker" alt="npm version" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Sanity-F03E2F?logo=sanity&logoColor=white" alt="Sanity" />
  <img src="https://img.shields.io/npm/l/@fredcorr/sanity-plugin-lucide-icon-picker?style&color=5D6D7E" alt="MIT License" />

  <br>
  <br>

  <img src="demo.gif" alt="Sanity Lucide Icon Picker Preview" />
</div>

---

## Features

- **1,600+ icons**: Access to the complete Lucide Icons library
- **Smart search**: Quickly find icons with intelligent search functionality
- **Responsive design**: Works seamlessly on desktop and mobile devices
- **High performance**: Virtualized rendering and lazy loading for smooth experience
- **Configurable**: Flexible options for filtering icons
- **Preview support**: Built-in preview function for Sanity Studio

---

## Compatibility Update

This fork is a dependency-compatibility update only:

- Updated peer dependencies for Sanity Studio v4 and @sanity/ui v3
- No functional changes intended

---

## Personal Use

This fork is intended for personal use only and is not published to npm.

---

## Installation

```sh
pnpm add @fredcorr/sanity-plugin-lucide-icon-picker
# or
yarn add @fredcorr/sanity-plugin-lucide-icon-picker
# or
npm install @fredcorr/sanity-plugin-lucide-icon-picker
```

---

## Usage

**1. Add the plugin to your Sanity config:**

```ts
// sanity.config.ts
import { defineConfig } from 'sanity';
import { lucideIconPicker } from '@fredcorr/sanity-plugin-lucide-icon-picker';

export default defineConfig({
  // ...
  plugins: [lucideIconPicker()],
});
```

**2. Use the `lucide-icon` type in your schema:**

```ts
// schemas/myDocument.ts
import { defineType } from 'sanity';

export default defineType({
  name: 'myDocument',
  title: 'My Document',
  type: 'document',
  fields: [
    {
      name: 'icon',
      title: 'Icon',
      type: 'lucide-icon',
    },
    // ... other fields
  ],
});
```

---

## Configuration Options

### Icon Filtering

Limit available icons to a specific whitelist:

```ts
{
  name: 'icon',
  title: 'Social Icon',
  type: 'lucide-icon',
  options: {
    allowedIcons: ['facebook', 'twitter', 'instagram', 'linkedin'],
  }
}
```

The `allowedIcons` option accepts an array of icon names (in kebab-case format) to show only those specific icons in the picker.

---

## Frontend Integration

### React with DynamicIcon

Icons are stored as kebab-case strings (e.g., `"arrow-right"`, `"chevron-down"`). Use Lucide's `DynamicIcon` component to render them:

```jsx
import { DynamicIcon } from 'lucide-react/dynamic';

// Your Sanity data
const iconName = 'arrow-right'; // from your Sanity document

// Usage
export default function MyComponent() {
  return (
    <div>
      <DynamicIcon name={iconName} size={24} />
    </div>
  );
}
```

---

## Performance

The plugin is optimized for performance with:

- **Virtualized rendering** - Only visible icons are rendered
- **Lazy loading** - Icons load on-demand
- **Efficient search** - Fast text-based search with debouncing
- **Tree shaking** - Only imported icons are included in your bundle

For optimal frontend performance:

1. Use dynamic imports to load only needed icons
2. Consider using the `allowedIcons` option to limit available icons

---

## Requirements

- Sanity Studio v4
- @sanity/ui v3
- React 18
- styled-components 6.1
- TypeScript (recommended)

---

## License

MIT © ContentWrap

---

## Fork Notes

This package is a fork of the original plugin by [ContentWrap](https://contentwrap.io). It only updates dependencies to support Sanity Studio v4 and @sanity/ui v3.
