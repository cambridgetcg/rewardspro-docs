---
description: Customize the look and feel of your loyalty widget to match your brand
---

# Widget Customization

Make the RewardsPro widget match your store's brand identity with extensive customization options.

## Accessing Customization

1. Go to **Online Store → Themes → Customize**
2. Click **App embeds** or find the widget block
3. Click on **RewardsPro Widget** to open settings

## Appearance Settings

### Colors

Customize the widget color scheme:

| Setting | Description | Default |
|---------|-------------|---------|
| **Primary Color** | Buttons, highlights | Your theme's primary |
| **Background** | Widget background | White |
| **Text Color** | Body text | Dark gray |
| **Accent Color** | Links, badges | Theme accent |

### Position

Control where the widget appears:

| Option | Description |
|--------|-------------|
| **Bottom Right** | Default, most common |
| **Bottom Left** | Good for stores with other right-side widgets |
| **Custom** | Set exact pixel position |

### Size

| Option | Dimensions | Best For |
|--------|------------|----------|
| Small | 320px wide | Mobile-first stores |
| Medium | 380px wide | Most stores (default) |
| Large | 440px wide | Desktop-focused stores |

## Content Settings

### Visible Sections

Toggle which sections appear:

| Section | Description | Default |
|---------|-------------|---------|
| **Tier Badge** | Current tier with icon | ✅ On |
| **Store Credit** | Available balance | ✅ On |
| **Progress Bar** | Progress to next tier | ✅ On |
| **Recent Activity** | Last 5 transactions | ✅ On |
| **Tier Benefits** | List of tier perks | ⬜ Off |

### Progress Bar Style

Choose how tier progress is displayed:

- **Bar** - Horizontal progress bar
- **Circle** - Circular progress indicator
- **Text Only** - "Silver: $350 / $500"

### Balance Display

Configure how store credit is shown:

- **Prominent** - Large balance at top
- **Compact** - Smaller, inline display
- **Hidden** - Don't show balance (transactions only)

## Trigger Button

### Button Style

| Style | Description |
|-------|-------------|
| **Icon Only** | Small circular button |
| **Icon + Text** | Button with "Rewards" label |
| **Text Only** | Text link style |
| **Custom** | Your own HTML/image |

### Button Text

Default: "Rewards"

Customize to match your brand:
- "My Rewards"
- "Loyalty Points"
- "VIP Status"
- "Member Benefits"

### Animation

| Animation | Description |
|-----------|-------------|
| **Bounce** | Subtle attention-grabbing bounce |
| **Pulse** | Gentle pulsing glow |
| **None** | Static button |

## Tier Badge Customization

### Badge Style

| Style | Example |
|-------|---------|
| **Filled** | Solid color background |
| **Outline** | Border only |
| **Gradient** | Modern gradient effect |
| **Minimal** | Text only, no badge |

### Tier Colors

Set custom colors per tier:

```
Bronze:   #CD7F32
Silver:   #C0C0C0
Gold:     #FFD700
Platinum: #E5E4E2
```

### Tier Icons

Choose icons for each tier:
- Default medal icons
- Star ratings (★★★)
- Custom uploaded icons
- Emoji support 🥉🥈🥇

## Language & Text

### Supported Languages

| Language | Code |
|----------|------|
| English | `en` |
| French | `fr` |
| Spanish | `es` |
| German | `de` |

### Custom Text

Override default text:

| Key | Default | Customizable |
|-----|---------|--------------|
| `widget.title` | "Your Rewards" | ✅ |
| `widget.balance` | "Store Credit" | ✅ |
| `widget.progress` | "Progress to {tier}" | ✅ |
| `widget.earn` | "Earn {rate}% cashback" | ✅ |

## Advanced Customization

### Custom CSS

Add custom styles:

```css
/* Make widget match dark theme */
.rewardspro-widget {
  --rp-bg-color: #1a1a1a;
  --rp-text-color: #ffffff;
  --rp-border-radius: 16px;
}

/* Custom tier badge */
.rewardspro-tier-badge {
  font-family: 'Your Custom Font', sans-serif;
  text-transform: uppercase;
}
```

### CSS Variables

Available CSS custom properties:

```css
--rp-primary-color
--rp-bg-color
--rp-text-color
--rp-border-color
--rp-border-radius
--rp-shadow
--rp-font-family
--rp-font-size
```

## Mobile Customization

### Mobile-Specific Settings

| Setting | Desktop | Mobile |
|---------|---------|--------|
| Position | Bottom-right | Bottom-center |
| Size | Medium | Full-width |
| Button | Icon + Text | Icon only |

### Responsive Behavior

The widget automatically adapts:
- Smaller padding on mobile
- Stacked layout for content
- Touch-optimized buttons
- Swipe to close

## Preview & Testing

### Theme Preview

1. Use theme customizer preview
2. Test logged-in and logged-out states
3. Check mobile preview

### Test Mode

Enable test mode to:
- See widget with sample data
- Test different tier states
- Preview customizations instantly

## Best Practices

### Do's ✅

- Match your brand colors
- Keep content focused
- Test on mobile devices
- Use clear, concise text

### Don'ts ❌

- Overwhelm with information
- Use hard-to-read colors
- Hide the store credit balance
- Disable progress indicators
