# Testing: 404-Ryo Portfolio Site

## Overview
Static HTML/CSS portfolio site. Single `index.html` file with inline styles and scripts.

## Local Testing
- Open `index.html` directly in Chrome via `file:///` protocol — no server needed
- Run `google-chrome file:///path/to/index.html` to open in browser

## What to Test

### Fonts
- **Google Fonts** are loaded via `<link>` tag in `<head>`. Check the URL to verify which fonts are included.
- Use DevTools → Elements → select text element → Computed tab → scroll to "Rendered Fonts" to confirm the actual font being used.
- Console check: `document.querySelector('link[href*="fonts.googleapis"]').href.includes('FontName')` returns true/false.

### CSS Effects (hover, gradients, animations)
- **Hover effects** on `.char` elements in hero section ("Hi," and "spark" have individual letter spans). Mouse over each letter to trigger.
- **Gradient text** uses `background: linear-gradient(...)`, `-webkit-background-clip: text`, `-webkit-text-fill-color: transparent`. Verify in DevTools Computed tab.
- **Marquee, scroll animations** are CSS-only (`@keyframes`).

### Responsive
- The site uses `@media (max-width: 768px)` breakpoints. Resize browser or use DevTools device emulation.
- Custom cursor is hidden on mobile/touch devices via `(hover: none)` media query.

### i18n
- Language toggle (JP/EN) in nav bar switches text via JS `data-i18n` attributes.
- Test both languages to verify text displays correctly.

## Key CSS Classes
- `.italic` — accent text (section titles, "building things"). Uses distinct font/style.
- `.char` — individual letter spans for hover effects in hero h1.
- `.marker` — yellow highlight behind "Ryo".
- `.pill` — tag badges in hero meta section.

## No CI
This repo has no CI pipeline. Testing is purely visual via browser.

## Devin Secrets Needed
None — static site with no authentication or API keys.
