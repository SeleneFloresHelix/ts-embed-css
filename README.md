# ThoughtSpot Embedded CSS Customization

A collection of starter CSS files for customizing the appearance of ThoughtSpot embedded liveboards. These templates provide a foundation for creating branded, professional-looking analytics dashboards within your application.

## 📁 Files

- **`css/liveboard-starter.css`** - Main starter template with comprehensive customization options
- **`css/themes/dark-theme.css`** - Modern dark theme for dark mode interfaces
- **`css/themes/light-minimal.css`** - Clean, minimal light theme
- **`css/themes/corporate-blue.css`** - Professional corporate theme with blue accents

## 🚀 Quick Start

### 1. Choose Your Theme

Select one of the pre-built themes or use the starter template as a base for your custom design.

### 2. Host the CSS File

Host your chosen CSS file on a CDN or your web server. The file must be accessible via HTTPS.

**Example hosting options:**
- Your own web server
- CDN (jsdelivr, unpkg, etc.)
- Cloud storage (S3, Azure Blob, etc.)

### 3. Configure ThoughtSpot Embed

Reference the CSS file in your ThoughtSpot embed initialization:

```javascript
import { init, AuthType } from '@thoughtspot/visual-embed-sdk';

init({
  thoughtSpotHost: "https://your-instance.thoughtspot.cloud",
  authType: AuthType.TrustedAuthToken,
  customCssUrl: "https://your-domain.com/css/liveboard-starter.css"
});
```

### 4. Allowlist the CSS URL

**Important:** You must allowlist your CSS URL in ThoughtSpot's security settings:

1. Go to **Admin** > **Security Settings**
2. Navigate to **CSP style-src domains**
3. Add your domain (e.g., `https://your-domain.com`)

## 🎨 Customization Guide

### Using CSS Variables

The starter CSS uses CSS variables for easy customization. Modify these in the `:root` section:

```css
:root {
  /* Primary Brand Colors */
  --ts-var-root-background: #ffffff;
  --ts-var-root-color: #333333;
  
  /* Navigation Panel */
  --ts-var-nav-background: #1a1a1a;
  --ts-var-nav-color: #ffffff;
  
  /* Button Colors */
  --ts-var-button--primary-background: #1976d2;
  --ts-var-button--primary-color: #ffffff;
  
  /* Chart Colors */
  --ts-var-viz-color-1: #1976d2;
  --ts-var-viz-color-2: #42a5f5;
  --ts-var-viz-color-3: #64b5f6;
  --ts-var-viz-color-4: #90caf9;
  --ts-var-viz-color-5: #bbdefb;
  
  /* Table Colors */
  --ts-var-table-header-background: #f5f5f5;
  --ts-var-table-header-color: #333333;
  --ts-var-table-header-border: #e0e0e0;
  --ts-var-table-row-background: #ffffff;
  --ts-var-table-row-alt-background: #fafafa;
  --ts-var-table-row-hover-background: #f5f5f5;
  --ts-var-table-border-color: #f0f0f0;
  --ts-var-table-text-color: #333333;
}
```

### Available Themes

#### 1. Starter Theme (`liveboard-starter.css`)
A comprehensive base template with:
- Clean, modern design
- Responsive layout
- Comprehensive component coverage
- Well-documented sections

#### 2. Dark Theme (`themes/dark-theme.css`)
Perfect for applications with dark interfaces:
- Dark backgrounds (#1a1a1a)
- High contrast text
- Vibrant chart colors optimized for dark backgrounds
- Subtle shadows and borders

#### 3. Light Minimal (`themes/light-minimal.css`)
A clean, minimal approach:
- Light backgrounds (#fafafa)
- Subtle borders
- Professional color palette
- Uncluttered design

#### 4. Corporate Blue (`themes/corporate-blue.css`)
Enterprise-ready theme:
- Professional blue color scheme
- Strong corporate identity
- Clear visual hierarchy
- Suitable for business dashboards

## 📋 Customizable Components

The CSS files include styles for:

- ✅ **Navigation Panel** - Side navigation and menus
- ✅ **Buttons** - Primary, secondary, and action buttons
- ✅ **Liveboard Headers** - Title and description areas
- ✅ **Visualization Tiles** - Chart and table containers
- ✅ **Charts** - Color palettes and styling
- ✅ **Tables** - Headers, rows, and hover states
- ✅ **Filters** - Search inputs and filter panels
- ✅ **Modals** - Dialog boxes and overlays
- ✅ **Loading States** - Spinners and loading indicators
- ✅ **Responsive Design** - Mobile and tablet optimizations

## 🛠️ Advanced Customization

### Creating Your Own Theme

1. Start with `liveboard-starter.css` as your base
2. Modify the CSS variables in the `:root` section
3. Add custom styles in the "Custom Overrides" section at the bottom
4. Test across different screen sizes and browsers

### Example: Custom Brand Colors

```css
:root {
  /* Your brand colors */
  --ts-var-button--primary-background: #ff6b6b;  /* Your primary color */
  --ts-var-button--primary--hover-background: #ee5a52;
  
  /* Chart color palette */
  --ts-var-viz-color-1: #ff6b6b;  /* Brand red */
  --ts-var-viz-color-2: #4ecdc4;  /* Brand teal */
  --ts-var-viz-color-3: #45b7d1;  /* Brand blue */
  --ts-var-viz-color-4: #f9ca24;  /* Brand yellow */
  --ts-var-viz-color-5: #6c5ce7;  /* Brand purple */
}
```

### Customizing Chart Colors

The 5 chart color variables (`--ts-var-viz-color-1` through `--ts-var-viz-color-5`) control the color palette used in visualizations. These colors are applied to:
- Bar charts
- Line charts
- Pie charts
- Area charts
- Other data visualizations

**Preview your chart colors** in the `examples/index.html` file to see how they look before deploying.

### Customizing Table Appearance

Tables support extensive customization through 8 CSS variables:

```css
:root {
  /* Header styling */
  --ts-var-table-header-background: #f5f5f5;  /* Header background color */
  --ts-var-table-header-color: #333333;       /* Header text color */
  --ts-var-table-header-border: #e0e0e0;      /* Header bottom border */
  
  /* Row styling */
  --ts-var-table-row-background: #ffffff;           /* Default row background */
  --ts-var-table-row-alt-background: #fafafa;       /* Alternating row background */
  --ts-var-table-row-hover-background: #f5f5f5;     /* Hover state background */
  
  /* Text and borders */
  --ts-var-table-border-color: #f0f0f0;       /* Cell border color */
  --ts-var-table-text-color: #333333;         /* Cell text color */
}
```

**Features:**
- Alternating row colors for better readability
- Customizable hover states
- Independent header and body styling
- Full color control for borders and text

### Using Multiple CSS Files

You can combine the base styles with theme-specific overrides:

```javascript
// Load base styles
init({
  thoughtSpotHost: "https://your-instance.thoughtspot.cloud",
  customCssUrl: "https://your-domain.com/css/liveboard-starter.css"
});

// Then add theme-specific overrides via a separate stylesheet
// in your application's HTML
```

## 📱 Responsive Design

All themes include responsive breakpoints for:
- **Desktop** (>768px) - Full layout with all features
- **Tablet** (768px) - Adjusted spacing and font sizes
- **Mobile** (<768px) - Optimized for small screens

## 🔒 Security Notes

- Always use HTTPS for hosting CSS files
- Allowlist your CSS domain in ThoughtSpot security settings
- Regularly review and update your CSS for security best practices
- Avoid inline styles that could pose XSS risks

## 📖 Resources

- [ThoughtSpot Developer Documentation](https://developers.thoughtspot.com/)
- [Visual Embed SDK](https://github.com/thoughtspot/visual-embed-sdk)
- [ThoughtSpot Custom CSS Demo](https://github.com/thoughtspot/custom-css-demo)
- [Style Customization Tutorial](https://developers.thoughtspot.com/docs/tutorials/style-customization/tutorial)

## 🤝 Contributing

To add a new theme or improve existing ones:
1. Create your CSS file in the `css/themes/` directory
2. Follow the existing structure and naming conventions
3. Document your theme in this README
4. Test with real ThoughtSpot embedded content

## 📄 License

This project is provided as-is for use with ThoughtSpot embedded analytics.

## 💡 Tips

- Start with a pre-built theme and customize from there
- Use browser DevTools to inspect ThoughtSpot elements and find CSS selectors
- Test your CSS changes in a development environment first
- Keep a backup of working CSS before making major changes
- Consider creating multiple theme variations for different use cases

---

**Need help?** Check the [ThoughtSpot Developer Community](https://community.thoughtspot.com/) or consult the official documentation.