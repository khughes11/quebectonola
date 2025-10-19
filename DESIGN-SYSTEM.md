# Quebec to NOLA Trail Documentation - Design System

A comprehensive, accessible design system for documenting the ancient First Nations trail across Canada and the United States.

## 🎨 Design Philosophy

This design system is inspired by:
- **National Park Service** design aesthetics
- **Historical atlases** and field notebooks
- **Topographic map symbology**
- **Respectful archival presentation** of Indigenous histories

## 🎯 Key Features

- **WCAG 2.2 AA Compliant** - Full accessibility support
- **Mobile-First Responsive** - Works from 320px to 1440px+
- **Dark Mode Support** - Automatic and manual toggle
- **Print Optimized** - Clean print styles for articles
- **Performance First** - Minimal assets, system fonts
- **Keyboard Accessible** - Full keyboard navigation support

## 🎨 Color Palette

### Light Mode
- **Ink**: `#1E2328` - Primary text color
- **Paper**: `#F7F5F2` - Background color
- **Moss**: `#2F5D3A` - Primary green
- **Cedar**: `#6B4F3B` - Secondary brown
- **River**: `#2D5F73` - Secondary blue
- **Sky**: `#7EA6C2` - Accent blue
- **Accent**: `#C07A2C` - Warm accent

### Dark Mode
- **Ink**: `#F7F5F2` - Primary text color
- **Paper**: `#1E2328` - Background color
- **Moss**: `#4A7C59` - Primary green (lighter)
- **Cedar**: `#8B6F4B` - Secondary brown (lighter)
- **River**: `#4A8BA3` - Secondary blue (lighter)
- **Sky**: `#9BB8D1` - Accent blue (lighter)
- **Accent**: `#D4A574` - Warm accent (lighter)

## 📝 Typography

### Font Families
- **Headings**: Inter (fallback: system-ui)
- **Body**: Source Serif 4 (fallback: Georgia)
- **Monospace**: SF Mono (fallback: Consolas)

### Scale
- **XS**: 12px
- **SM**: 14px
- **Base**: 16px
- **LG**: 20px
- **XL**: 24px
- **2XL**: 32px
- **3XL**: 40px
- **4XL**: 56px

## 🧩 Components

### Buttons
```html
<!-- Primary Button -->
<a href="#" class="btn btn--primary">Primary Action</a>

<!-- Secondary Button -->
<a href="#" class="btn btn--secondary">Secondary Action</a>

<!-- Subtle Button -->
<a href="#" class="btn btn--subtle">Subtle Action</a>

<!-- Link Button -->
<a href="#" class="btn btn--link">Link Action</a>
```

### Cards
```html
<!-- Basic Card -->
<div class="card">
  <div class="card__header">
    <h3 class="card__title">Card Title</h3>
    <p class="card__subtitle">Card subtitle</p>
  </div>
  <div class="card__content">
    <p>Card content goes here.</p>
  </div>
  <div class="card__footer">
    <a href="#" class="btn btn--primary">Action</a>
  </div>
</div>

<!-- Featured Card -->
<div class="card card--featured">
  <!-- Same structure as basic card -->
</div>
```

### Alerts/Callouts
```html
<!-- Info Alert -->
<div class="alert alert--info">
  <div class="alert__icon"><!-- SVG icon --></div>
  <div class="alert__content">
    <h4 class="alert__title">Info Title</h4>
    <div class="alert__text">Alert message content.</div>
  </div>
</div>

<!-- Note Alert -->
<div class="alert alert--note">
  <!-- Same structure -->
</div>

<!-- Source Alert -->
<div class="alert alert--source">
  <!-- Same structure -->
</div>

<!-- Caution Alert -->
<div class="alert alert--caution">
  <!-- Same structure -->
</div>
```

### Tags
```html
<!-- Basic Tag -->
<span class="tag">Tag Label</span>

<!-- Primary Tag -->
<span class="tag tag--primary">Primary Tag</span>

<!-- Secondary Tag -->
<span class="tag tag--secondary">Secondary Tag</span>

<!-- Accent Tag -->
<span class="tag tag--accent">Accent Tag</span>
```

## 📱 Layout System

### Container
```html
<div class="container">
  <!-- Content with max-width and responsive padding -->
</div>
```

### Grid System
```html
<!-- 12-column grid -->
<div class="grid grid-cols-12 gap-6">
  <div class="lg:col-span-8"><!-- Main content --></div>
  <div class="lg:col-span-4"><!-- Sidebar --></div>
</div>

<!-- Responsive grid -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  <!-- Responsive columns -->
</div>
```

### Flexbox Utilities
```html
<div class="flex items-center justify-between gap-4">
  <!-- Flexbox layout -->
</div>
```

## 🎯 Page-Specific Styles

### Trail Map Page
- Full-bleed responsive map container
- Legend panel with custom symbols
- Sticky "Back to sections" link

### Trail Sections Index
- Filterable grid by region, difficulty, status
- Consistent card layout
- Search functionality

### All Posts Page
- Searchable list with tags
- Year groupings
- Filter by content type

### How to Contribute Page
- Step-by-step cards
- Styled form patterns
- Clear call-to-actions

## 🌙 Dark Mode

### Automatic Detection
Dark mode automatically activates based on `prefers-color-scheme: dark`.

### Manual Toggle
Users can manually toggle dark mode using the theme toggle button in the navigation.

### Implementation
```javascript
// Theme toggle functionality is included in theme-toggle.js
// Automatically handles localStorage persistence
```

## ♿ Accessibility Features

### WCAG 2.2 AA Compliance
- **Color Contrast**: All color combinations meet 4.5:1 ratio
- **Focus States**: Visible focus indicators on all interactive elements
- **Touch Targets**: Minimum 44px touch targets
- **Keyboard Navigation**: Full keyboard accessibility
- **Screen Reader Support**: Proper ARIA labels and semantic HTML

### Keyboard Navigation
- **Tab Order**: Logical tab sequence
- **Skip Links**: Skip to main content
- **Focus Management**: Proper focus handling in modals/dropdowns
- **Escape Key**: Close modals and menus

### Reduced Motion Support
```css
@media (prefers-reduced-motion: reduce) {
  /* All animations and transitions are disabled */
}
```

## 🖨️ Print Styles

### Optimized for Articles
- Single-column layout
- Serif body text
- URLs after links
- Hidden navigation/footers
- Included citations

### Implementation
```css
@media print {
  /* Print-specific styles are included in design-system.css */
}
```

## 📁 File Structure

```
assets/
├── css/
│   ├── design-system.css    # Core design tokens and base styles
│   ├── components.css       # Reusable component styles
│   └── pages.css           # Page-specific styles
├── js/
│   └── theme-toggle.js     # Dark mode toggle functionality
└── images/
    ├── favicon.svg         # SVG favicon
    └── favicon.png         # PNG fallback favicon

_includes/
├── header.html            # Navigation header
├── breadcrumbs.html       # Breadcrumb navigation
├── section-card.html      # Trail section card component
├── alert.html            # Alert/callout component
├── timeline.html         # Timeline component
└── map-legend.html       # Map legend component

_layouts/
├── default.html          # Base layout template
├── home.html            # Homepage layout
├── post.html            # Blog post layout
└── page.html            # General page layout
```

## 🚀 Getting Started

### 1. Include CSS Files
```html
<link rel="stylesheet" href="/assets/css/design-system.css">
<link rel="stylesheet" href="/assets/css/components.css">
<link rel="stylesheet" href="/assets/css/pages.css">
```

### 2. Include JavaScript
```html
<script src="/assets/js/theme-toggle.js"></script>
```

### 3. Use Components
```html
<!-- Include components in your Jekyll templates -->
{% include header.html %}
{% include breadcrumbs.html %}
{% include section-card.html title="Section A" url="/sections/section-a/" %}
```

### 4. Apply Layouts
```yaml
# In your Jekyll front matter
---
layout: home
title: "Page Title"
description: "Page description"
---
```

## 🎨 Customization

### CSS Variables
All colors, spacing, and typography can be customized by overriding CSS custom properties:

```css
:root {
  --color-primary: #your-color;
  --font-family-heading: 'Your Font', sans-serif;
  --space-4: 1.5rem;
}
```

### Component Variants
Create new component variants by extending existing classes:

```css
.btn--custom {
  background-color: var(--color-accent);
  color: var(--color-text-inverse);
}
```

## 📚 Resources

### Design Inspiration
- [National Park Service Design System](https://www.nps.gov/subjects/digital/design-system.htm)
- [USWDS (U.S. Web Design System)](https://designsystem.digital.gov/)
- [Accessible Color Palette Builder](https://www.tpgi.com/color-contrast-checker/)

### Accessibility Guidelines
- [WCAG 2.2 Guidelines](https://www.w3.org/WAI/WCAG22/quickref/)
- [WebAIM Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Keyboard Navigation Testing](https://webaim.org/techniques/keyboard/)

### Typography Resources
- [Inter Font](https://rsms.me/inter/)
- [Source Serif 4](https://github.com/adobe-fonts/source-serif)
- [System Font Stack](https://systemfontstack.com/)

## 🤝 Contributing

When contributing to this design system:

1. **Maintain Accessibility**: Ensure all changes meet WCAG 2.2 AA standards
2. **Test Responsively**: Verify changes work across all breakpoints
3. **Document Changes**: Update this README for new components or modifications
4. **Respect Indigenous Histories**: Maintain respectful, archival tone in all content

## 📄 License

This design system is part of the Quebec to NOLA Trail Documentation project and follows the same licensing terms as the main project.
