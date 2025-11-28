---
description: Configure business metrics for accurate ROI tracking and analytics
---

# Business Metrics

Configure your business metrics to enable accurate ROI calculations, profitability analysis, and program performance tracking in the Analytics dashboard.

## Why Configure Business Metrics?

Without business metrics, RewardsPro can only show basic revenue numbers. With properly configured metrics, you get:

| Without Metrics | With Metrics |
|-----------------|--------------|
| Total cashback issued | **Net profit impact** |
| Revenue from loyalty customers | **True ROI percentage** |
| Order counts | **Cost-adjusted profitability** |
| Basic trends | **Break-even analysis** |

---

## Accessing Business Metrics

1. Go to **Settings** in the main navigation
2. Select the **Store Metrics** tab
3. Or access directly from **Analytics** → **Configure Metrics**

---

## Configurable Metrics

### Average Profit Margin

Your typical profit margin as a percentage of revenue.

| Field | Details |
|-------|---------|
| **Format** | Percentage (0-100+) |
| **Example** | 40 means 40% profit margin |
| **Used For** | ROI calculations, profitability analysis |

**How to calculate:**
```
Profit Margin = (Revenue - Cost) / Revenue × 100

Example:
  Revenue: $100
  Cost: $60
  Profit Margin: ($100 - $60) / $100 × 100 = 40%
```

{% hint style="info" %}
Use your overall average margin. If margins vary by product, use a weighted average based on sales volume.
{% endhint %}

---

### Average COGS Percentage

Cost of Goods Sold as a percentage of revenue.

| Field | Details |
|-------|---------|
| **Format** | Percentage (0-100+) |
| **Example** | 35 means COGS is 35% of revenue |
| **Used For** | Gross profit calculations |

**Relationship with Profit Margin:**
```
COGS% + Gross Profit Margin% ≈ 100%

Example:
  If COGS = 35%
  Then Gross Margin ≈ 65%
```

---

### Average Shipping Cost

Your typical shipping cost per order.

| Field | Details |
|-------|---------|
| **Format** | Currency amount |
| **Example** | 5.50 means $5.50 per order |
| **Used For** | True cost calculations |

**Consider including:**
- Packaging materials
- Carrier costs (averaged)
- Handling labor (if significant)

{% hint style="warning" %}
If you offer free shipping, still enter your actual cost here for accurate profit calculations.
{% endhint %}

---

### Average Order Value (AOV)

Your historical average order value.

| Field | Details |
|-------|---------|
| **Format** | Currency amount |
| **Example** | 85.00 means $85 average order |
| **Used For** | Benchmarking, projections |

**How to find this:**
1. Go to **Shopify Admin** → **Analytics** → **Reports**
2. Look for "Average order value" in your sales reports
3. Use a 3-6 month average for stability

---

### Target ROI Percentage

Your desired return on investment for the loyalty program.

| Field | Details |
|-------|---------|
| **Format** | Percentage (0-100+) |
| **Example** | 300 means 3x return target |
| **Used For** | Performance benchmarking |

**Understanding ROI targets:**

| Target ROI | Meaning | Typical For |
|------------|---------|-------------|
| 100% | Break even | Minimum acceptable |
| 200% | 2x return | Conservative goal |
| 300% | 3x return | Healthy program |
| 500%+ | 5x+ return | High-performing program |

---

## How Metrics Affect Analytics

### ROI Calculation

With configured metrics, RewardsPro calculates:

```
Program ROI = (Incremental Revenue × Profit Margin - Cashback Issued) / Cashback Issued × 100

Example:
  Incremental Revenue from loyalty: $10,000
  Profit Margin: 40%
  Cashback Issued: $500

  ROI = ($10,000 × 0.40 - $500) / $500 × 100
  ROI = ($4,000 - $500) / $500 × 100
  ROI = 700%
```

### Break-Even Analysis

Shows how much revenue is needed to cover cashback costs:

```
Break-Even Revenue = Cashback Issued / Profit Margin

Example:
  Cashback Issued: $500
  Profit Margin: 40%

  Break-Even = $500 / 0.40 = $1,250
```

### Profitability Dashboard

The Analytics page shows:
- **Net Program Profit**: Revenue × Margin - Cashback
- **Cost per Acquisition**: Cashback per new customer
- **Lifetime Value Impact**: How loyalty affects CLV
- **Margin-Adjusted Metrics**: True profitability numbers

---

## Best Practices

### Setting Accurate Metrics

1. **Use historical data** - Don't guess, pull from your accounting
2. **Update quarterly** - Refresh metrics as your business changes
3. **Be conservative** - Slightly lower margins = realistic expectations
4. **Include all costs** - Don't forget hidden costs in COGS

### Common Mistakes

| Mistake | Impact | Solution |
|---------|--------|----------|
| Ignoring shipping costs | Overstated profits | Include actual shipping cost |
| Using list price margin | Inflated ROI | Use actual realized margin |
| Forgetting discounts | Wrong calculations | Use post-discount revenue |
| Outdated metrics | Misleading analytics | Update quarterly |

### Recommended Update Schedule

| Metric | Update Frequency |
|--------|------------------|
| Profit Margin | Quarterly |
| COGS | Quarterly |
| Shipping Cost | When rates change |
| AOV | Monthly |
| Target ROI | Annually |

---

## Example Configurations

### E-commerce (Physical Products)

```
Profit Margin: 45%
COGS: 35%
Shipping Cost: $6.50
AOV: $75
Target ROI: 300%
```

### Digital Products

```
Profit Margin: 85%
COGS: 10%
Shipping Cost: $0
AOV: $49
Target ROI: 500%
```

### Fashion/Apparel

```
Profit Margin: 55%
COGS: 30%
Shipping Cost: $8.00
AOV: $120
Target ROI: 250%
```

### Food & Beverage

```
Profit Margin: 35%
COGS: 45%
Shipping Cost: $12.00
AOV: $65
Target ROI: 200%
```

---

## Troubleshooting

### Analytics Not Showing ROI

1. Verify all metrics are filled in
2. Check that values are positive numbers
3. Ensure profit margin is reasonable (1-100%)
4. Refresh the Analytics page

### Numbers Look Wrong

1. Double-check your margin calculation
2. Verify currency is correct
3. Ensure AOV matches your Shopify data
4. Review COGS vs margin relationship

### Last Updated Shows Old Date

1. Make a small change to any metric
2. Click Save
3. Timestamp will update automatically
