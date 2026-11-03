---
description: Set the sender, sending domain and branding of the emails RewardsPro sends
---

# Email Settings

RewardsPro sends emails to your customers about their loyalty program. This page covers which emails go out and the settings that shape them.

{% hint style="warning" %}
**Not available yet**

- **Email campaigns and automations** aren't sending yet. You can draft them, but nothing is sent.
- **The AI writing assistant** in the email editor isn't available.
{% endhint %}

---

## Emails RewardsPro Sends on Its Own

| Email | When it's sent |
|-------|----------------|
| **Welcome** | When a new customer is added to your Shopify store |
| **Tier upgrade** | When an order moves a customer up a tier |
| **Tier downgrade** | When an order moves a customer down a tier |

These emails go out automatically. There's no switch to turn them off one by one yet.

[Yu: decide whether these emails should wait for a per-email switch before release, then keep or change this section.]

---

## Accessing Email Settings

1. Go to **Marketing** in the RewardsPro navigation
2. Click **Settings** on the Marketing overview

The page is called **Email Settings**.

---

## Marketing Platform

| Option | What it means |
|--------|---------------|
| **In-House** | RewardsPro sends your emails, using SendGrid |
| **Klaviyo** | RewardsPro sends customer profiles and events to your Klaviyo account, where you build flows and campaigns |

[Yu: Klaviyo hasn't been tested on the rebuilt backend. Keep the Klaviyo row only once it has.]

---

## Sending Domain

| Mode | From address |
|------|--------------|
| **Shared Domain** (default) | Emails are sent from **rewards@rewardspro.io** with your store name. Some email clients show "via rewardspro.io". |
| **Custom Domain** | Emails are sent from your own domain once you've added the DNS records RewardsPro shows you and clicked **Verify DNS**. |

---

## Sender Configuration

| Field | Details |
|-------|---------|
| **From Name** | The name in the "From" field, such as "MyStore Rewards" |
| **From Email** | With a custom domain, it must match your verified domain. In shared mode, it's used as the Reply-To address |
| **Reply-To Email** | Where replies go (optional). Use an inbox you check |

---

## Brand Customization

Set a **Primary color**, a **Secondary color** and a **Font Family** for your emails.

---

## Email Usage

The **Email Usage** card counts the emails sent this month, split into campaign, automation and transactional emails. RewardsPro is free, and passing the number shown doesn't stop emails.

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
| **High bounces** | Invalid email addresses | Clean customer list |
| **Not receiving** | Blocked by provider | Check SPF/DKIM records |

---

## Related Guides

- [Widget Settings](widget-settings.md) - Customer-facing branding
- [Tier Automation](tier-automation.md) - Trigger tier change emails
- [Store Settings](store-settings.md) - Store information for emails
