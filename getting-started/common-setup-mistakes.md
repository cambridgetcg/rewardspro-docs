---
description: Avoid these common mistakes when setting up your loyalty program
---

# Common Setup Mistakes

Learn from others' mistakes. Here are the most common issues merchants encounter during setup and how to avoid them.

---

## Tier Configuration Mistakes

### ❌ Unreachable Tier Thresholds

**The Mistake:**
Setting thresholds so high that customers can never reach them.

```
Example (for a store with $50 AOV):
Bronze: $0
Silver: $5,000    ← Takes 100 orders!
Gold: $20,000     ← Nearly impossible
```

**The Fix:**
Set thresholds based on your actual customer data:
- First upgrade: 2-4x your AOV
- Top tier: Achievable by top 2-5% of customers

```
Better Example:
Bronze: $0
Silver: $200      ← 4 orders
Gold: $600        ← Loyal customers
Platinum: $1,500  ← Top customers
```

---

### ❌ Insignificant Rate Differences

**The Mistake:**
Making cashback differences so small they don't motivate.

```
Bad Example:
Bronze: 2.0%
Silver: 2.5%    ← Only 0.5% more
Gold: 3.0%      ← Barely noticeable
```

**The Fix:**
Make each tier noticeably better (at least 1.5x):

```
Better Example:
Bronze: 2%
Silver: 4%      ← 2x Bronze
Gold: 6%        ← 1.5x Silver
Platinum: 10%   ← Clear top tier benefit
```

---

### ❌ Too Many Tiers

**The Mistake:**
Creating 6+ tiers that confuse customers.

**The Fix:**
Stick to 3-4 tiers. More isn't better—it's confusing.

---

## Data Sync Mistakes

### ❌ Not Syncing Before Launch

**The Mistake:**
Launching without importing historical orders. Result: All customers start at base tier.

**The Fix:**
Always sync historical data before going live:

1. Go to **Settings** → **Data Sync**
2. Select date range matching your evaluation period
3. Enable **Update Customer Metrics**
4. Run sync and wait for completion

---

### ❌ Wrong Date Range

**The Mistake:**
Using "Annual" evaluation but only syncing "Last 30 days."

**The Fix:**
Match your sync range to your evaluation period:

| Evaluation Period | Minimum Sync Range |
|-------------------|-------------------|
| Annual | Last year |
| Lifetime | All time |

---

### ❌ Syncing Without Updating Metrics

**The Mistake:**
Running sync but leaving "Update Customer Metrics" disabled.

**The Fix:**
For initial setup, ALWAYS enable:
- ✅ Update Customer Metrics
- ✅ Reconcile Existing Ledger Entries (if re-syncing)

---

## Automation Mistakes

### ❌ Forgetting to Enable Automation

**The Mistake:**
Tiers are set up but automation is disabled. Customers never upgrade.

**The Fix:**

1. Go to **Settings** → **Tier Automation**
2. Toggle **Enable Automatic Tier Recalculation** ON
3. Set frequency (Weekly recommended)
4. Save

---

### ❌ Wrong Evaluation Period

**The Mistake:**
Using "Annual" when you want spending to accumulate forever, or vice versa.

**The Fix:**
Understand the difference:

| Setting | Behavior | Best For |
|---------|----------|----------|
| **Annual** | Resets each year | Most stores |
| **Lifetime** | Never resets | Relationship-focused brands |

---

## Cashback Mistakes

### ❌ Unsustainable Rates

**The Mistake:**
Setting 15% cashback when your profit margin is 20%.

**The Fix:**
Calculate sustainable rates:
- Maximum cashback should be < 50% of profit margin
- Example: 40% margin → max 15-20% cashback at top tier

---

### ❌ Not Testing Calculations

**The Mistake:**
Going live without placing a test order.

**The Fix:**
Always test before launch:

1. Place a real order (low-cost item)
2. Complete payment
3. Verify cashback appears
4. Check customer balance updated

---

### ❌ Excluding Everything

**The Mistake:**
Excluding so many products that customers rarely earn cashback.

**The Fix:**
Be selective with exclusions:
- ✅ Gift cards (recommended)
- ✅ Donations
- ⚠️ Sale items (consider carefully)
- ❌ Too many collections

---

## Widget Mistakes

### ❌ Not Enabling the App Embed

**The Mistake:**
Widget settings configured but app embed not enabled in theme.

**The Fix:**

1. Go to **Shopify Admin** → **Online Store** → **Themes**
2. Click **Customize** on active theme
3. Click **App embeds** (left sidebar, bottom)
4. Toggle RewardsPro widget ON
5. Save

---

### ❌ Not Testing Mobile

**The Mistake:**
Widget looks good on desktop but broken on mobile.

**The Fix:**
Always test on:
- Desktop browser
- Mobile phone
- Tablet (if relevant)

---

### ❌ Conflicting Positions

**The Mistake:**
Widget positioned where it overlaps with chat widget or other elements.

**The Fix:**
Check for conflicts:
- Chat widgets (Tidio, Intercom, etc.)
- Cookie banners
- Announcement bars
- Sticky add-to-cart buttons

Move RewardsPro to opposite corner if needed.

---

## Communication Mistakes

### ❌ Not Announcing the Program

**The Mistake:**
Launching silently. Customers don't know the program exists.

**The Fix:**
Communicate through multiple channels:
- Email to existing customers
- Website banner/popup
- Social media announcement
- Order confirmation mention

---

### ❌ Overpromising

**The Mistake:**
Marketing says "Earn up to 20% back!" when top tier is actually 10%.

**The Fix:**
Be accurate in all communications. Disappointment hurts more than modest promises.

---

### ❌ Confusing Terms

**The Mistake:**
Using "points," "credits," and "cashback" interchangeably.

**The Fix:**
Pick one term and use it consistently:
- "Store credit" - most clear
- "Cashback" - familiar to customers
- "Rewards" - generic but works

---

## Monitoring Mistakes

### ❌ Set and Forget

**The Mistake:**
Setting up the program and never checking on it.

**The Fix:**
Monitor regularly:
- **Week 1**: Daily checks
- **Month 1**: Weekly reviews
- **Ongoing**: Monthly analytics review

---

### ❌ Ignoring Errors

**The Mistake:**
Dismissing sync errors or processing failures.

**The Fix:**
Check for issues:
1. Review **Discrepancies** after syncs
2. Monitor order processing success rate
3. Investigate customer complaints promptly

---

## Quick Fixes Checklist

If something's wrong, check these first:

### Customers Not Getting Cashback
- [ ] Order is marked "Paid" in Shopify
- [ ] Products aren't excluded
- [ ] Customer has an account (not guest)
- [ ] Webhook is connected

### Tiers Not Updating
- [ ] Tier automation is enabled
- [ ] Recalculation frequency isn't "Never"
- [ ] Customer spending crosses threshold
- [ ] Try manual recalculation

### Widget Not Showing
- [ ] App embed enabled in theme
- [ ] Not blocked by ad blocker
- [ ] Cleared browser cache
- [ ] Correct theme is active

### Data Looks Wrong
- [ ] Correct date range synced
- [ ] "Update Customer Metrics" was enabled
- [ ] Evaluation period matches sync
- [ ] Wait for sync to complete

---

## Still Stuck?

If you've checked everything and still have issues:

1. **Email Support**: support@rewardspro.io
2. **Include Details**:
   - Your store URL
   - What you expected to happen
   - What actually happened
   - Screenshots if possible

{% hint style="info" %}
**Most issues are solved by the fixes above.** Check each item before contacting support.
{% endhint %}

