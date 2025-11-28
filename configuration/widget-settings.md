---
description: Configure the customer-facing loyalty widget on your storefront
---

# Widget Settings

Customize the loyalty widget that appears on your storefront, allowing customers to view their tier status, store credit balance, and rewards progress.

## What is the Widget?

The RewardsPro widget is a floating panel that appears on your storefront, giving customers easy access to their loyalty information without leaving the page they're browsing.

**Widget features:**
- Current tier and benefits
- Store credit balance
- Progress toward next tier
- Transaction history
- Localized content

---

## Accessing Widget Settings

1. Go to **Settings** in the main navigation
2. Select the **Widget** tab

---

## Widget Appearance

### Position

Choose where the widget trigger button appears on screen:

| Position | Coordinates | Best For |
|----------|-------------|----------|
| **Bottom-right** | Right: 20px, Bottom: 20px | Most stores (default) |
| **Bottom-left** | Left: 20px, Bottom: 20px | Stores with chat widgets on right |
| **Top-right** | Right: 20px, Top: 80px | Below header positioning |
| **Custom** | Your values | Specific placement needs |

{% hint style="info" %}
If you have a chat widget (Tidio, Intercom, etc.), position RewardsPro on the opposite side to avoid overlap.
{% endhint %}

### Panel Size

Configure the widget panel dimensions:

| Size | Width | Height | Best For |
|------|-------|--------|----------|
| **Small** | 320px | Auto | Mobile-first stores |
| **Medium** | 380px | Auto | Most stores (recommended) |
| **Large** | 440px | Auto | Desktop-focused, detailed content |

**Mobile behavior:**
- Widget automatically adjusts to screen width on mobile
- Full-width on screens under 480px
- Touch-friendly tap targets

### Colors

Match the widget to your brand identity:

| Color Setting | Default | Purpose |
|---------------|---------|---------|
| **Primary Color** | #5C6AC4 | Buttons, tier badges, progress bar |
| **Background Color** | #FFFFFF | Panel background |
| **Text Color** | #212B36 | Body text, headings |
| **Accent Color** | #008060 | Success states, highlights |

**Color format:** Use hex codes (e.g., `#FF5733`) or RGB values.

{% hint style="warning" %}
Ensure sufficient contrast between text and background colors for accessibility (WCAG 2.1 AA compliance).
{% endhint %}

---

## Content Sections

Toggle which sections appear in the widget panel:

### Core Sections

| Section | Description | Default | Recommendation |
|---------|-------------|---------|----------------|
| **Tier Badge** | Current tier name and icon | On | Always keep on |
| **Store Credit** | Available balance display | On | Always keep on |
| **Progress Bar** | Visual progress to next tier | On | Keep on for engagement |

### Optional Sections

| Section | Description | Default | Recommendation |
|---------|-------------|---------|----------------|
| **Benefits List** | Current tier perks/rewards | Off | Enable for complex programs |
| **Next Tier Preview** | Benefits at next tier | Off | Enable to encourage upgrades |
| **Transaction History** | Recent cashback/redemptions | Off | Enable for transparency |
| **How It Works** | Program explanation | Off | Enable for new programs |

### Section Order

Drag and drop to reorder sections:

```
Default Order:
1. Tier Badge
2. Store Credit Balance
3. Progress to Next Tier
4. Benefits (if enabled)
5. History (if enabled)
```

---

## Trigger Button

### Button Style

Choose how the widget trigger appears:

| Style | Appearance | Best For |
|-------|------------|----------|
| **Icon + Text** | Badge icon with "Rewards" label | Maximum visibility |
| **Icon Only** | Circular icon button | Minimal, clean themes |
| **Text Only** | Text link style | Integrated feel |
| **Custom Image** | Your own image/logo | Brand consistency |

### Button Text

Customize the trigger button text:

| Default | Alternatives |
|---------|-------------|
| "Rewards" | "My Rewards" |
| | "VIP Status" |
| | "Loyalty Points" |
| | "Member Benefits" |
| | Your custom text |

**Character limit:** 20 characters maximum

### Icon Options

For icon-based buttons:

| Icon | Description |
|------|-------------|
| **Star** | Classic rewards icon (default) |
| **Gift** | Emphasizes rewards/perks |
| **Badge** | VIP/membership feel |
| **Crown** | Premium/luxury positioning |
| **Heart** | Community/relationship focus |

---

## Language & Localization

### Supported Languages

The widget supports automatic translation:

| Language | Code | Status |
|----------|------|--------|
| English | en | Default |
| French | fr | Full support |
| Spanish | es | Full support |
| German | de | Full support |
| Portuguese | pt | Full support |
| Italian | it | Full support |
| Dutch | nl | Full support |
| Japanese | ja | Full support |

### Auto-Detection

Widget automatically detects language from:

1. **Shopify locale** (if multi-language store)
2. **Browser settings** (Accept-Language header)
3. **Customer preference** (if saved)

**Priority order:** Shopify locale > Browser settings > Default (English)

### Custom Translations

Override any text string in the widget:

```
Original: "Your Store Credit"
Custom: "Your Cash Balance"

Original: "Spend to reach"
Custom: "Shop to unlock"
```

Access custom translations in **Settings** → **Widget** → **Customize Text**.

---

## Advanced Settings

### Lazy Loading

Widget loads on-demand for optimal performance:

| Setting | Behavior | Impact |
|---------|----------|--------|
| **Enabled** (default) | Script loads after page ready | Faster initial page load |
| **Disabled** | Script loads immediately | Widget ready faster |

**Load sequence:**
1. Page content loads
2. Widget script loads (deferred)
3. Customer data fetches on first open
4. Images load progressively

### Z-Index

Control widget stacking order:

| Setting | Value | Use Case |
|---------|-------|----------|
| Default | 999999 | Above most elements |
| Custom | Your value | Resolve conflicts with other widgets |

### Animation

Configure widget open/close animation:

| Animation | Duration | Feel |
|-----------|----------|------|
| **Slide** (default) | 200ms | Smooth, professional |
| **Fade** | 150ms | Subtle, minimal |
| **None** | 0ms | Instant, no animation |

### Custom CSS

Add custom styles to match your theme:

```css
/* Override primary color */
.rewardspro-widget {
  --rp-primary-color: #your-brand-color;
  --rp-primary-hover: #your-hover-color;
}

/* Customize border radius */
.rewardspro-widget {
  --rp-border-radius: 16px;
}

/* Adjust shadow */
.rewardspro-widget-panel {
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
}

/* Custom font */
.rewardspro-widget {
  font-family: 'Your Font', sans-serif;
}
```

{% hint style="info" %}
Custom CSS requires knowledge of CSS. Changes may need adjustment after widget updates.
{% endhint %}

---

## Mobile Optimization

### Responsive Behavior

The widget automatically adapts to mobile devices:

| Screen Width | Behavior |
|--------------|----------|
| > 768px | Standard floating panel |
| 480-768px | Reduced panel width |
| < 480px | Full-width bottom sheet |

### Mobile-Specific Settings

| Setting | Desktop | Mobile |
|---------|---------|--------|
| Button position | Configurable | Fixed bottom-right |
| Panel width | As configured | Full width |
| Scroll behavior | Panel scrolls | Native scroll |
| Close button | Click outside | Swipe down or X |

### Touch Optimization

- 44px minimum tap targets
- Swipe gestures supported
- Pull-to-refresh disabled (prevents conflicts)
- Smooth momentum scrolling

---

## Testing Your Widget

### Preview Mode

1. Go to **Settings** → **Widget**
2. Click **Preview Widget**
3. View widget as it will appear to customers
4. Test all sections and interactions

### Test on Live Store

1. Save widget settings
2. Visit your storefront (logged in or incognito)
3. Look for widget trigger button
4. Click to open and verify content

### Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Widget not appearing | Theme app embed disabled | Enable in Shopify theme editor |
| Wrong position | CSS conflict | Adjust z-index or position |
| Slow loading | Large page size | Enable lazy loading |
| Overlapping other widgets | Same position | Change widget position |

---

## Best Practices

### For Maximum Engagement

- Position bottom-right (most visible)
- Use "Icon + Text" button style
- Enable progress bar (encourages spending)
- Enable tier benefits section
- Use your primary brand color

### For Minimal Design

- Position bottom-left
- Use "Icon Only" button style
- Disable optional sections
- Match background to site
- Use subtle animations

### For Complex Programs

- Enable all content sections
- Use larger panel size
- Include "How It Works" section
- Enable transaction history
- Consider custom translations

---

## Troubleshooting

### Widget Not Appearing

1. Verify theme app embed is enabled:
   - Go to Shopify Admin → Online Store → Themes
   - Click Customize on active theme
   - Go to App Embeds section
   - Enable RewardsPro widget

2. Check for JavaScript errors:
   - Open browser developer tools (F12)
   - Check Console tab for errors
   - Look for RewardsPro-related messages

3. Verify settings are saved:
   - Return to Widget Settings
   - Click Save again
   - Hard refresh storefront (Ctrl+Shift+R)

### Widget Conflicts

If widget conflicts with other apps:

1. Try different position settings
2. Adjust z-index value
3. Check for CSS conflicts
4. Contact support with screenshots

### Slow Widget Loading

1. Enable lazy loading
2. Reduce enabled sections
3. Optimize store page speed
4. Check network in dev tools

