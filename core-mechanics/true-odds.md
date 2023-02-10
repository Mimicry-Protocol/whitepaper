---
description: >-
  True Odds describe how likely "the street" thinks it is for a market's
  reference price to move up or down in the future.
---

# 🎲 True Odds

The True Odds for each side of a Pantomime functions as a multiplier, where, all things being equal, a player's deposited collateral will grow by a rate equal to the True Odds every time the reference price for the Pantomime in question doubles.&#x20;

> **For example:** <mark style="color:purple;">Let's assume there is a market with $1M long and $2M short. The Short Side's True Odds would be 0.5x, and the Long Side's True Odds would be 2.0x. So, all other things being equal, a long position would double in value if the reference price for this fictional market were to increase by 50%.</mark>

### Calculating True Odds

Within a Pantomime, the long side's True Odds <mark style="color:green;">`Lto`</mark>, is equal to capital in the short pool <mark style="color:green;">`sp`</mark>, divided by the capital in the long pool <mark style="color:green;">`lp`</mark>.

$$
Lto = sp / lp
$$

Within a Pantomime, the short side's True Odds <mark style="color:green;">`Sto`</mark>, is equal to capital in the long pool <mark style="color:green;">`lp`</mark>, divided by the capital in the short pool <mark style="color:green;">`sp`</mark>.

$$
Sto = lp/sp
$$
