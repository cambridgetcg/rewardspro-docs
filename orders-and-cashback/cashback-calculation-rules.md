# Cashback Calculation Rules

**Cashback Calculation Rules & Formula**

* **Eligibility**: the order must belong to a known customer (Shopify ID match) and the customer must have an active tier; guest checkouts or customers without a tier earn `0` cashback.



* **Net amount basis**: calculations use the order subtotal minus Shopify discounts, and exclude tax and shipping so incentives only apply to merchandise value.



* **Tier-driven percent**: each tier defines a `cashbackPercent`; the system captures the tier ID/name at order time so historical payouts remain auditable even after tier changes.



* **Formula**:\
  \[ {Cashback Amount} = ({Subtotal} - {Discounts}) \times \frac\{{Cashback Percent\}}{100} ]&#x20;

Example: $100 subtotal with $10 discounts and a 5% tier:

$$
(100-10)*0.05=4.5
$$
