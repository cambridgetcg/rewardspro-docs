---
description: View and manage all orders with cashback tracking
---

# Orders Page

The Orders page displays all customer orders synced from Shopify with their cashback status, allowing you to monitor processing and take action when needed.

---

## Page Overview

### Order List

Each order displays:

| Column | Description |
|--------|-------------|
| **Order Number** | Shopify order name (e.g., #1234) |
| **Date** | Order creation date in Shopify |
| **Customer** | Customer name and email |
| **Tier at Order** | Customer's tier when order was placed |
| **Total** | Order total paid by customer |
| **Cashback** | Amount earned (cashbackAmount) |
| **Status** | Financial and processing status |

### Order Data Fields

RewardsPro tracks comprehensive financial data for each order:

| Field | Description |
|-------|-------------|
| **subtotalPrice** | Sum of line item prices before discounts |
| **totalDiscounts** | All discounts applied to order |
| **totalShipping** | Shipping cost |
| **totalTax** | Tax amount |
| **totalPrice** | Final amount paid by customer |
| **totalRefunded** | Amount refunded (if any) |
| **netAmount** | totalPrice - totalRefunded |
| **cashbackPercent** | Tier cashback rate at time of order |
| **cashbackAmount** | Calculated cashback earned |
| **cashbackProcessed** | Whether cashback has been credited |

### Financial Status

| Status | Badge | Meaning |
|--------|-------|---------|
| `PAID` | Green | Payment complete, cashback eligible |
| `PENDING` | Yellow | Awaiting payment |
| `AUTHORIZED` | Blue | Payment authorized, not captured |
| `PARTIALLY_PAID` | Orange | Partial payment received |
| `PARTIALLY_REFUNDED` | Purple | Some items refunded |
| `REFUNDED` | Gray | Fully refunded |
| `VOIDED` | Red | Order voided |

### Cashback Status

| Status | Badge | Meaning |
|--------|-------|---------|
| ✅ Processed | Green | Cashback credited to customer |
| ⏳ Pending | Yellow | Order paid, awaiting processing |
| ❌ Not Eligible | Gray | Guest order or excluded products |
| 🔄 Clawed Back | Orange | Cashback reversed due to refund |

---

## Filtering Orders

### By Status

- **All Orders**: Complete list
- **Processed**: Successfully awarded
- **Pending**: Awaiting action
- **Failed**: Need attention

### By Date

- Today
- Last 7 days
- Last 30 days
- Custom date range

### By Customer

Search by:
- Customer name
- Customer email
- Order number

---

## Order Actions

### Process Cashback

For pending orders in manual mode:
1. Review order details
2. Verify customer and amount
3. Click **Process**
4. Confirm cashback award

### Reverse Cashback

If cashback needs to be reversed:
1. Find the processed order
2. Click **Reverse**
3. Enter reason
4. Confirm reversal

### Recalculate

If tier or settings changed:
1. Select order
2. Click **Recalculate**
3. Review new amount
4. Process if different

---

## Order Details

Click any order to see:

### Order Information
- Full order number
- Customer details
- Order date and time
- Payment status
- Fulfillment status

### Line Items
- Products ordered
- Quantities
- Prices
- Discounts applied

### Cashback Details
- Eligible amount
- Tier at time of order
- Cashback rate
- Calculated amount
- Processing status

---

## Bulk Operations

### Select Multiple Orders

1. Use checkboxes to select
2. Or "Select All" on page

### Bulk Actions

| Action | Use For |
|--------|---------|
| **Process All** | Approve pending orders |
| **Export** | Download to CSV |

---

## Monitoring & Alerts

### Dashboard Metrics

- Orders processed today
- Total cashback issued
- Pending queue size
- Failed orders count

### Alerts

Get notified for:
- Processing failures
- High-value cashback
- Unusual patterns

---

## Best Practices

### Daily Review

- Check failed orders
- Process pending queue (manual mode)
- Monitor cashback totals
- Investigate anomalies

### Weekly Audit

- Review processing accuracy
- Check for missed orders
- Verify customer balances
- Export reports

---

## Troubleshooting

### Order Not Showing

1. Check date filter
2. Verify order is paid
3. Sync with Shopify
4. Check customer account exists

### Wrong Cashback Amount

1. Review tier at order time
2. Check for excluded products
3. Verify discount handling
4. Recalculate if needed

### Processing Failed

1. Check error message
2. Verify customer has account
3. Check tier assignment
4. Process manually if needed
