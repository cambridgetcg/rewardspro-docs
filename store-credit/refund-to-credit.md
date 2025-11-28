---
description: Convert order refunds into store credit instead of card refunds
---

# Refund to Store Credit

Instead of processing a traditional refund to the customer's payment method, you can convert refunds into store credit, keeping the value within your store's ecosystem.

## Benefits of Refund to Credit

| Benefit | Description |
|---------|-------------|
| **Retain Revenue** | Money stays in your store |
| **Faster Processing** | Instant vs. 5-10 day card refund |
| **Customer Convenience** | Immediately usable |
| **Reduced Fees** | Avoid payment processor fees |
| **Loyalty Building** | Encourages return purchase |

---

## When to Offer

### Good Candidates

| Scenario | Why Offer Credit |
|----------|------------------|
| **Size exchange** | Customer will reorder |
| **Minor defect** | Partial credit as goodwill |
| **Shipping delay** | Compensation for inconvenience |
| **Customer preference** | They request store credit |
| **Return without product** | When item can't be returned |

### Consider Traditional Refund

| Scenario | Why Card Refund |
|----------|-----------------|
| **Customer insists** | Respect their preference |
| **Large amount** | May prefer original payment method |
| **Closing account** | Won't shop again |
| **Legal requirement** | Some jurisdictions require option |

---

## How to Process

### From Customer Details

1. Open customer from Customers page
2. Go to **Store Credit** tab
3. Click **Refund to Store Credit**
4. Select the order
5. Enter amount (full or partial)
6. Add reason/notes
7. Confirm

### From Orders Page

1. Go to **Orders**
2. Find the order
3. Click **Refund to Credit**
4. Enter amount
5. Confirm

---

## Refund Options

### Full Refund to Credit

Convert entire order value to store credit:

```
Order Total: $150.00
Refund to Credit: $150.00
New Balance: +$150.00
```

### Partial Refund to Credit

Refund specific amount:

```
Order Total: $150.00
Partial Refund: $50.00
New Balance: +$50.00
Order Status: Partially Refunded
```

### Split Refund

Combine methods:
- Part to store credit
- Part to original payment

---

## Transaction Recording

When processing refund to credit:

| Field | Value |
|-------|-------|
| **Type** | Refund Credit |
| **Amount** | + Positive (credit) |
| **Reference** | Order number |
| **Notes** | Refund reason |

### Audit Trail

The transaction shows:
- Original order reference
- Refund amount
- Who processed it
- Timestamp
- Reason provided

---

## Customer Communication

### Automatic Notification

Customer receives:
- Email confirmation of refund
- New balance amount
- How to use the credit

### Suggested Message

> "We've processed your refund of $50.00 as store credit, which has been added to your account. Your new balance is $75.00. This credit can be applied at checkout on your next order."

---

## Best Practices

### Processing

✅ **Do:**
- Explain benefits to customer
- Get consent when possible
- Process promptly
- Document the reason
- Confirm with customer

❌ **Don't:**
- Force credit without consent
- Delay processing
- Skip documentation
- Forget to communicate

### Offering to Customers

**Good approach:**
> "I can process this as store credit, which will be available immediately. Would you prefer that, or a refund to your original payment method (which takes 5-10 business days)?"

**Avoid:**
> "We only do store credit refunds." (unless policy clearly states this)

---

## Policies

### Consider Having Clear Policy

- State options in return policy
- Clarify which situations get credit vs. refund
- Be consistent in application
- Train customer service team

### Sample Policy Language

> "Refunds may be issued as store credit or to your original payment method. Store credit is available immediately, while card refunds may take 5-10 business days to process."

---

## Reporting

### Track Refund to Credit Metrics

| Metric | What It Shows |
|--------|---------------|
| **Total Refund Credits** | Amount converted to credit |
| **Refund Credit Rate** | % of refunds as credit |
| **Redemption Rate** | % of refund credit used |
| **Average Time to Use** | Days until credit is spent |

### Why Track

- Understand revenue retention
- Measure customer return rate
- Optimize refund policies
- Plan for credit liability
