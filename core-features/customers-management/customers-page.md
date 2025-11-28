---
description: Manage all your loyalty program members from the Customers Page
---

# Customers Page

<figure><img src="../.gitbook/assets/Customers Page.png" alt="RewardsPro Customers Page showing customer list with tiers and balances"><figcaption>The Customers Page is your central hub for managing loyalty members</figcaption></figure>

The Customers Page displays all customers synced from your Shopify store, allowing you to manage their loyalty status, view balances, and take actions.

---

## Page Overview

### Customer List

Each customer row displays:

| Column | Description |
|--------|-------------|
| **Name** | Customer's full name (firstName + lastName) |
| **Email** | Contact email address |
| **Tier** | Current loyalty tier with colored badge and icon |
| **Store Credit** | Available balance in your store currency |
| **Total Spent** | All-time spending (or annual, based on evaluation) |
| **Order Count** | Number of orders placed |
| **Last Order** | Date of most recent order |

### Customer Data Fields

RewardsPro tracks comprehensive data for each customer:

| Field | Description |
|-------|-------------|
| **storeCredit** | Current available store credit balance |
| **pointsBalance** | Current loyalty points balance |
| **lifetimePoints** | Total points ever earned |
| **totalSpent** | All-time order value |
| **annualSpent** | Spending in last 12 months (for tier calculation) |
| **netSpent** | totalSpent minus refunds |
| **totalCashbackEarned** | All cashback earned over time |
| **totalRefunded** | Total refund amount received |
| **orderCount** | Number of orders |
| **lastOrderDate** | Most recent order date |
| **tags** | Shopify customer tags (synced) |

### Quick Actions

From the customer list you can:
- Click a row to open **Customer Details** modal
- Use checkboxes for **bulk actions**
- Access **quick tier assignment**
- **Sync** button to refresh data from Shopify

---

## Search & Filter

### Search Box

Find customers quickly by:
- First name or last name
- Email address
- Partial matches supported
- Customer tags

### Filter Options

| Filter | Options |
|--------|---------|
| **Tier** | All tiers, or select specific tier |
| **Balance** | Has balance, No balance |
| **Spend Range** | Custom min/max amount |
| **Order Count** | Minimum orders placed |

### Sorting

Sort the list by:
- Name (A-Z, Z-A)
- Store Credit (High to Low, Low to High)
- Total Spent (High to Low, Low to High)
- Order Count (Most to Least)
- Last Order (Newest, Oldest)
- Created Date (Newest, Oldest)

## Syncing Customers

### Initial Sync

First time using RewardsPro:
1. Click the **Sync Customers** button
2. Wait for the sync to complete
3. All Shopify customers are imported

### Automatic Sync

New customers are automatically added when:
- They create a Shopify account
- They place their first order

### Manual Refresh

Click **Sync** anytime to:
- Pull latest customer data from Shopify
- Update names and emails
- Sync new customers

## Pagination

For stores with many customers:
- Default: 25 customers per page
- Navigate with Previous/Next buttons
- Jump to specific page numbers
- Total count displayed

## Bulk Operations

### Select Multiple Customers

1. Use checkboxes to select customers
2. Or use "Select All" on current page

### Available Bulk Actions

| Action | Description |
|--------|-------------|
| **Assign Tier** | Move selected to specific tier |
| **Export** | Download as CSV |

## Best Practices

### Regular Review

- Check for customers approaching tier upgrades
- Monitor inactive customers for re-engagement
- Review high-balance customers

### Data Hygiene

- Sync regularly to keep data current
- Clean up duplicate customers in Shopify
- Verify tier assignments after bulk changes

## Next Steps

- [Customer Details](customer-details.md) - Deep dive into individual customers
- [Manually Assign Tiers](manually-assign-tiers.md) - Override automatic tier assignment
- [Edit Store Credits](manually-edit-store-credits.md) - Add or remove credit
