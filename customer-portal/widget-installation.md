---
description: Step-by-step guide to installing the RewardsPro widget on your storefront
---

# Widget Installation

Add the RewardsPro loyalty widget to your Shopify store in minutes.

## Installation Methods

### Method 1: App Embed (Recommended)

The easiest way to add the widget:

1. Go to **Online Store → Themes** in Shopify admin
2. Click **Customize** on your active theme
3. Click **App embeds** (bottom left)
4. Find **RewardsPro Widget** and toggle it **ON**
5. Click **Save**

The widget will appear as a floating button on your storefront.

### Method 2: Theme Block

Add the widget to specific pages:

1. Go to **Online Store → Themes → Customize**
2. Navigate to the page where you want the widget
3. Click **Add block** or **Add section**
4. Select **RewardsPro Widget** from the app blocks
5. Position where desired
6. Click **Save**

### Method 3: Manual Installation

For advanced customization:

1. Go to **Online Store → Themes**
2. Click **Actions → Edit code**
3. Open `theme.liquid`
4. Add before `</body>`:

```liquid
{% render 'rewardspro-widget' %}
```

## Verifying Installation

After installation, verify the widget works:

1. Visit your storefront (not preview)
2. Look for the floating widget button
3. Click to open and verify content loads
4. Test with a logged-in customer account

## Widget Placement Options

### Floating Widget

**Default position**: Bottom-right corner

| Position | Best For |
|----------|----------|
| Bottom-right | Most stores (default) |
| Bottom-left | Stores with chat widgets on right |
| Top-right | Minimal interference with footer |

### Inline Widget

Embed directly in page content:

- Product pages (show tier pricing)
- Account dashboard (detailed view)
- Cart page (show available credit)

## Theme Compatibility

RewardsPro works with all Shopify themes:

| Theme Type | Compatibility |
|------------|---------------|
| Dawn (OS 2.0) | ✅ Full support |
| Debut | ✅ Full support |
| Brooklyn | ✅ Full support |
| Custom themes | ✅ Full support |
| Headless/Hydrogen | ⚠️ API integration required |

## Troubleshooting Installation

### Widget Not Appearing

1. **Check app embed is enabled** - Verify in theme customizer
2. **Clear cache** - Hard refresh (Ctrl+Shift+R)
3. **Check theme.liquid** - Ensure no conflicts
4. **Verify app is installed** - Check Shopify admin

### Widget Appears But Won't Open

1. **JavaScript errors** - Check browser console
2. **CSP issues** - Verify Content Security Policy allows app
3. **Theme conflicts** - Test with default theme

### Styling Issues

1. **CSS conflicts** - Check for `!important` overrides
2. **Z-index issues** - Widget may be behind other elements
3. **Responsive problems** - Test on mobile devices

## Performance Considerations

The widget is optimized for performance:

| Metric | Target |
|--------|--------|
| Initial load | < 100ms |
| Data fetch | < 500ms |
| Interaction delay | < 50ms |

### Lazy Loading

The widget loads on-demand:
- JavaScript loads after page content
- Data fetches only when widget opens
- Images load progressively

## Next Steps

- [Widget Customization](widget-customization.md) - Style the widget
- [Account Integration](account-integration.md) - Add to customer accounts
