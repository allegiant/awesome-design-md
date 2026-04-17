# Vue Vben Admin Design System

[DESIGN.md](./DESIGN.md) extracted from the [vue-vben-admin](https://github.com/vbenjs/vue-vben-admin) project source code (`packages/@core/base/design/src/design-tokens/`). Every CSS variable, layout dimension, transition, and component pattern has been verified against the actual codebase.

## Files

| File | Description |
|------|-------------|
| `DESIGN.md` | Complete design system documentation (12 sections) |
| `preview.html` | Interactive design token catalog (light mode) |
| `preview-dark.html` | Interactive design token catalog (dark mode) |
| `README.md` | This file |

Use [DESIGN.md](./DESIGN.md) as a reference for AI agents (Claude, Cursor, Stitch) to generate UI that follows the Vue Vben Admin design language with Ant Design Vue.

## Key Characteristics

- **Framework**: Vue 3 + Ant Design Vue + VXE Table
- **Theme System**: 14+ switchable HSL-based theme presets via CSS variables
- **Dark Mode**: Class-based (`.dark` on `<html>`)
- **Typography**: System font stack — no custom web fonts
- **Layout**: Sidebar-driven admin layout with 5 configurable modes
- **CRUD Patterns**: Two canonical layouts — SearchForm+Table+Drawer & TreeTable+Modal

## Preview

Open `preview.html` or `preview-dark.html` in a browser for a visual catalog of all design tokens and component patterns.
