---
description: How customers view and use their store credit balance
---

# Access Store Credits

Store credit is a balance held in a customer's account that can be applied toward purchases. RewardsPro integrates with Shopify's native store credit system for seamless checkout experiences.

## What is Store Credit?

Store credit is:
- A balance on the customer's Shopify account
- Earned through cashback on purchases
- Can be added manually by merchants
- Usable as payment at checkout
- Tracked with complete transaction history

---

## Customer Access Points

### 1. VIP Status Widget

<figure><img src="../.gitbook/assets/VIP status.png" alt="VIP Status widget showing tier and store credit"><figcaption>Customers see their status and balance in the storefront widget</figcaption></figure>

The customer-facing widget displays:

| Element | Description |
|---------|-------------|
| **Tier Badge** | Current loyalty tier with icon |
| **Cashback Rate** | Percentage they earn on orders |
| **Store Credit** | Current available balance |
| **Progress** | Progress toward next tier |

**Widget Location:**
- Floating button on storefront
- Opens to show full status
- Updates in real-time

### 2. Merchant's Customer Portal

<figure><img src="../.gitbook/assets/StoreCredit_Customers.png" alt="Store Credit in Shopify customer portal"><figcaption>Store credit visible in customer account pages</figcaption></figure>

**Customer-level balance:**
- Stored on the Customer resource in Shopify
- Each customer has a StoreCreditAccount
- Running balance updated with each transaction

**Accessed through:**
- Shopify customer account pages
- Order confirmation emails (if configured)
- Account dashboard

### 3. Transaction Ledger

<figure><img src="../.gitbook/assets/Store Credit Ledger.png" alt="Store Credit transaction ledger"><figcaption>Complete history of credit and debit entries</figcaption></figure>

All changes are recorded as **ledger entries**:

| Entry Type | Direction | Examples |
|------------|-----------|----------|
| **Credit** | + Add | Cashback, refunds, promotions |
| **Debit** | - Subtract | Checkout redemption |

**Ledger benefits:**
- Complete audit trail
- Transparent to customers
- Useful for disputes
- Required for accounting

---

## Using Store Credit at Checkout

### Step 1: View Available Credit

<figure><img src="../.gitbook/assets/Customer_Checkout_1.png" alt="Checkout page showing store credit option"><figcaption>Store credit appears as a payment option</figcaption></figure>

At checkout, customers see:
- Available store credit balance
- Option to apply credit
- Remaining balance after use

### Step 2: Apply Credit

<figure><img src="../.gitbook/assets/Customer_Checkout_2.png" alt="Store credit being applied at checkout"><figcaption>Credit is automatically deducted from total</figcaption></figure>

**Application options:**
- Apply full balance
- Apply partial amount
- Combine with other payment

**What happens:**
1. Customer clicks "Apply Store Credit"
2. Amount deducted from order total
3. Remaining paid by card/other method
4. Balance updated immediately

---

## Balance Display

### In Widget

```
┌─────────────────────────┐
│ 💰 Store Credit         │
│                         │
│      $45.50             │
│    Available Balance    │
│                         │
└─────────────────────────┘
```

### In Account

Customers see on their account page:
- Current balance
- Recent transactions
- Link to full history

### In Checkout

During checkout:
- Balance available to apply
- Clear apply/remove buttons
- Updated total after applying

---

## Currency Handling

### Store Currency

- Credit is stored in store currency
- Displayed in store currency format
- Proper symbol and decimal handling

### Multi-Currency Stores

If your store uses multiple currencies:
- Credit stored in base currency
- Displayed in customer's local currency
- Converted at current rates

---

## Best Practices

### For Merchants

✅ **Do:**
- Make balance visible in widget
- Remind customers of credit in emails
- Train support on credit inquiries
- Monitor outstanding balances

❌ **Don't:**
- Hide credit information
- Make redemption difficult
- Forget to sync balances
- Ignore credit disputes

### For Customer Experience

- **Visibility**: Ensure customers can easily see their balance
- **Reminders**: Email about unused credit periodically
- **Ease of Use**: One-click apply at checkout
- **Transparency**: Show how credit was earned

---

## Troubleshooting

### Customer Can't See Balance

1. Verify they're logged in
2. Check widget is enabled
3. Confirm balance exists
4. Clear browser cache

### Balance Not Updating

1. Check for processing delays
2. Verify order was paid
3. Review transaction history
4. Sync with Shopify if needed

### Can't Apply at Checkout

1. Ensure sufficient balance
2. Check for minimum order requirements
3. Verify checkout settings
4. Test with admin account
