# DESIGN.md — Vue Vben Admin

> Enterprise-grade admin dashboard framework built on Vue 3 + Ant Design Vue.
> Clean, data-dense, multi-theme, production-ready.

---

## 1. Visual Theme & Atmosphere

| Attribute        | Value                                                                 |
| ---------------- | --------------------------------------------------------------------- |
| **Mood**         | Professional, efficient, trustworthy — enterprise admin dashboard     |
| **Density**      | Medium-high; data-dense tables, compact forms, efficient layouts      |
| **Philosophy**   | Functional minimalism — every pixel serves the user's workflow        |
| **Light mode**   | Clean white surfaces with cool gray-blue content areas                |
| **Dark mode**    | Deep charcoal-navy surfaces with subtle elevation                     |
| **Personality**  | Quietly authoritative; UI recedes so content leads                    |

### Design Principles

- **Content-first**: Chrome stays minimal; data tables, forms, and dashboards dominate
- **Multi-theme**: 14+ built-in theme presets — always honor the active theme's token overrides
- **Component-library-native**: Build with Ant Design Vue components; never reinvent what the library provides
- **Responsive admin**: Sidebar-driven desktop layouts that collapse gracefully on mobile

---

## 2. Color Palette & Roles

All colors use **HSL format** and are applied via CSS custom properties on `:root` / `.dark`.

### Default Theme (Blue)

| Token                    | Light Mode HSL              | Hex (approx.)   | Role                                      |
| ------------------------ | --------------------------- | ---------------- | ----------------------------------------- |
| `--primary`              | `212 100% 45%`              | `#0066E6`        | Primary actions, links, active states      |
| `--primary-foreground`   | `0 0% 98%`                  | `#FAFAFA`        | Text on primary surfaces                   |
| `--destructive`          | `359.33 100% 65.1%`         | `#FF4D4F`        | Delete, error, danger actions              |
| `--destructive-foreground`| `0 0% 98%`                 | `#FAFAFA`        | Text on destructive surfaces               |
| `--success`              | `144 57% 58%`               | `#57D188`        | Success states, confirmations              |
| `--success-foreground`   | `0 0% 98%`                  | `#FAFAFA`        | Text on success surfaces                   |
| `--warning`              | `42 84% 61%`                | `#FAAD14`        | Warnings, attention states                 |
| `--warning-foreground`   | `0 0% 98%`                  | `#FAFAFA`        | Text on warning surfaces                   |
| `--background`           | `0 0% 100%`                 | `#FFFFFF`        | Page body / shell background               |
| `--background-deep`      | `216 20.11% 95.47%`         | `#EEF1F6`        | Content area background                    |
| `--foreground`           | `210 6% 21%`                | `#323233`        | Default body text                          |
| `--card`                 | `0 0% 100%`                 | `#FFFFFF`        | Card / panel surfaces                      |
| `--card-foreground`      | `222.2 84% 4.9%`            | `#020817`        | Card text                                  |
| `--popover`              | `0 0% 100%`                 | `#FFFFFF`        | Dropdown, tooltip surfaces                 |
| `--popover-foreground`   | `222.2 84% 4.9%`            | `#020817`        | Popover text                               |
| `--muted`                | `240 4.8% 95.9%`            | `#F4F4F5`        | Tabs list, skeleton, disabled backgrounds  |
| `--muted-foreground`     | `240 3.8% 46.1%`            | `#71717A`        | Placeholder, secondary text                |
| `--secondary`            | `240 5% 96%`                | `#F4F4F6`        | Secondary button background                |
| `--secondary-foreground` | `240 6% 10%`                | `#18181B`        | Secondary button text                      |
| `--accent`               | `240 5% 96%`                | `#F4F4F6`        | Hover highlights on menu items             |
| `--accent-foreground`    | `240 6% 10%`                | `#18181B`        | Accent text                                |
| `--accent-hover`         | `200 10% 90%`               | `#E0E7EC`        | Stronger hover highlight                   |
| `--accent-dark`          | `216 14% 93%`               | `#EAEDF2`        | Darker accent variant                      |
| `--accent-darker`        | `216 11% 91%`               | `#E3E6EB`        | Darkest accent variant                     |
| `--accent-lighter`       | `240 0% 98%`                | `#FAFAFA`        | Lighter accent variant                     |
| `--heavy`                | `192 9.43% 89.61%`          | `#DDE5E5`        | Heavy / darker accent for separators       |
| `--heavy-foreground`     | `= --accent-foreground`     | —                | Text on heavy surfaces                     |
| `--border`               | `240 5.9% 90%`              | `#E4E4E7`        | Default borders                            |
| `--input`                | `240 5.88% 90%`             | `#E4E4E7`        | Input field borders                        |
| `--input-placeholder`    | `217 10.6% 65%`             | `#9CA3AF`        | Input placeholder text                     |
| `--input-background`     | `0 0% 100%`                 | `#FFFFFF`        | Input field background                     |
| `--ring`                 | `222.2 84% 4.9%`            | `#020817`        | Focus ring                                 |
| `--info`                 | `240 5% 96%`                | `#F4F4F6`        | Info state background                      |
| `--info-foreground`      | `220 4% 58%`                | `#8E9196`        | Info state text                            |
| `--sidebar`              | `0 0% 100%`                 | `#FFFFFF`        | Sidebar background                         |
| `--sidebar-deep`         | `0 0% 100%`                 | `#FFFFFF`        | Sidebar deep / secondary background        |
| `--menu`                 | `= --sidebar`               | —                | Menu background (alias for sidebar)        |
| `--header`               | `0 0% 100%`                 | `#FFFFFF`        | Header background                          |
| `--overlay`              | `0 0% 0% / 45%`             | —                | Modal overlay                              |
| `--overlay-content`      | `0 0% 95% / 45%`            | —                | Content area loading overlay               |

### Dark Mode (Default Theme)

| Token                    | Dark Mode HSL               | Hex (approx.)   | Notes                                     |
| ------------------------ | --------------------------- | ---------------- | ----------------------------------------- |
| `--background`           | `222.34 10.43% 12.27%`      | `#1C1F26`        | Dark shell background                     |
| `--background-deep`      | `220 13.06% 9%`             | `#141619`        | Dark content area                         |
| `--foreground`           | `0 0% 95%`                  | `#F2F2F2`        | Primary text on dark                      |
| `--card`                 | `222.34 10.43% 12.27%`      | `#1C1F26`        | Card surface (matches background)         |
| `--popover`              | `0 0% 14.2%`                | `#242424`        | Popover — slightly lighter than card      |
| `--muted`                | `240 3.7% 15.9%`            | `#272729`        | Muted surface                             |
| `--muted-foreground`     | `240 5% 64.9%`              | `#A1A1AA`        | Secondary text                            |
| `--secondary`            | `240 5% 17%`                | `#2A2A2D`        | Secondary button bg                       |
| `--secondary-foreground` | `0 0% 98%`                  | `#FAFAFA`        | Secondary button text                     |
| `--accent`               | `216 5% 19%`                | `#2E3035`        | Accent / hover highlight                  |
| `--accent-foreground`    | `0 0% 98%`                  | `#FAFAFA`        | Accent text                               |
| `--accent-hover`         | `216 5% 24%`                | `#3A3D40`        | Hover highlight                           |
| `--accent-dark`          | `240 0% 22%`                | `#383838`        | Darker accent variant                     |
| `--accent-darker`        | `240 0% 26%`                | `#424242`        | Darkest accent variant                    |
| `--accent-lighter`       | `216 5% 12%`                | `#1D1F22`        | Lighter accent variant                    |
| `--heavy`                | `216 5% 24%`                | `#3A3D40`        | Heavy / darker accent for separators      |
| `--heavy-foreground`     | `= --accent-foreground`     | —                | Text on heavy surfaces                    |
| `--border`               | `240 3.7% 22%`              | `#363639`        | Borders                                   |
| `--input`                | `0 0% 100% / 10%`           | —                | Input borders (translucent)               |
| `--input-placeholder`    | `218 11% 65%`               | `#9CA3AF`        | Input placeholder text                    |
| `--input-background`     | `0 0% 100% / 5%`            | —                | Input bg (translucent)                    |
| `--ring`                 | `222.2 84% 4.9%`            | `#020817`        | Focus ring                                |
| `--info`                 | `180 1.54% 12.75%`          | `#1F2121`        | Info state background                     |
| `--info-foreground`      | `220 4% 58%`                | `#8E9196`        | Info state text                           |
| `--destructive`          | `359.21 68.47% 56.47%`      | `#D94650`        | Softer red for dark mode                  |
| `--card-foreground`      | `210 40% 98%`               | `#F8FAFC`        | Card text (lighter for dark)              |
| `--popover-foreground`   | `210 40% 98%`               | `#F8FAFC`        | Popover text                              |
| `--sidebar`              | `222.34 10.43% 12.27%`      | `#1C1F26`        | Sidebar                                   |
| `--sidebar-deep`         | `220 13.06% 9%`             | `#141619`        | Sidebar deep background                   |
| `--menu`                 | `= --sidebar`               | —                | Menu background (alias for sidebar)       |
| `--header`               | `222.34 10.43% 12.27%`      | `#1C1F26`        | Header                                    |
| `--overlay`              | `0 0% 0% / 40%`             | —                | Modal overlay (slightly less opaque)      |
| `--overlay-content`      | `0 0% 0% / 40%`             | —                | Content area loading overlay              |

### Built-in Theme Presets

The system ships with 14+ switchable theme presets. Each overrides `--primary` and related tokens:

| Theme        | Primary Color HSL        | Visual Character                        |
| ------------ | ------------------------ | --------------------------------------- |
| `default`    | `212 100% 45%`           | Professional blue                       |
| `violet`     | `245 82% 67%`            | Playful purple                          |
| `pink`       | `347 77% 60%`            | Warm pink                               |
| `yellow`     | `42 84% 61%`             | Energetic amber                         |
| `sky-blue`   | `231 98% 65%`            | Bright sky blue                         |
| `green`      | `161 90% 43%`            | Fresh green                             |
| `zinc`       | `240 5% 26%`             | Neutral zinc                            |
| `deep-green` | `181 84% 32%`            | Teal / deep green                       |
| `deep-blue`  | `211 91% 39%`            | Navy blue                               |
| `orange`     | `18 89% 40%`             | Bold orange                             |
| `rose`       | `0 75% 42%`              | Classic rose                            |
| `neutral`    | `0 0% 25%`               | Pure neutral                            |
| `slate`      | `215 25% 27%`            | Cool slate                              |
| `gray`       | `217 19% 27%`            | Warm gray                               |
| `custom`     | User-defined             | Fully custom via preferences            |

---

## 3. Typography Rules

### Font Stack

```
--font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
  'Helvetica Neue', Arial, 'Noto Sans', sans-serif,
  'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
```

No custom web font — relies on system font stack for maximum performance and native feel.

### Type Scale

| Element                    | Size                          | Weight | Notes                                 |
| -------------------------- | ----------------------------- | ------ | ------------------------------------- |
| **Base font size**         | `var(--font-size-base)` 16px  | 400    | CSS variable, configurable            |
| **Menu items**             | `calc(base × 0.875)` = 14px  | 400    | Sidebar & top navigation              |
| **Page title (h1)**        | 20px                          | 600    | Card/page section headers             |
| **Section heading (h2)**   | 16px                          | 600    | Sub-section titles                    |
| **Body text**              | 14px                          | 400    | Table cells, form labels, descriptions|
| **Caption / helper**       | 12px                          | 400    | Timestamps, tooltips, help text       |
| **Data value (large)**     | 24–30px                       | 600    | Dashboard stat numbers                |

### Typography Rules

- **No decorative fonts** — readability is paramount in admin UIs
- Use `font-weight: 600` for emphasis, never heavier
- Line height: default `1.5715` (Ant Design Vue default)
- Letter spacing: normal — never increase for body text
- Monospace for code snippets: `'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, monospace`

---

## 4. Component Stylings

All components are from **Ant Design Vue** — do NOT create custom replacements. Customize via theme tokens and CSS variables.

### Buttons

| Variant        | Background                      | Text                  | Border          | Radius           |
| -------------- | ------------------------------- | --------------------- | --------------- | ---------------- |
| Primary        | `hsl(var(--primary))`           | `--primary-foreground`| none            | `var(--radius)`  |
| Default        | `transparent`                   | `--foreground`        | `--border`      | `var(--radius)`  |
| Dashed         | `transparent`                   | `--foreground`        | dashed `--border`| `var(--radius)` |
| Text           | `transparent`                   | `--foreground`        | none            | `var(--radius)`  |
| Link           | `transparent`                   | `--primary`           | none            | 0                |
| Destructive    | `hsl(var(--destructive))`       | `--destructive-fg`    | none            | `var(--radius)`  |

**States:**
- Hover: lighten 10% via Ant Design's built-in color algorithm
- Active: darken 10%
- Disabled: `opacity: 0.65`, cursor not-allowed
- Loading: spinner icon, disabled state

### Cards

```
Background:   hsl(var(--card))
Foreground:   hsl(var(--card-foreground))
Border:       1px solid hsl(var(--border))
Border-radius: var(--radius) = 0.5rem
Shadow:       none (flat by default)
Padding:      24px
```

- Cards stack vertically with `16px` gap in content area
- Cards sit on top of `--background-deep` (the slightly tinted content area)

### Inputs

```
Background:   hsl(var(--input-background))
Border:       1px solid hsl(var(--input))
Border-radius: var(--radius)
Height:       32px (default Ant Design)
Placeholder:  hsl(var(--input-placeholder))
Focus ring:   primary color glow (2px spread)
```

- Error state: border color → `hsl(var(--destructive))`
- Error focus: box-shadow `0 0 0 2px rgba(255, 38, 5, 6%)`

### Tables (Ant Design Table)

- Header: `--muted` background, `--muted-foreground` text, `font-weight: 600`
- Rows: alternating with subtle `--accent` tint on hover
- Borders: horizontal dividers using `--border`
- Dense mode available via compact table prop
- Pagination at bottom-right

### Navigation & Sidebar

```
Sidebar width:        210px (expanded) / 48px (collapsed)
Sidebar background:   hsl(var(--sidebar))
Sidebar deep bg:      hsl(var(--sidebar-deep))
Menu background:      hsl(var(--menu))  (alias for --sidebar)
Menu item height:     40px
Active menu item:     Primary color text + tinted background
Menu font size:       var(--menu-font-size) = 14px
Navigation style:     'rounded' (default), supports accordion
```

- Sidebar supports drag-resize
- Expand-on-hover when collapsed
- Split navigation: top-level in sidebar, sub-menus in sub-sidebar

### Header

```
Height:      48px
Background:  hsl(var(--header))
Position:    fixed (default)
Contains:    Breadcrumb, global search, theme toggle, user avatar, notifications
```

### Tabbar

```
Height:        30px
Style:         'chrome' tabs (default)
Features:      Draggable, scrollable, persist, show icons
Max tabs:      Unlimited (scrollable)
```

### Modal / Drawer

- Background: `hsl(var(--popover))` or `hsl(var(--card))`
- Overlay: `hsl(var(--overlay))` — `rgba(0,0,0,0.45)`
- Dark mode border: `1px solid hsl(var(--border) / 60%)`
- Standard Ant Design Vue Modal and Drawer — no custom wrappers

### Notifications & Messages

- Message: Ant Design Vue `message` API
- Notification: Bottom-right placement by default
- Dark mode: adds subtle border `hsl(var(--border) / 60%)`

---

## 5. Layout Principles

### Spacing Scale

| Token   | Value  | Usage                                     |
| ------- | ------ | ----------------------------------------- |
| `xs`    | 4px    | Tight internal padding                    |
| `sm`    | 8px    | Icon-to-text gap, compact padding         |
| `md`    | 16px   | Default spacing between elements          |
| `lg`    | 24px   | Card padding, section separation          |
| `xl`    | 32px   | Major section breaks                      |
| `2xl`   | 48px   | Page-level vertical spacing               |

### Layout Structure

```
┌──────────────────────────────────────────────┐
│  Header (50px, fixed)                        │
├──────┬───────────────────────────────────────┤
│      │  Tabbar (38px, optional)              │
│ Side │───────────────────────────────────────│
│ bar  │                                       │
│      │  Content Area                         │
│ 224px│  (background-deep, scrollable)        │
│      │                                       │
│      │  ┌─────────────────────────────────┐  │
│      │  │  Cards / Tables / Forms         │  │
│      │  │  (white/card bg, rounded)       │  │
│      │  └─────────────────────────────────┘  │
│      │                                       │
├──────┴───────────────────────────────────────┤
│  Footer (32px, optional, hidden by default)  │
└──────────────────────────────────────────────┘
```

### Layout Modes

| Mode | Value | Description |
|------|-------|-------------|
| Sidebar Nav | `sidebar-nav` | Classic sidebar (default) |
| Header Nav | `header-nav` | Full horizontal navigation |
| Mixed Nav | `mixed-nav` | Top-level nav in header, sub-nav in sidebar |
| Sidebar Mixed | `sidebar-mixed-nav` | Sidebar with mixed sub-menus |
| Full Content | `full-content` | No sidebar, no header |

### Content Area

- Content padding: configurable (default `16px` — all sides)
- Content compact: `wide` mode (max-width 1200px) or fluid
- Scroll: vertical scroll within content area
- Page transitions: `fade-slide` animation with configurable duration

### Page-Level Layout Patterns

The system defines two canonical CRUD page layouts. Choose the appropriate pattern based on data shape and form complexity.

#### Pattern A: SearchForm + Table + Drawer (Recommended Default)

Best for: flat/paged data with many searchable fields and complex edit forms (e.g. role management, user management).

```
┌─────────────────────────────────────────────────┐
│ Page (auto-content-height)                      │
│ ┌─────────────────────────────────────────────┐ │
│ │ bg-card, rounded-md, h-full                 │ │
│ │                                             │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Search Form (collapsible, 3-col grid)   │ │ │
│ │ │ submitOnChange: true                    │ │ │
│ │ │ showCollapseButton: true                │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ │ ═══════════ separator (bg-deep) ══════════  │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Toolbar                                 │ │ │
│ │ │ [Title]          [＋Create] [🔍] [↻] [⛶]│ │ │
│ │ ├─────────────────────────────────────────┤ │ │
│ │ │ Table (height: auto, paged)             │ │ │
│ │ │ status: CellSwitch + confirm dialog     │ │ │
│ │ │ ops: CellOperation (edit, delete)       │ │ │
│ │ ├─────────────────────────────────────────┤ │ │
│ │ │ Pagination                              │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ └─────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────┘
         ← Drawer (side panel for create/edit)
```

**Key configuration:**

```ts
// Grid setup
useVbenVxeGrid({
  formOptions: {
    schema: useGridFormSchema(),
    submitOnChange: true, // Auto-submit; set false to show Search/Reset buttons
    fieldMappingTime: [['createTime', ['startTime', 'endTime']]],
  },
  gridOptions: {
    height: 'auto',
    toolbarConfig: {
      custom: true, refresh: true, search: true, zoom: true,
    },
    proxyConfig: {
      ajax: {
        query: async ({ page }, formValues) => { /* paged API */ },
      },
    },
  },
});

// Drawer for edit form
const [FormDrawer, formDrawerApi] = useVbenDrawer({
  connectedComponent: Form,
  destroyOnClose: true,
});
```

> **`submitOnChange` mode:** When `true`, the search form auto-submits on every field change — no Search/Reset buttons are rendered. When `false` (or omitted), a manual Search/Reset button pair appears. The preview demos show the manual-button variant for visual completeness.

**When to use Drawer vs Modal:**
- **Drawer**: Form has many fields, embedded trees/complex components, or needs vertical scroll space
- **Modal**: Simple forms with ≤5 fields and no nested components

#### Pattern B: TreeTable + Modal (No Search)

Best for: hierarchical/tree-structured data that is loaded in full without pagination (e.g. dept management, menu management).

```
┌─────────────────────────────────────────────────┐
│ Page (auto-content-height)                      │
│ ┌─────────────────────────────────────────────┐ │
│ │ bg-card, rounded-md, h-full                 │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Toolbar (no search form)                │ │ │
│ │ │ [Title]              [＋Create] [↻] [⛶] │ │ │
│ │ ├─────────────────────────────────────────┤ │ │
│ │ │ TreeTable (height: auto, no pager)      │ │ │
│ │ │ treeNode on name column                 │ │ │
│ │ │ status: CellTag (read-only)             │ │ │
│ │ │ ops: CellOperation (append, edit, del)  │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ └─────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────┘
         Modal (centered dialog for create/edit)
```

**Key configuration:**

```ts
useVbenVxeGrid({
  // No formOptions — no search form
  gridOptions: {
    height: 'auto',
    pagerConfig: { enabled: false },
    treeConfig: {
      parentField: 'pid', rowField: 'id', transform: false,
    },
    toolbarConfig: {
      custom: true, refresh: true, zoom: true,
      // No search: true — no search toggle button
    },
    proxyConfig: {
      ajax: { query: async () => await getFullTreeList() },
    },
  },
});

// Modal for edit form
const [FormModal, formModalApi] = useVbenModal({
  connectedComponent: Form,
  destroyOnClose: true,
});
```

**TreeTable-specific operations:**
- "Append child" action: opens form with `pid` pre-filled from parent row
- Delete disabled when `row.children.length > 0`

#### Shared Conventions (Both Patterns)

| Convention | Detail |
|---|---|
| **Page wrapper** | Always `<Page auto-content-height>` for full-height content |
| **Grid container** | `bg-card rounded-md h-full` with `p-2` internal padding |
| **Table height** | `height: 'auto'` — adapts to available space |
| **Toolbar left** | `table-title` prop/slot for bold title text |
| **Toolbar right** | `#toolbar-tools` slot for primary action button (e.g., Create) |
| **Create button** | `<Button type="primary">` with `<Plus>` icon prefix |
| **Action column** | `CellOperation` renderer, `fixed: 'right'`, `align: 'center'` |
| **Status column** | `CellTag` (read-only) or `CellSwitch` (interactive with `beforeChange`) |
| **Form submission** | `onConfirm` handler: validate → lock → API call → close + emit `success` |
| **Refresh** | Parent listens `@success` → calls `gridApi.query()` |
| **Delete feedback** | `message.loading` → API → `message.success` / catch → hide loading |

---

## 6. Depth & Elevation

Vben Admin uses a **flat design** approach — elevation is minimized.

| Level     | Usage                          | Treatment                                  |
| --------- | ------------------------------ | ------------------------------------------ |
| Level 0   | Content area                   | `--background-deep`, no shadow             |
| Level 1   | Cards, panels                  | `--card` bg, no shadow, optional border    |
| Level 2   | Floating menus, dropdowns      | `--popover` bg, system shadow (Ant Design) |
| Level 3   | Modals, drawers                | Overlay + centered surface                 |
| Level 4   | Notifications, toasts          | Ant Design default shadows                 |

### Z-Index System

```
--popup-z-index: 2000    (base for all overlays)
Ant Design defaults:      Dropdown: 1050, Modal: 1000, Popover: 1030
Vben app z-index:         200 (configurable)
```

---

## 7. Do's and Don'ts

### ✅ Do

- Use Ant Design Vue components exclusively — `a-button`, `a-table`, `a-form`, `a-modal`, etc.
- Reference CSS variables via `hsl(var(--token-name))` syntax
- Support both light and dark mode — test both
- Keep data tables scannable: left-align text, right-align numbers
- Use `--primary` for actionable elements, `--destructive` only for danger actions
- Follow the sidebar + content area layout pattern
- Use breadcrumbs for deep navigation
- Use Ant Design's `message` and `notification` APIs — never custom toasts
- Honor the active theme preset — colors are dynamic, never hardcode hex values

### ❌ Don't

- Don't use raw hex/RGB colors — always use CSS variables
- Don't create custom button/input/select components — use Ant Design Vue
- Don't add heavy shadows or drop-shadows — keep the flat aesthetic
- Don't use decorative fonts, gradients on surfaces, or heavy animations
- Don't nest modals inside drawers or vice versa
- Don't use more than 2 levels of visual hierarchy in a single view
- Don't forget the `dark` class toggle on `<html>` — dark mode is class-based
- Don't put page-level padding on the content area (it's configurable to `0` by default)
- Don't bypass the sidebar navigation — all routes go through the menu system

---

## 8. Responsive Behavior

### Breakpoints

| Breakpoint | Width    | Behavior                                    |
| ---------- | -------- | ------------------------------------------- |
| Desktop    | ≥1200px  | Full sidebar + header + tabbar              |
| Tablet     | 768–1199 | Sidebar collapsed (60px), expandable        |
| Mobile     | <768px   | Sidebar hidden, hamburger toggle, no tabbar |

### Mobile Adaptations

- Sidebar becomes a slide-out drawer
- Tabbar hidden on mobile
- Tables switch to responsive card layout
- Content padding adjusts automatically
- Touch targets ≥ 44px minimum

### Sidebar Collapse Behavior

```
Expanded width:  210px
Collapsed width: 48px (icons only)
Mixed mode width: 80px
Extra collapsed: 48px
Expand on hover: true (configurable)
Drag to resize:  true (configurable)
```

---

## 9. Agent Prompt Guide

### Quick Color Reference

```
Primary:      hsl(212 100% 45%)     — #0066E6
Success:      hsl(144 57% 58%)      — #57D188
Warning:      hsl(42 84% 61%)       — #FAAD14
Destructive:  hsl(359.33 100% 65.1%) — #FF4D4F
Background:   hsl(0 0% 100%)        — #FFFFFF (light)
Background:   hsl(222.34 10.43% 12.27%) — #1C1F26 (dark)
Content area: hsl(216 20.11% 95.47%) — #EEF1F6 (light)
Content area: hsl(220 13.06% 9%)    — #141619 (dark)
Border:       hsl(240 5.9% 90%)     — #E4E4E7  (light)
Border:       hsl(240 3.7% 22%)     — #363639  (dark)
```

### Ready-to-Use Prompts

**"Build a user list page"**
> Create an Ant Design Vue page with a Table component showing user data (name, email, role, status, created date). Add a search bar above the table using a-form with inline layout. Include action column with Edit and Delete buttons. Use a-card wrapper with no extra padding. Primary action button for "Add User" positioned at top-right of the card header.

**"Create a settings form"**
> Build a form using Ant Design Vue's a-form component with vertical label layout inside an a-card. Include text inputs, select dropdowns, switches, and a date picker. Use horizontal a-form-item with label-col span of 6. Add Primary submit button and Default cancel button at the bottom-right. All form validation using Ant Design's built-in rules.

**"Build a dashboard analytics page"**
> Create a dashboard with stat cards (4 columns grid) at the top showing key metrics using a-statistic components in a-card containers. Below add two side-by-side a-card panels for charts. Use the content area's background-deep color as the page background. Cards use the --card color. Keep spacing at 16px between cards.

**"Add a CRUD modal"**
> Use Ant Design Vue's a-modal with title, form fields inside, and footer with Cancel (Default button) and Submit (Primary button). Form uses a-form with model binding. Modal width 520px. Close on mask click disabled. Keyboard ESC to close enabled.

**"Build a searchable list page with Drawer form" (Pattern A)**
> Use `<Page auto-content-height>` wrapping a `useVbenVxeGrid` with `formOptions` (collapsible search form, `submitOnChange: true`, 3-column grid layout). Table columns include a status column with `CellSwitch` (interactive toggle + confirm dialog), an action column with `CellOperation` (edit, delete), and standard data columns. Toolbar: left = table title, right = primary "Create" button with Plus icon + built-in refresh/zoom/search-toggle buttons. Edit/create uses `useVbenDrawer` with `destroyOnClose: true`. Drawer form includes `onConfirm` with validate → lock → API call → close + emit `success` pattern. Pagination enabled.

**"Build a tree management page with Modal form" (Pattern B)**
> Use `<Page auto-content-height>` wrapping a `useVbenVxeGrid` with NO `formOptions`. Configure `treeConfig` with `parentField`/`rowField`, `pagerConfig: { enabled: false }`. Name column uses `treeNode: true` + `fixed: 'left'`. Action column uses `CellOperation` with "append" (add child), "edit", and "delete" (disabled when has children). Toolbar: left = table title, right = primary "Create" button + refresh/zoom. Edit/create uses `useVbenModal` with `destroyOnClose: true`. "Append" action pre-fills `pid` from parent row. Status displayed as read-only `CellTag`.

### Component Library Reference

Always use these Ant Design Vue components:

| Purpose            | Component                                              |
| ------------------ | ------------------------------------------------------ |
| Button             | `a-button` with `type="primary"` / `type="default"`   |
| Table              | `a-table` with `a-table-column`                        |
| Form               | `a-form` + `a-form-item`                               |
| Input              | `a-input`, `a-input-number`, `a-textarea`              |
| Select             | `a-select` + `a-select-option`                         |
| Date Picker        | `a-date-picker`, `a-range-picker`                      |
| Modal              | `a-modal`                                              |
| Drawer             | `a-drawer`                                             |
| Card               | `a-card`                                               |
| Tabs               | `a-tabs` + `a-tab-pane`                                |
| Dropdown           | `a-dropdown` + `a-menu`                                |
| Message            | `message.success()` / `message.error()`                |
| Notification       | `notification.success()`                               |
| Tag                | `a-tag`                                                |
| Badge              | `a-badge`                                              |
| Switch             | `a-switch`                                             |
| Tree / Tree Select | `a-tree`, `a-tree-select`                              |
| Upload             | `a-upload`                                             |
| Pagination         | Built into `a-table`                                   |

### CSS Variable Usage Pattern

```css
/* Always use the HSL variable pattern */
.my-element {
  background: hsl(var(--card));
  color: hsl(var(--card-foreground));
  border: 1px solid hsl(var(--border));
  border-radius: var(--radius);
}

/* For overlays and transparency */
.my-overlay {
  background: hsl(var(--overlay));
}

/* For primary-colored elements */
.my-highlight {
  color: hsl(var(--primary));
}
```

---

## 10. Iconography

- **Icon library**: `@iconify/vue` with `@vben/icons` wrapper
- **Icon size**: 16px inline, 20px for button icons, 24px for standalone
- **Icon weight**: Regular (not filled) unless indicating active state
- **Color**: Inherits from parent text color via `currentColor`
- **Menu icons**: Always include — sidebar navigation items require icons

---

## 11. Transitions & Animations

### Page & Route Transitions

| Animation          | Duration | Easing                                  | Usage                     |
| ------------------ | -------- | --------------------------------------- | ------------------------- |
| `fade-slide`       | 300ms    | Default                                 | Content entrance (default)|
| `fade`             | 200ms    | ease-in-out                             | Simple fade               |
| `fade-up`          | 200–250ms| ease-in-out                             | Bottom-up entrance        |
| `fade-down`        | 250–300ms| ease-in-out                             | Top-down entrance         |
| `fade-scale`       | 280ms    | Default                                 | Scale entrance            |
| `fade-transition`  | 200ms    | ease-in-out                             | Opacity-only fade         |

### Directional Slides

| Animation          | Duration | Easing                                  | Usage                     |
| ------------------ | -------- | --------------------------------------- | ------------------------- |
| `slide-up`         | 250ms    | `cubic-bezier(0.25, 0.8, 0.5, 1)`      | Slide up (menus, toast)   |
| `slide-down`       | 250ms    | `cubic-bezier(0.25, 0.8, 0.5, 1)`      | Slide down (dropdowns)    |
| `slide-left`       | 250ms    | `cubic-bezier(0.25, 0.8, 0.5, 1)`      | Slide left (drawers)      |
| `slide-right`      | 250ms    | `cubic-bezier(0.25, 0.8, 0.5, 1)`      | Slide right (drawers)     |

### UI-Specific Transitions

| Animation          | Duration | Easing                                  | Usage                     |
| ------------------ | -------- | --------------------------------------- | ------------------------- |
| Side content       | 300ms    | `cubic-bezier(0.16, 1, 0.3, 1)`        | Popovers, dropdown panels |
| Breadcrumb enter   | 400ms    | `cubic-bezier(0.76, 0, 0.24, 1)`       | Breadcrumb item + skewX   |
| Collapse           | 200ms    | ease-in-out                             | Height / padding collapse |
| Sidebar collapse   | 200ms    | ease-in-out                             | Width transition          |
| Menu accordion     | 200ms    | ease                                    | Sub-menu expand/collapse  |
| Progress bar       | Continuous| Linear                                 | NProgress route loading   |

- Animations are **configurable** — can be disabled globally
- Loading progress bar appears on route transitions (NProgress)
- No decorative animations — all motion is functional

---

## 12. VXE Table Integration

VXE Table (used via `useVbenVxeGrid`) maps its internal CSS variables to the design system tokens:

| VXE Variable                                  | Maps to                          | Purpose                          |
| --------------------------------------------- | -------------------------------- | -------------------------------- |
| `--vxe-ui-font-color`                         | `hsl(var(--foreground))`         | Default table text               |
| `--vxe-ui-font-primary-color`                 | `hsl(var(--primary))`            | Primary color highlights         |
| `--vxe-ui-font-disabled-color`                | `hsl(var(--foreground) / 50%)`   | Disabled text                    |
| `--vxe-ui-table-header-background-color`      | `hsl(var(--accent))`             | Table header row background      |
| `--vxe-ui-table-border-color`                 | `hsl(var(--border))`             | Table grid lines                 |
| `--vxe-ui-table-row-hover-background-color`   | `hsl(var(--accent-hover))`       | Row hover highlight              |
| `--vxe-ui-table-row-striped-background-color` | `hsl(var(--accent) / 60%)`       | Striped row tint                 |
| `--vxe-ui-table-row-current-background-color` | `hsl(var(--accent))`             | Currently selected row           |
| `--vxe-ui-table-resizable-line-color`         | `hsl(var(--heavy))`              | Column resize handle line        |
| `--vxe-ui-layout-background-color`            | `hsl(var(--background))`         | Table container background       |
| `--vxe-ui-loading-background-color`           | `hsl(var(--overlay-content))`    | Loading overlay                  |
| `--vxe-ui-input-border-color`                 | `hsl(var(--border))`             | Inline input borders             |
| `--vxe-ui-base-popup-border-color`            | `hsl(var(--border))`             | Popup borders                    |

> All VXE Table components automatically inherit the active theme's tokens — no additional configuration needed when switching themes.
