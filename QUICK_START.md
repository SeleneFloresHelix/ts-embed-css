# Quick Start Guide

## What's Included

This repository provides ready-to-use CSS files for customizing ThoughtSpot embedded liveboards:

### Main Files
- **`css/liveboard-starter.css`** (329 lines)
  - Comprehensive starter template
  - All customizable components
  - Well-documented sections
  - Ready to use or customize

### Theme Variations
- **`css/themes/dark-theme.css`** (90 lines)
  - Modern dark theme
  - Perfect for dark mode apps
  
- **`css/themes/light-minimal.css`** (85 lines)
  - Clean, minimal design
  - Professional appearance
  
- **`css/themes/corporate-blue.css`** (95 lines)
  - Enterprise-ready
  - Professional blue palette

### Examples
- **`examples/index.html`**
  - Live demonstration of all styled components
  - Integration code examples
  - Theme switching instructions

## 5-Minute Setup

### Step 1: Choose Your CSS File
Pick a theme that matches your application:
```
css/liveboard-starter.css       # Start here for custom styling
css/themes/dark-theme.css       # Dark mode
css/themes/light-minimal.css    # Clean & minimal
css/themes/corporate-blue.css   # Enterprise style
```

### Step 2: Host the File
Upload your chosen CSS file to:
- Your web server
- CDN (jsDelivr, unpkg)
- Cloud storage (S3, Azure, etc.)

**Important:** Must be HTTPS accessible.

### Step 3: Integrate with ThoughtSpot
```javascript
import { init, AuthType } from '@thoughtspot/visual-embed-sdk';

init({
  thoughtSpotHost: "https://your-instance.thoughtspot.cloud",
  authType: AuthType.TrustedAuthToken,
  customCssUrl: "https://your-domain.com/css/liveboard-starter.css"
});
```

### Step 4: Allowlist Your Domain
In ThoughtSpot Admin:
1. Go to **Security Settings**
2. Add your domain to **CSP style-src domains**
3. Save changes

## Customization Tips

### Change Brand Colors
Edit the `:root` section in your CSS file:
```css
:root {
  --ts-var-button--primary-background: #YOUR_COLOR;
  --ts-var-viz-color-1: #YOUR_CHART_COLOR_1;
  /* etc. */
}
```

### Override Specific Components
Add your custom styles at the bottom of the CSS file:
```css
/* Custom Overrides */
.liveboard-title {
  font-family: 'Your Custom Font', sans-serif;
  color: #your-color;
}
```

### Test Locally
Open `examples/index.html` in a browser to preview changes before deploying.

## What Can You Customize?

✅ Colors (backgrounds, text, borders)
✅ Typography (fonts, sizes, weights)
✅ Buttons (all states and variants)
✅ Charts (color palettes)
✅ Tables (headers, rows, hover effects)
✅ Filters and search inputs
✅ Navigation panels
✅ Loading states
✅ Modals and dialogs
✅ Spacing and layout
✅ Responsive breakpoints

## Need Help?

- View the example page: `examples/index.html`
- Read the full README: `README.md`
- Check [ThoughtSpot Developer Docs](https://developers.thoughtspot.com/)
- Visit [ThoughtSpot Community](https://community.thoughtspot.com/)

## Screenshot

View the styled components:
![CSS Customization Examples](https://github.com/user-attachments/assets/47ff4cef-3344-40cb-ac89-24e9807fbc00)
