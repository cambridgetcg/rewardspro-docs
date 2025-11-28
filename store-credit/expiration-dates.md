---
description: Configure and manage store credit expiration policies
---

# Expiration Dates

You can optionally set expiration dates for store credit. When enabled, credit that isn't used by the expiration date becomes void.

## Before Enabling Expiration

{% hint style="warning" %}
**Important Legal Considerations**

Before setting up expiration dates:
- **Check local laws**: Store credit expiration may be prohibited or restricted in some jurisdictions
- **Review regulations**: Some regions require minimum validity periods
- **Consult legal**: When in doubt, seek legal advice for your specific market
{% endhint %}

### Regional Considerations

| Region | Notes |
|--------|-------|
| **US (varies by state)** | Some states prohibit expiration |
| **EU** | Generally allowed with notice |
| **Canada** | Varies by province |
| **UK** | Generally allowed |
| **Australia** | Minimum 3-year validity required |

---

## How Expiration Works

### Timezone Handling

Store credit expires at the **end of the day** in your **store's timezone**, regardless of where the customer is located.

**Example:**
- Store timezone: EST (New York)
- Credit expires: March 10
- Actual expiry: March 10, 11:59:59 PM EST

### Multiple Credits with Different Dates

When a customer has multiple credits with different expiration dates, the system uses **First Expiring, First Out (FEFO)**:

**Example:**
```
Credit A: $10 - Expires March 10
Credit B: $10 - Expires March 15

Customer spends $10 on March 9:
→ Credit A is used (expires first)
→ Credit B ($10, expires March 15) remains
```

This ensures:
- Oldest credits are used first
- Customers don't lose expiring credit
- Fair and transparent usage

---

## Configuring Expiration

### Enabling Expiration

1. Go to **Settings** → **Store Credit**
2. Enable **Credit Expiration**
3. Set default expiration period
4. Save changes

### Expiration Options

| Option | Description |
|--------|-------------|
| **No expiration** | Credit never expires (default) |
| **30 days** | Credit expires in 30 days |
| **60 days** | Credit expires in 60 days |
| **90 days** | Credit expires in 90 days |
| **6 months** | Credit expires in 6 months |
| **12 months** | Credit expires in 12 months |
| **Custom** | Set specific number of days |

### Per-Credit Expiration

When adding credit manually, you can set custom expiration:
1. Add credit to customer
2. Toggle "Set Expiration"
3. Choose specific date
4. Credit expires on that date

---

## Customer Communication

### Balance Display

When expiration is enabled, customers see:
- Current balance
- Expiration date (if applicable)
- Warning when credit is expiring soon

**Widget display:**
```
Store Credit: $25.00
⚠️ $10.00 expires in 5 days
```

### Expiration Reminders

Send automated reminders:

| Timing | Message |
|--------|---------|
| 30 days before | "Your credit expires soon" |
| 7 days before | "Use your credit this week" |
| 1 day before | "Last day to use your credit" |

### Post-Expiration

After credit expires:
- Balance is reduced
- Transaction logged as "Expired"
- Customer notified (optional)

---

## Managing Expired Credit

### Viewing Expired Credit

In transaction history:
- Type: "Expiration"
- Amount: Negative (debit)
- Notes: Original expiration date

### Reinstating Expired Credit

If you need to restore expired credit:
1. Go to customer details
2. Add new credit manually
3. Note reason: "Reinstated expired credit"
4. Set new expiration (if applicable)

### Reporting

Track expiration metrics:
- Total credit expired (period)
- Customers with expiring credit
- Average time to expiration
- Redemption rate before expiry

---

## Best Practices

### Setting Expiration Periods

| Credit Type | Suggested Period |
|-------------|------------------|
| **Cashback earned** | 12 months or no expiration |
| **Promotional bonus** | 30-90 days |
| **Referral credit** | 60-90 days |
| **Service recovery** | 6-12 months |

### Communication

✅ **Do:**
- Clearly state expiration at time of issue
- Send reminders before expiration
- Make policy visible in terms
- Allow customer service exceptions

❌ **Don't:**
- Set very short expiration without notice
- Hide expiration terms
- Refuse all reinstatement requests
- Ignore legal requirements

### Customer Experience

- **Transparency**: Always show expiration dates
- **Fairness**: Give reasonable validity periods
- **Flexibility**: Consider exceptions for loyal customers
- **Reminders**: Notify before credit expires

---

## Troubleshooting

### Credit Expired Unexpectedly

1. Check the expiration date set
2. Verify store timezone settings
3. Review transaction history
4. Reinstate if error found

### Wrong Expiration Date

1. Can't change existing credit expiration
2. Void the credit with adjustment
3. Issue new credit with correct date
4. Document the correction

### Customer Complaints

1. Review transaction history
2. Check if reminders were sent
3. Consider goodwill reinstatement
4. Document outcome for records
