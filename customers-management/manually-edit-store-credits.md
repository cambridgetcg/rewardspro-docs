---
description: Add or remove store credit from customer accounts
---

# Manually Edit Store Credits

Merchants can manually adjust store credit balances for goodwill credits, corrections, promotions, or other business needs.

## When to Edit Store Credit

| Scenario | Action | Example |
|----------|--------|---------|
| **Service recovery** | Add credit | $10 for shipping delay |
| **Promotional bonus** | Add credit | $25 welcome bonus |
| **Correction** | Add/Remove | Fix calculation error |
| **Contest winner** | Add credit | $100 prize |
| **Fraud prevention** | Remove credit | Suspicious activity |
| **Refund alternative** | Add credit | Convert refund to credit |

## Adding Store Credit

{% stepper %}
{% step %}
### Navigate to Store Credit Tab

<figure><img src="../.gitbook/assets/Store Credit.png" alt="Store Credit tab in Customer Details"><figcaption>Access the Store Credit tab in Customer Details</figcaption></figure>

1. Open the customer from Customers page
2. Click on **Store Credit** tab
3. View current balance and history

{% endstep %}

{% step %}
### Click Add Credit

<figure><img src="../.gitbook/assets/Add Credit.png" alt="Add Credit modal with amount and reason fields"><figcaption>Enter the credit amount and reason</figcaption></figure>

**Required fields:**

| Field | Description | Example |
|-------|-------------|---------|
| **Amount** | Credit to add | $25.00 |
| **Reason** | Select from dropdown | Goodwill / Promotional / Other |
| **Note** | Additional details | "Late delivery compensation" |

{% endstep %}

{% step %}
### Confirm and Verify

After adding:
- ✅ Balance updates immediately
- ✅ Transaction appears in history
- ✅ Customer can use credit at checkout

{% endstep %}
{% endstepper %}

## Removing Store Credit

Use with caution - removing credit should be documented clearly.

**Process:**
1. Open customer details → Store Credit tab
2. Click **Deduct Credit**
3. Enter amount to remove
4. Enter mandatory reason
5. Confirm deduction

**Common reasons for removal:**
- Correction of erroneous credit
- Fraud investigation
- Account cleanup
- Customer request

## Reason Categories

### Predefined Reasons

| Reason | Use For |
|--------|---------|
| **Goodwill** | Service recovery, customer satisfaction |
| **Promotional** | Campaigns, welcome bonuses |
| **Referral** | Referral program rewards |
| **Adjustment** | Corrections, reconciliation |
| **Refund** | Converting refund to credit |
| **Other** | Custom situations |

### Custom Notes

Always add detailed notes:
- **Who** authorized the credit
- **Why** it was issued
- **Reference** ticket/order numbers

**Example notes:**
- "Service recovery per ticket #12345 - shipping delay"
- "Q4 promotion: Holiday bonus for Gold members"
- "Correction: duplicate cashback from order #5678"

## Refund to Store Credit

A special workflow for converting order refunds to store credit:

1. Open customer details
2. Click **Refund to Store Credit**
3. Select the order to refund
4. Choose full or partial amount
5. Credit is added with order reference

**Benefits:**
- Keeps money in your ecosystem
- Faster than card refund
- Customer can use immediately

## Transaction History

Every credit change is logged:

| Field | Description |
|-------|-------------|
| **Date/Time** | Exact timestamp |
| **Type** | Adjustment, Refund, etc. |
| **Amount** | + or - value |
| **Balance** | Running balance after |
| **Reference** | Order or note |
| **Admin** | Who made the change |

### Exporting History

1. Go to Store Credit tab
2. Click **Export**
3. Download CSV with all transactions

Useful for:
- Accounting reconciliation
- Audit compliance
- Customer service records

## Best Practices

### Adding Credit

✅ **Do:**
- Document the reason clearly
- Use appropriate reason category
- Include reference numbers
- Notify customer when appropriate

❌ **Don't:**
- Add credit without documentation
- Use vague reasons like "test"
- Forget to verify the update
- Over-credit accounts

### Removing Credit

✅ **Do:**
- Double-check before removing
- Document thoroughly
- Get approval if large amount
- Consider customer notification

❌ **Don't:**
- Remove without clear reason
- Remove disputed credit without review
- Forget to log the action

## Bulk Credit Operations

For adding credit to multiple customers:

1. **Export** customer list to CSV
2. **Prepare** list of emails and amounts
3. Contact **support** for bulk upload
4. **Verify** after processing

Use cases:
- Promotional campaigns
- Loyalty program migrations
- Mass corrections

## Impact on Reports

Manual credits affect:

| Report | Impact |
|--------|--------|
| **Total Issued** | Increases with additions |
| **Outstanding Balance** | Changes with any edit |
| **Credit by Type** | Categorized separately |
| **Customer LTV** | May affect calculations |

Manual adjustments are tracked separately from automatic cashback for accurate reporting.
