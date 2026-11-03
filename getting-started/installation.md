---
description: Install RewardsPro from the Shopify App Store
---

# Installation

Get RewardsPro installed and connected to your Shopify store in just a few minutes.

## Requirements

Before installing, ensure you have:

| Requirement | Details |
|-------------|---------|
| **Shopify Store** | Any Shopify plan (Basic, Shopify, Advanced, Plus) |
| **Admin Access** | Store owner or staff with app installation permissions |
| **Customer Accounts** | Shopify customer accounts (not legacy customer accounts), so customers can sign in and spend their store credit |

### Customer Accounts and Spending Store Credit

RewardsPro pays cashback as Shopify store credit. Shopify decides where and how store credit can be spent:

- **Sign-in or Shop Pay**: Customers can spend store credit at checkout only when signed in through customer accounts, or when paying with Shop Pay.
- **No legacy accounts**: Store credit isn't available with legacy customer accounts.
- **Full balance only**: Shopify applies the customer's full store credit balance as payment. Customers can't choose to spend part of it.
- **Other Shopify limits**: Store credit can't pay for draft orders, edited orders or recurring subscription payments. It works on your online store, Point of Sale and Shop. At checkout, customers see only the balance in that checkout's currency.

To check your setup:

1. Go to **Shopify Admin** → **Settings** → **Customer accounts**
2. Make sure customers sign in with customer accounts, not legacy customer accounts
3. Make sure the **Store credit** setting is turned on there, so customers see their balance in their account
4. Save changes

See Shopify's [store credit help page](https://help.shopify.com/en/manual/customers/store-credit) for the full rules.

### Shopify's Fee on Store Credit

If your Shopify store was created on or after 12 May 2025, Shopify charges you its third-party transaction fee on the part of an order paid with store credit. This applies even if you use Shopify Payments. Stores created before 12 May 2025 don't pay this fee on store credit.

Shopify sets and bills this fee. RewardsPro doesn't receive it. See Shopify's [third-party transaction fees page](https://help.shopify.com/en/manual/your-account/manage-billing/billing-charges/types-of-charges/third-party-charges/third-party-transaction-fees) for the rate on your plan.

---

## Installation Steps

### Step 1: Find RewardsPro

**Option A: Direct Link**
Visit the [RewardsPro listing on the Shopify App Store](https://apps.shopify.com/rewards-pro).

**Option B: Search**
1. Go to [apps.shopify.com](https://apps.shopify.com)
2. Search for "RewardsPro"
3. Click on the RewardsPro listing

### Step 2: Add the App

1. Click **Add app** on the listing page
2. You'll be redirected to your Shopify admin
3. Review the app permissions

### Step 3: Authorize Permissions

Shopify shows the full list of permissions RewardsPro asks for before you approve. The main ones:

| Permission | Why It's Needed |
|------------|-----------------|
| **Customers** | Keep each customer's tier and spending up to date |
| **Orders** | Work out cashback, handle refunds and import past orders |
| **Store credit** | Issue cashback as store credit, and take back refunded cashback |
| **Products** | Tier products, if you sell memberships as products (optional) |

RewardsPro is free, so installing it doesn't start a charge.

Click **Install app** to grant permissions.

### Step 4: Complete Setup

After installation, you'll be taken to the RewardsPro dashboard. RewardsPro starts importing your customers in the background.

Three steps get RewardsPro ready. No cashback reaches customers automatically until the first two are done, and the third lets them see it. The **Get RewardsPro ready** card on the dashboard lists the steps until they're done:

1. **Create your first tier**: Cashback is a percentage of each order, set by the customer's tier. Until a tier exists, orders earn nothing. Tiers are under **Customers** → **Tiers**.
2. **Turn on automatic cashback**: Sends each order's cashback to the customer as Shopify store credit. While it's off, cashback waits on the **Orders** page for you to issue.
3. **Turn on the rewards widget**: Opens your theme editor with the **RewardsPro Widget** app embed switched on, so customers can see their tier and store credit. Click **Save** in the theme editor to publish it.

---

## Your First Tier

Create a basic tier structure:

| Suggested Setup | Value |
|-----------------|-------|
| Tier Name | "Bronze" or "Member" |
| Minimum Spend | $0 |
| Cashback Rate | 2-3% |

{% hint style="info" %}
See [Create Your First Tier](first-tier.md) for every tier setting.
{% endhint %}

---

## Post-Installation Checklist

After installation, complete these steps:

### Immediate (Do Now)

- [ ] Verify app appears in your Shopify admin sidebar
- [ ] Check that your currency displays correctly
- [ ] Create at least one tier
- [ ] Turn on **Automatic Cashback** on the dashboard
- [ ] Confirm customers sign in with customer accounts, not legacy accounts

### Before Launching

- [ ] [Create your tier structure](first-tier.md)
- [ ] [Sync historical data](initial-data-sync.md)
- [ ] [Test with a sample order, then spend the credit at checkout](testing-your-setup.md)

### Optional but Recommended

- [ ] [Assign VIP customers to top tiers](assigning-vips.md)
- [ ] [Configure business metrics](../configuration/business-metrics.md) for ROI tracking
- [ ] Turn on the **RewardsPro Widget** app embed in your theme

---

## Accessing RewardsPro

After installation, access the app through:

### From Shopify Admin

1. Go to your Shopify admin
2. Click **Apps** in the sidebar
3. Click **RewardsPro**

### Direct URL

Bookmark: `https://admin.shopify.com/store/[your-store]/apps/rewardspro`

---

## Troubleshooting Installation

### App Won't Install

**Check:**
- You have admin/owner permissions
- You're logged into the correct store
- No browser extensions blocking installation

**Try:**
1. Use a different browser
2. Clear cookies and cache
3. Disable ad blockers temporarily

### Permission Errors

**Check:**
- Your staff account has app management permissions
- You're not on a restricted staff role

**Solution:**
Ask the store owner to install the app.

### App Installed but Not Working

**Check:**
- App appears in Apps list
- No error messages in the dashboard
- Browser JavaScript is enabled

**Try:**
1. Refresh the page
2. Log out and back in
3. Contact support if issues persist

---

## Uninstalling (If Needed)

To uninstall RewardsPro:

1. Go to **Shopify Admin** → **Settings** → **Apps and sales channels**
2. Find RewardsPro
3. Click **Uninstall**

{% hint style="warning" %}
**Warning**: Uninstalling erases your store's records from RewardsPro's database straight away: tiers, customers, orders, cashback history and settings. This cannot be undone. Copies in our database host's daily backups expire within 8 days; see the [privacy policy](https://rewardspro.io/privacy-policy/).

Store credit already issued, and any tier products RewardsPro created, stay in Shopify.
{% endhint %}

---

## Next Steps

Now that RewardsPro is installed:

1. **[Create Your First Tier](first-tier.md)** - Set up your loyalty structure
2. **[Tier Strategy Guide](tier-strategy.md)** - Plan an effective tier system
3. **[Initial Data Sync](initial-data-sync.md)** - Import existing customers and orders

