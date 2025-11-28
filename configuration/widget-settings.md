---
description: Configure the customer-facing loyalty widget
---

# Widget Settings

Customize the loyalty widget that appears on your storefront.

## Widget Appearance

### Position

Choose where the widget button appears:

| Position | Best For |
|----------|----------|
| Bottom-right | Most stores (default) |
| Bottom-left | Stores with chat widgets |
| Custom | Specific placement needs |

### Size

| Size | Width | Best For |
|------|-------|----------|
| Small | 320px | Mobile-first |
| Medium | 380px | Most stores |
| Large | 440px | Desktop focus |

### Colors

Match your brand:
- Primary color (buttons, highlights)
- Background color
- Text color
- Accent color

## Content Sections

Toggle which sections appear:

| Section | Description | Default |
|---------|-------------|---------|
| Tier Badge | Current tier with icon | ✅ On |
| Store Credit | Available balance | ✅ On |
| Progress Bar | Progress to next tier | ✅ On |
| Benefits | List of tier perks | ⬜ Off |
| History | Recent transactions | ⬜ Off |

## Trigger Button

### Button Style

| Style | Description |
|-------|-------------|
| Icon + Text | Button with "Rewards" label |
| Icon Only | Small circular button |
| Text Only | Text link style |

### Button Text

Default: "Rewards"

Customize to:
- "My Rewards"
- "Loyalty Points"
- "VIP Status"

## Language

### Supported Languages

- English (en) - Default
- French (fr)
- Spanish (es)
- German (de)

### Auto-Detection

Widget can auto-detect language from:
- Browser settings
- Shopify locale
- Customer preference

## Advanced Settings

### Lazy Loading

Widget loads on-demand for performance:
- JavaScript loads after page
- Data fetches on open
- Images load progressively

### Custom CSS

Add custom styles to match your theme:

```css
.rewardspro-widget {
  --rp-primary-color: #your-color;
  --rp-border-radius: 16px;
}
```
