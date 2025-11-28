---
description: Configure branded email notifications for your loyalty program (Max & Ultra plans)
---

# Email Settings

Send professional, branded email notifications to customers about their rewards, tier changes, and program updates.

{% hint style="info" %}
**Plan Requirement**: Email configuration is available on Max and Ultra plans only. Basic notification emails are included in all plans.
{% endhint %}

---

## Accessing Email Settings

1. Go to **Settings** in the main navigation
2. Select the **Email** tab

---

## Email Configuration

### Enable Email Notifications

| Setting | Default | Description |
|---------|---------|-------------|
| **Email Enabled** | Off | Master toggle for custom email notifications |

When enabled, customers receive emails for:
- Tier upgrades and downgrades
- Cashback earned confirmations
- Store credit balance updates
- Program announcements

---

## Email Provider Options

Choose your email delivery service:

| Provider | Best For | Features |
|----------|----------|----------|
| **SendGrid** | Most stores | Easy setup, reliable delivery, analytics |
| **Mailgun** | Technical teams | Developer-friendly, flexible |
| **Amazon SES** | High volume | Cost-effective, scalable |
| **Custom SMTP** | Existing infrastructure | Use your own mail server |

### SendGrid Setup

1. Create a SendGrid account
2. Generate an API key with "Mail Send" permissions
3. Enter API key in RewardsPro settings
4. Verify sender email

### Mailgun Setup

1. Create a Mailgun account
2. Verify your domain
3. Generate an API key
4. Enter credentials in RewardsPro settings

### Amazon SES Setup

1. Set up SES in AWS Console
2. Verify sender domain
3. Request production access (out of sandbox)
4. Generate SMTP credentials
5. Enter credentials in RewardsPro settings

### Custom SMTP Setup

For your own mail server:

| Field | Description | Example |
|-------|-------------|---------|
| **SMTP Host** | Mail server hostname | `smtp.yourcompany.com` |
| **SMTP Port** | Server port | `587` (TLS) or `465` (SSL) |
| **Username** | SMTP username | `notifications@yourcompany.com` |
| **Password** | SMTP password | (encrypted) |

{% hint style="warning" %}
All email credentials are encrypted using AES-256-GCM before storage. Your API keys and passwords are never stored in plain text.
{% endhint %}

---

## Sender Configuration

### From Name

The name displayed as the email sender.

| Field | Details |
|-------|---------|
| **Max Length** | 100 characters |
| **Example** | "MyStore Rewards" |
| **Recommendation** | Use your brand name + "Rewards" or "VIP" |

### From Address

The email address shown as the sender.

| Field | Details |
|-------|---------|
| **Format** | Valid email address |
| **Example** | `rewards@mystore.com` |
| **Requirement** | Must be verified with your email provider |

### Reply-To Address

Where customer replies are directed.

| Field | Details |
|-------|---------|
| **Format** | Valid email address |
| **Example** | `support@mystore.com` |
| **Recommendation** | Use a monitored inbox |

{% hint style="info" %}
**Tip**: Set reply-to to your support email so customer questions reach the right team.
{% endhint %}

---

## Branding

### Email Logo

Your logo displayed in email headers.

| Requirement | Details |
|-------------|---------|
| **Format** | PNG, JPG, or SVG |
| **Size** | Max 200KB |
| **Dimensions** | Recommended 200x50px |
| **URL** | Must be HTTPS |

### Primary Brand Color

The main color used for buttons and accents.

| Field | Details |
|-------|---------|
| **Format** | Hex code (e.g., `#5C6AC4`) |
| **Used In** | Buttons, links, tier badges |
| **Recommendation** | Match your store's primary color |

### Footer Text

Custom text in email footer.

| Field | Details |
|-------|---------|
| **Max Length** | 500 characters |
| **Default** | Company address and unsubscribe info |
| **Example** | "123 Main St, City, State 12345" |

---

## Custom Email Domain (Ultra Plan)

White-label your emails with a custom domain:

### Benefits

- Professional appearance (rewards@yourdomain.com)
- Better deliverability with DKIM/SPF
- Full brand consistency
- No third-party branding

### Setup Process

1. Add custom domain in settings
2. Add DNS records to your domain:
   - SPF record
   - DKIM record
   - DMARC record (recommended)
3. Verify domain
4. Enable custom domain sending

### Required DNS Records

| Record Type | Name | Value |
|-------------|------|-------|
| **TXT (SPF)** | `@` | `v=spf1 include:spf.provider.com ~all` |
| **CNAME (DKIM)** | `em._domainkey` | `dkim.provider.com` |
| **TXT (DMARC)** | `_dmarc` | `v=DMARC1; p=quarantine; rua=mailto:...` |

{% hint style="warning" %}
DNS propagation can take up to 48 hours. Plan ahead when setting up custom domains.
{% endhint %}

---

## Email Templates

### Available Templates

| Template | Trigger | Content |
|----------|---------|---------|
| **Tier Upgrade** | Customer reaches new tier | Congratulations, new benefits |
| **Tier Downgrade** | Customer drops tier | Status change, how to regain |
| **Cashback Earned** | Order with cashback | Amount earned, balance |
| **Balance Update** | Manual credit adjustment | New balance, reason |
| **Welcome** | New program member | Program overview, current tier |

### Template Customization

Each template can be customized:

| Element | Customizable | Notes |
|---------|--------------|-------|
| **Subject Line** | Yes | Max 100 characters |
| **Header Text** | Yes | Main message heading |
| **Body Content** | Yes | Main content area |
| **CTA Button** | Yes | Text and link |
| **Footer** | Yes | Additional info |

### Dynamic Variables

Use these variables in templates:

| Variable | Description | Example Output |
|----------|-------------|----------------|
| `{{customer_name}}` | Customer's name | "John" |
| `{{tier_name}}` | Current tier | "Gold" |
| `{{cashback_rate}}` | Cashback percentage | "5%" |
| `{{store_credit}}` | Current balance | "$45.50" |
| `{{amount_earned}}` | Cashback from order | "$5.00" |
| `{{next_tier}}` | Next tier name | "Platinum" |
| `{{spend_needed}}` | Amount to next tier | "$500" |

---

## Usage Tracking

### Monthly Email Quota

Email limits based on plan:

| Plan | Monthly Emails |
|------|----------------|
| **Max** | 10,000 |
| **Ultra** | Unlimited |

### Tracking Metrics

Monitor your email usage:

| Metric | Description |
|--------|-------------|
| **Emails Sent This Month** | Count since last reset |
| **Quota Remaining** | Available sends |
| **Reset Date** | When counter resets |
| **Last Email Sent** | Timestamp of most recent |

### Approaching Quota

When nearing your limit:
- Warning at 80% usage
- Notification at 90% usage
- Sends pause at 100% (emails queued)

{% hint style="warning" %}
Queued emails send when quota resets or you upgrade. No emails are lost.
{% endhint %}

---

## Deliverability

### Best Practices

1. **Verify your domain** - Improves trust with email providers
2. **Use consistent from address** - Build sender reputation
3. **Monitor bounce rates** - Remove invalid addresses
4. **Include unsubscribe link** - Required by law, improves reputation

### Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| **Emails going to spam** | Poor sender reputation | Verify domain, warm up sender |
| **Low open rates** | Weak subject lines | Test different subjects |
| **High bounces** | Invalid email addresses | Clean customer list |
| **Not receiving** | Blocked by provider | Check SPF/DKIM records |

---

## Troubleshooting

### Emails Not Sending

1. Verify email is enabled in settings
2. Check API key is valid
3. Confirm sender email is verified
4. Check monthly quota hasn't been reached
5. Review email provider dashboard for errors

### Wrong Branding

1. Clear email template cache
2. Re-upload logo if needed
3. Verify color hex code format
4. Check preview before sending

### Provider Connection Failed

1. Verify API key/credentials
2. Check provider service status
3. Ensure correct provider selected
4. Test with provider's own tools

---

## Related Guides

- [Widget Settings](widget-settings.md) - Customer-facing branding
- [Tier Automation](tier-automation.md) - Trigger tier change emails
- [Store Settings](store-settings.md) - Store information for emails
