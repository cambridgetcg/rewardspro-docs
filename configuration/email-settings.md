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
| **Welcome** | When a customer is created in your Shopify store, or when Shopify sends an update about a customer RewardsPro hasn't imported yet |
| **Tier upgrade** | When a paid order moves a customer up a tier |
| **Tier downgrade** | When a paid order moves a customer down a tier |
| **Tier membership ending** | For a tier membership with an end date, such as one bought as a tier product: a warning before it ends, and a notice when it has ended. A daily scheduled job sends these |

Refunds, tier changes you make by hand and scheduled tier recalculation don't send any of these emails.

### When They Start

The welcome and tier upgrade emails start once RewardsPro has saved email settings for your store. That happens the first time you:

- choose In-House or Klaviyo on the **Marketing** page, or close that choice
- save **Email Settings**
- connect Klaviyo
- switch to your own sending domain

The tier downgrade and tier membership emails don't wait for that, so they can go out from the day you install. Until you've saved email settings, they're sent from "RewardsPro" at rewards@rewardspro.io.

### Turning Them Off

There's no switch to turn these emails off. If you connect Klaviyo and choose it as your marketing platform, RewardsPro stops sending the welcome and tier upgrade emails itself, and your Klaviyo flows decide what goes out. RewardsPro still sends the tier downgrade and tier membership emails.

{% hint style="warning" %}
**Read these emails before your customers get them.** They go to customers whether or not they accept email marketing, and they have no unsubscribe link. The welcome email thanks the customer for joining your loyalty program and has a **Shop Now** button. The tier upgrade email has a **Start Earning More** button. You're responsible for any consent your emails need ([Terms](https://rewardspro.io/terms/), section 4).
{% endhint %}

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
| **Klaviyo** | RewardsPro sends customer profiles and events to your Klaviyo account, where you build flows and campaigns. We haven't tested the Klaviyo connection on the current version of RewardsPro yet |

---

## Sending Domain

| Mode | From address |
|------|--------------|
| **Shared Domain** (default) | Emails are sent from **rewards@rewardspro.io** with the From Name you set. Check it: it's "Store" if your settings were first saved from the Marketing page. |
| **Custom Domain** | Emails are sent from your own domain once you've added the DNS records RewardsPro shows you and clicked **Verify DNS**. |

---

## Sender Configuration

| Field | Details |
|-------|---------|
| **From Name** | The name in the "From" field, such as "MyStore Rewards" |
| **From Email** | With a custom domain, it must match your verified domain. In shared mode, From Email isn't used |
| **Reply-To Email** | Where replies go. In shared mode, set it to an inbox you check, or replies go to rewards@rewardspro.io instead of to you |

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

### Common Issues

| Issue | Cause | Solution |
|-------|-------|----------|
| **Emails going to spam** | Poor sender reputation | Verify domain, warm up sender |
| **High bounces** | Invalid email addresses | Clean customer list |
| **Not receiving** | Blocked by provider | Check SPF/DKIM records |

---

## Related Guides

- [Widget Settings](widget-settings.md) - Customer-facing branding
- [Tier Automation](tier-automation.md) - How tiers are recalculated
- [Store Settings](store-settings.md) - Store information for emails
