# Vendor markup

When a vendor decides to integrate their platform with the MoC ecosystem, they must be registered first. Then, they will receive a markup for every transaction they are involved in (denoted by the parameter **vendorAccount**).

If the user who makes the transaction has balance and allowance of MoC token, this markup will be charged in MoC; otherwise it will be charged in RBTC. The exact percentage of the markup cannot be more than 1%. This is set in the **vendors** mapping of the **MoCVendors** contract (the vendor account address is the key), and the value to check is **markup**.

Note that the markup has also a precision of 18 decimals, i.e. a 1 \* 10^15 in that parameter means that 0.1% is being charged as a commission.
