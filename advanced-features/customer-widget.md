---
description: Display loyalty status on your storefront with the customer widget
---

# Customer Widget

The Customer Widget displays loyalty information directly on your storefront, showing customers their tier status, cashback rate, store credit balance, and progress toward the next tier.

---

## How It Works

```
Customer visits your store
        ↓
Widget loads via Theme App Extension
        ↓
Widget calls RewardsPro API (HMAC verified)
        ↓
Customer data retrieved (if logged in)
        ↓
Tier status, balance, and progress displayed
        ↓
Guest message shown (if not logged in)
```

---

## Widget Features

| Feature | Description |
|---------|-------------|
| **Tier Badge** | Current tier with icon and color |
| **Cashback Rate** | Percentage earned on orders |
| **Store Credit** | Available balance in store currency |
| **Progress Bar** | Visual progress to next tier |
| **Next Tier** | What's needed for upgrade |
| **Guest Prompt** | Encourages login/signup |

---

## Enabling the Widget

### Step 1: Enable in RewardsPro

1. Go to **Settings** > **Widget**
2. Toggle **Widget Active** to ON
3. Save settings

### Step 2: Enable App Embed in Theme

1. Go to **Shopify Admin** > **Online Store** > **Themes**
2. Click **Customize** on your active theme
3. Click **App embeds** (bottom left)
4. Find **RewardsPro Widget** and toggle ON
5. Click **Save**

### Step 3: Configure Position

In the App embed settings:

| Setting | Options | Description |
|---------|---------|-------------|
| **Position** | Bottom-right, Bottom-left, Top-right, Top-left | Widget location |
| **Offset X** | 0-100px | Horizontal offset from edge |
| **Offset Y** | 0-100px | Vertical offset from edge |

---

## Widget Configuration

### Display Settings

Configure in RewardsPro **Settings** > **Widget**:

| Setting | Description | Default |
|---------|-------------|---------|
| **Widget Active** | Enable/disable widget | Off |
| **Show Tier Badge** | Display current tier | On |
| **Show Cashback Rate** | Display earning percentage | On |
| **Show Balance** | Display store credit | On |
| **Show Progress** | Show next tier progress | On |

### Guest Settings

Configure what guests (non-logged-in users) see:

| Setting | Description | Example |
|---------|-------------|---------|
| **Guest Message** | Text shown to guests | "Join our loyalty program!" |
| **Guest CTA Text** | Button text | "Sign Up" |
| **Guest CTA URL** | Where button links | "/account/login" |

### Cache Settings

| Setting | Range | Description |
|---------|-------|-------------|
| **Cache Duration** | 60-3600 seconds | How long to cache data |
| **Fallback Cache** | On/Off | Use cached data if API fails |

---

## Theme App Extension

The widget is delivered via Shopify's Theme App Extension:

### Block File

Located at: `extensions/theme-app-extension-rewardspro/blocks/membership_widget.liquid`

### Assets

| File | Purpose |
|------|---------|
| `membership-widget.js` | Widget functionality (30KB) |
| `membership-widget.css` | Widget styling (53KB) |

### Block Settings

The Liquid block exposes these settings to theme editors:

```liquid
{% schema %}
{
  "name": "RewardsPro Widget",
  "settings": [
    {
      "type": "checkbox",
      "id": "enable_api_calls",
      "label": "Enable Live Data",
      "default": true
    },
    {
      "type": "range",
      "id": "cache_duration",
      "label": "Cache Duration (seconds)",
      "min": 60,
      "max": 3600,
      "default": 300
    }
  ]
}
{% endschema %}
```

---

## Widget API

The widget fetches data from RewardsPro via app proxy:

### Endpoint

```
GET /apps/rewardspro/membership
```

### Authentication

- Uses Shopify app proxy HMAC verification
- Customer identified via `logged_in_customer_id`
- No API key exposed to frontend

### Response Data

```json
{
  "success": true,
  "data": {
    "customer": {
      "firstName": "John",
      "lastName": "Doe",
      "storeCredit": 45.50,
      "totalCashbackEarned": 125.00,
      "totalSpent": 2500.00
    },
    "tier": {
      "name": "Gold",
      "cashbackPercent": 5,
      "icon": "⭐",
      "color": "#FFD700"
    },
    "nextTier": {
      "name": "Platinum",
      "minSpend": 5000,
      "cashbackPercent": 8
    },
    "progress": {
      "current": 2500,
      "target": 5000,
      "percentage": 50
    }
  }
}
```

---

## Customization

### CSS Variables

Override widget styles with CSS variables:

```css
:root {
  --rewardspro-primary: #FFD700;
  --rewardspro-secondary: #333333;
  --rewardspro-text: #FFFFFF;
  --rewardspro-background: #1a1a1a;
  --rewardspro-border-radius: 12px;
  --rewardspro-font-family: inherit;
}
```

### Custom Styling

Add custom CSS in your theme:

```css
/* Widget container */
.rewardspro-widget {
  /* Your custom styles */
}

/* Tier badge */
.rewardspro-tier-badge {
  /* Your custom styles */
}

/* Progress bar */
.rewardspro-progress-bar {
  /* Your custom styles */
}

/* Balance display */
.rewardspro-balance {
  /* Your custom styles */
}
```

### Hiding Elements

Hide specific widget elements:

```css
/* Hide progress bar */
.rewardspro-progress { display: none; }

/* Hide store credit */
.rewardspro-balance { display: none; }
```

---

## Widget States

### Logged In Customer

Shows:
- Tier badge with name, icon, and color
- Cashback rate percentage
- Store credit balance
- Progress bar to next tier
- Next tier name and requirement

### Guest (Not Logged In)

Shows:
- Guest message
- Call-to-action button
- Brief program overview

### Loading State

Shows:
- Skeleton loading animation
- Brief loading indicator

### Error State

If API fails:
- Falls back to cached data
- Shows generic tier info
- Encourages page refresh

---

## Mobile Optimization

The widget is fully responsive:

| Breakpoint | Behavior |
|------------|----------|
| Desktop (>768px) | Full widget with all elements |
| Tablet (768px) | Compact layout |
| Mobile (<480px) | Minimal floating button, expands on tap |

### Mobile-Specific Features

- Touch-friendly button size
- Swipe to dismiss
- Reduced animations for performance
- Smaller cache for memory

---

## Performance

### Load Time

- Widget JS: ~30KB gzipped
- Widget CSS: ~15KB gzipped
- API call: <200ms typical

### Optimization

| Feature | Benefit |
|---------|---------|
| **Lazy Loading** | Widget loads after page |
| **Caching** | Reduces API calls |
| **No Dependencies** | Pure JS, no framework |
| **Async Loading** | Non-blocking |

### Noscript Fallback

For users with JavaScript disabled:

```html
<noscript>
  <a href="/account">View your loyalty status</a>
</noscript>
```

---

## Troubleshooting

### Widget Not Appearing

**Check:**
1. Widget enabled in RewardsPro Settings
2. App embed enabled in theme
3. Theme is active (not draft)
4. No JavaScript errors in console

**Solution:**
1. Toggle app embed off and on
2. Clear browser cache
3. Try incognito window

### Shows Guest State When Logged In

**Check:**
1. Customer is actually logged in
2. Shopify customer accounts enabled
3. App proxy is configured

**Solution:**
1. Log out and log back in
2. Clear cookies
3. Verify app proxy in Shopify Partners

### Wrong Data Displayed

**Check:**
1. Customer synced to RewardsPro
2. Tier assigned correctly
3. Cache hasn't expired

**Solution:**
1. Force sync customer
2. Clear widget cache
3. Verify data in RewardsPro admin

### Styling Conflicts

**Check:**
1. Theme CSS not overriding widget
2. Z-index conflicts
3. Position conflicts

**Solution:**
1. Add `!important` to widget styles
2. Adjust z-index
3. Change widget position

---

## Best Practices

### Placement

- **Bottom-right**: Most common, unobtrusive
- **Bottom-left**: Good if chat widget on right
- **Avoid top**: Can conflict with navigation

### Messaging

- **Guest message**: Keep short and compelling
- **CTA text**: Action-oriented ("Join Now", "Sign Up")
- **Benefits focus**: Highlight what they'll get

### Performance

- Enable caching (300+ seconds recommended)
- Use fallback cache for reliability
- Monitor API response times

---

## Related Guides

- [Widget Customization](widget-customization.md) - Advanced styling
- [Customer Account](customer-account.md) - Account page integration
- [Settings](../configuration/widget-settings.md) - All widget settings
