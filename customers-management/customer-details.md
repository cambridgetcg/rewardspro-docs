---
description: View complete customer information and manage their loyalty account
---

# Customer Details

Click on any customer in the Customers Page to open the Customer Details modal with comprehensive information and management tools.

## Overview Tab

<figure><img src="../.gitbook/assets/Screenshot 2025-11-19 at 16.21.25.png" alt="Customer Details Overview showing information and tier cards"><figcaption>Customer Overview with key information at a glance</figcaption></figure>

### Customer Information Card

Displays essential customer data:

| Field | Description |
|-------|-------------|
| **Name** | Customer's full name |
| **Email** | Contact email (clickable) |
| **Shopify ID** | Unique customer identifier |
| **Store Credit** | Current balance with currency |
| **Created** | Account creation date |
| **Updated** | Last modification date |

### Tier Details Card

Shows current tier information:

| Field | Description |
|-------|-------------|
| **Current Tier** | Active tier name with badge |
| **Cashback Rate** | Percentage earned on orders |
| **Minimum Spend** | Threshold for current tier |
| **Evaluation** | Annual or Lifetime |
| **Progress** | Progress to next tier |

---

## Store Credit Tab

<figure><img src="../.gitbook/assets/Store Credit.png" alt="Store Credit tab showing balance and transaction history"><figcaption>Store Credit management with full transaction history</figcaption></figure>

### Current Balance Panel

- **Balance Display**: Large, prominent balance amount
- **Currency**: Formatted in your store currency
- **Quick Actions**: Issue credit, deduct credit buttons

### Transaction History Table

Every credit change is recorded:

| Column | Description |
|--------|-------------|
| **Date** | When transaction occurred |
| **Type** | Badge showing transaction type |
| **Amount** | Credit or debit amount |
| **Order** | Associated order (if applicable) |
| **Notes** | Reason or description |

### Transaction Types

| Type | Badge Color | Description |
|------|-------------|-------------|
| `Cashback` | Green | Earned from order |
| `Payment` | Blue | Used at checkout |
| `Refund` | Orange | Refund to credit |
| `Adjustment` | Gray | Manual adjustment |
| `Sync` | Purple | System synchronization |

### Credit Actions

**Add Credit:**
1. Click **Issue Credit**
2. Enter amount
3. Select reason
4. Add note (optional)
5. Confirm

**Deduct Credit:**
1. Click **Deduct Credit**
2. Enter amount
3. Enter reason
4. Confirm

---

## Orders Tab

<figure><img src="../.gitbook/assets/Orders.png" alt="Orders tab showing customer order history"><figcaption>Complete order history with cashback tracking</figcaption></figure>

### Order List Cards

Each order displays:

| Element | Description |
|---------|-------------|
| **Order Name** | Order number (e.g., #1234) |
| **Date** | Order creation timestamp |
| **Status Badges** | Payment and fulfillment status |
| **Total** | Order grand total |
| **Cashback** | Amount earned (if processed) |

### Order Statuses

**Payment Status:**
- ✅ Paid
- ⏳ Pending
- ❌ Refunded

**Fulfillment Status:**
- 📦 Fulfilled
- ⏳ Unfulfilled
- 🔄 Partial

### Expandable Line Items

Click the chevron to reveal:
- Product names
- Quantities
- Line item prices
- Discounts applied

Useful for:
- Reconciling disputes
- Verifying cashback calculation
- Customer service inquiries

---

## Tier Changes Tab

<figure><img src="../.gitbook/assets/Tier Changes.png" alt="Tier Changes tab showing tier history timeline"><figcaption>Complete audit trail of tier changes</figcaption></figure>

### Change Timeline Cards

Each tier change shows:

| Element | Description |
|---------|-------------|
| **Change Type** | Upgrade, Downgrade, Manual Override |
| **From → To** | Previous and new tier badges |
| **Date** | When the change occurred |
| **Trigger** | What caused the change |
| **Notes** | Additional context |

### Change Types

| Type | Description |
|------|-------------|
| **Initial** | First tier assignment |
| **Upgrade** | Moved to higher tier |
| **Downgrade** | Moved to lower tier |
| **Manual** | Admin override |
| **Recalculation** | System recalculated |

### Badge Transitions

Visual representation:
- **From tier** → **To tier** with arrow
- Color-coded to show direction
- Upgrade = green arrow ↑
- Downgrade = red arrow ↓

### Context Information

Additional details shown:
- Trigger type (automation, manual, etc.)
- Total spend at time of change
- Admin who made change (if manual)
- Notes explaining the change

## Quick Actions

From any tab, you can:

| Action | Description |
|--------|-------------|
| **Change Tier** | Manually assign different tier |
| **Add Credit** | Issue store credit |
| **View in Shopify** | Open customer in Shopify admin |
| **Email Customer** | Send email (opens mail client) |

## Best Practices

### When to Review Customer Details

- Before making manual tier changes
- When processing refund requests
- Investigating cashback discrepancies
- VIP customer management

### Audit Trail Usage

The tier changes log helps:
- Verify tier history for disputes
- Track manual overrides
- Audit program integrity
- Report on tier movement
