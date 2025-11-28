---
icon: book-open
description: Technical documentation for developers and advanced users
---

# Reference

In-depth technical documentation covering how RewardsPro works under the hood, API integrations, and definitions.

## Quick Links

<table data-view="cards">
<thead>
<tr>
<th></th>
<th></th>
<th data-hidden data-card-target data-type="content-ref"></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Evaluation Periods</strong></td>
<td>Annual vs Lifetime tier calculations</td>
<td><a href="evaluation-periods.md">evaluation-periods.md</a></td>
</tr>
<tr>
<td><strong>Cashback Logic</strong></td>
<td>How cashback amounts are calculated</td>
<td><a href="cashback-logic.md">cashback-logic.md</a></td>
</tr>
<tr>
<td><strong>API Endpoints</strong></td>
<td>Integration endpoints for developers</td>
<td><a href="api-endpoints.md">api-endpoints.md</a></td>
</tr>
<tr>
<td><strong>Webhooks</strong></td>
<td>Event notifications and processing</td>
<td><a href="webhooks.md">webhooks.md</a></td>
</tr>
</tbody>
</table>

## Technical Reference

### Evaluation Periods
Understanding how tier qualification is calculated:
- **Annual evaluation**: Customer spending resets each year
- **Lifetime evaluation**: Cumulative spending never resets
- **Best practices** for choosing the right approach

### Cashback Logic
Detailed breakdown of cashback calculation:
- Formula and components
- What's included/excluded
- Rounding rules and edge cases

### Multi-Currency Support
How RewardsPro handles different currencies:
- 33 supported currencies
- Exchange rate management
- Display formatting

## Integration

### API Endpoints
Available endpoints for custom integrations:
- Customer data retrieval
- Store credit operations
- Tier information

### Webhooks
Event-driven notifications:
- Order processing events
- Customer updates
- Subscription changes

## Appendix

### Glossary
Definitions of key terms used throughout RewardsPro:
- Tiers, cashback, store credit
- Evaluation periods
- Processing modes

---

{% hint style="info" %}
**Developer?** Check out the [API Endpoints](api-endpoints.md) and [Webhooks](webhooks.md) documentation for integration details.
{% endhint %}
