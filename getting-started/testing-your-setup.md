---
description: Verify your loyalty program works correctly before going live
---

# Testing Your Setup

Before announcing your loyalty program, thoroughly test every aspect to ensure customers have a great experience.

## Pre-Testing Checklist

Before you start testing, confirm:

- [ ] At least 2 tiers are created
- [ ] One tier is set as the default
- [ ] Tier automation is enabled
- [ ] **Automatic Cashback** is on (dashboard → **Features**)
- [ ] Customers sign in with customer accounts, not legacy customer accounts (**Shopify Admin** → **Settings** → **Customer accounts**)
- [ ] Historical data has been synced (if applicable)

---

## Test 1: Tier Creation

### What to Check

| Item | Expected Result |
|------|-----------------|
| Tiers display correctly | All tiers visible in dashboard |
| Thresholds are logical | Each tier has higher threshold than previous |
| Cashback rates are set | Each tier shows a percentage |
| Default tier is assigned | One tier marked as default |

### How to Test

1. Go to **Membership Tiers**
2. Verify all tiers are listed
3. Check that thresholds increase progressively
4. Confirm the default tier is highlighted

---

## Test 2: Customer Sync

### What to Check

| Item | Expected Result |
|------|-----------------|
| Customers appear in list | Customer count matches Shopify |
| Tiers are assigned | Each customer has a tier |
| Spending totals are correct | Match Shopify order history |

### How to Test

1. Go to **Customers**
2. Find a known customer
3. Verify their tier assignment
4. Check their spending total against Shopify

---

## Test 3: Place a Test Order

This is the most important test. Place a real order to verify cashback works.

### Step-by-Step

1. **Create a test product** (or use an existing low-cost item)
2. **Place an order** signed in as a test customer whose email you control
3. **Complete payment** (use Shopify's test mode if available)
4. **Wait 1-2 minutes** for webhook processing
5. **Check RewardsPro** for the order

### Expected Results

| Check | What to Look For |
|-------|------------------|
| Order appears | Listed in Orders page |
| Cashback calculated | Shows correct percentage of order |
| Customer balance updated | Store credit increased, in RewardsPro and on the customer in Shopify admin |
| Ledger entry created | Transaction in customer history |

### If Using Shopify Payments Test Mode

1. Enable test mode in Shopify Payments
2. Use card: `4242 4242 4242 4242`
3. Any future expiry and CVV
4. Complete the test order

---

## Test 4: Spend Store Credit at Checkout

Customers spend their cashback at checkout, so test that too. Use the test customer from Test 3 once their cashback shows as store credit.

### Before You Start

- Customers sign in with customer accounts, not legacy customer accounts. Store credit isn't available with legacy accounts.
- The test customer has a store credit balance in Shopify. Open the customer in your Shopify admin to check.

### How to Test

1. On your storefront, add products worth more than the test customer's balance
2. At checkout, sign in as the test customer (or pay with Shop Pay)
3. Apply the store credit
4. Pay the rest and complete the order

### Expected Results

| Check | What to Look For |
|-------|------------------|
| Store credit offered | Checkout offers the customer's store credit |
| Full balance applied | Shopify applies the full balance. There's no way to choose part of it |
| Shopify balance | The customer's store credit in Shopify admin went down by the amount used |
| RewardsPro balance | The customer in RewardsPro shows the same balance as Shopify, and their store credit history has a **Payment** entry |

[Yu: after the dev-store run, say here whether this order earns cashback on the part paid with store credit, or delete this line.]

{% hint style="warning" %}
**Store credit not offered at checkout?** Check that the customer is signed in through customer accounts (not legacy accounts) or paying with Shop Pay, and that the checkout currency matches the currency of their balance.
{% endhint %}

---

## Test 5: Tier Upgrade

Test that customers upgrade when they cross thresholds.

### How to Test

1. Find a customer close to an upgrade threshold
2. Place an order that pushes them over
3. Wait for tier recalculation (or trigger manual recalc)
4. Verify they're now in the higher tier

### Manual Tier Recalculation

If you can't wait for automatic recalculation:

1. Go to **Settings** → **Tier Automation**
2. Click **Recalculate Now**
3. Wait for completion
4. Check customer's tier

---

## Test 6: Customer Widget (If Enabled)

### What to Check

| Item | Expected Result |
|------|-----------------|
| Widget appears | Floating button visible on storefront |
| Tier displays | Correct tier name and badge |
| Balance shows | Accurate store credit amount |
| Progress bar works | Shows progress to next tier |

### How to Test

1. Go to your storefront
2. Log in as a test customer
3. Look for the widget button
4. Click to open the widget panel
5. Verify all information is correct

### Common Widget Issues

| Issue | Solution |
|-------|----------|
| Widget not appearing | Enable app embed in theme settings |
| Wrong information | Clear browser cache, refresh |
| Slow to load | Normal on first load, check internet |

---

## Test 7: Refund Handling

Test that refunds properly reverse cashback.

{% hint style="info" %}
RewardsPro takes back refunded cashback only from store credit the customer still holds. Credit already spent isn't taken back. For this test, use an order whose cashback the customer hasn't spent, such as a new test order.
{% endhint %}

### How to Test

1. Using that test order, process a refund in Shopify
2. Wait 1-2 minutes for webhook
3. Check RewardsPro:
   - Customer balance should decrease
   - Ledger should show reversal entry

---

## Test 8: Email Notifications

RewardsPro emails your customers on its own when a new customer is added and when their tier changes. See [Email Settings](../configuration/email-settings.md).

### What to Check

- [ ] Welcome email sends when a new customer is added
- [ ] Tier upgrade email sends on promotion
- [ ] Tier downgrade email sends when a customer moves down a tier

### How to Test

1. Use a real email address you can access
2. Trigger each notification type
3. Verify emails arrive and look correct

---

## Testing Checklist Summary

### Must Pass ✓

- [ ] Tiers display correctly
- [ ] Test order processes cashback
- [ ] Customer balance updates
- [ ] Store credit can be spent at checkout
- [ ] Ledger shows transactions

### Should Pass ✓

- [ ] Tier upgrade works
- [ ] Refund reverses cashback
- [ ] Widget displays correctly

### Nice to Have ✓

- [ ] Emails send correctly
- [ ] Bulk operations work
- [ ] Analytics show data

---

## Common Test Issues

### Order Not Appearing

**Causes:**
- Order not yet paid (pending payment)
- Webhook delay (wait 2-3 minutes)
- Test order excluded by settings

**Solutions:**
1. Verify order is marked "Paid" in Shopify
2. Wait and refresh
3. Check Settings for test order exclusions

### Wrong Cashback Amount

**Causes:**
- Discounts not accounted for
- Wrong tier assigned
- Shipping/tax inclusion settings

**Solutions:**
1. Check what's included in cashback calculation
2. Verify customer's tier
3. Review cashback settings

### Customer Not Upgrading

**Causes:**
- Tier automation disabled
- Threshold not actually crossed
- Recalculation hasn't run yet

**Solutions:**
1. Enable tier automation
2. Double-check spending vs threshold
3. Trigger manual recalculation

---

## After Testing

Once all tests pass:

1. ✅ Delete test orders (if needed)
2. ✅ Reset test customer data (if needed)
3. ✅ Proceed to [Going Live Checklist](going-live-checklist.md)

{% hint style="success" %}
**All tests passed?** You're ready to launch! Continue to the [Going Live Checklist](going-live-checklist.md).
{% endhint %}

