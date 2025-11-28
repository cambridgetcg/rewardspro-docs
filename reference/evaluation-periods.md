---
description: Understanding annual vs. lifetime tier evaluation
---

# Evaluation Periods

How RewardsPro calculates customer tier status based on spending.

## Two Evaluation Methods

### Annual Evaluation

Spending is calculated from the **past 12 months** only.

**How it works:**
- Rolling 12-month window
- Recalculated monthly (or on each order)
- Customers can move up OR down
- Old spending "falls off"

**Example:**
```
Customer: John
Last 12 months spending: $800
Tier: Silver ($500 threshold)

Next month, a $400 order from 13 months ago falls off:
New 12-month spending: $400
New tier: Bronze
```

**Best for:**
- Encouraging ongoing engagement
- Seasonal businesses
- Stores wanting fresh starts

### Lifetime Evaluation

Spending is calculated from **all time** since account creation.

**How it works:**
- Total historical spending
- Customers only move UP
- No tier demotions
- Rewards long-term loyalty

**Example:**
```
Customer: Jane
Lifetime spending: $2,000
Tier: Gold ($1,000 threshold)

Even if Jane doesn't purchase for a year:
Lifetime spending: Still $2,000
Tier: Still Gold
```

**Best for:**
- Building permanent loyalty
- Luxury/high-value stores
- Rewarding legacy customers

## Comparison

| Aspect | Annual | Lifetime |
|--------|--------|----------|
| Window | 12 months | All time |
| Direction | Up and down | Up only |
| Demotions | Possible | Never |
| Engagement | Continuous | One-time achievement |
| Liability | Lower | Higher |

## Choosing an Evaluation Period

### Choose Annual If:

- You want ongoing engagement
- Business is seasonal
- You prefer lower credit liability
- Customers shop frequently

### Choose Lifetime If:

- You value long-term relationships
- High-value, infrequent purchases
- Luxury or premium positioning
- You want simple customer communication

## Changing Evaluation Period

### Can I Switch?

Yes, but consider:
- All tiers recalculate
- Some customers may change tiers
- Communicate changes to customers

### Best Practice

Choose your evaluation period during setup and stick with it. Frequent changes confuse customers.

## Technical Details

### When Recalculation Happens

**Annual:**
- On each order
- Daily cron job (overnight)
- Manual recalculation option

**Lifetime:**
- On each order
- Immediate updates

### Order Date Handling

For annual evaluation:
- Uses order **paid date**
- Not order created date
- Timezone-aware
