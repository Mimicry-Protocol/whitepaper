---
description: >-
  Value Transfer Events are the smart contract functions that move ownership
  rights of deposited collateral between players.
---

# 💸 Value Transfer Events

Capital within existing positions are redistributed as part of a Value Transfer Event whenever players add or remove capital from a pool, where the winner’s profits <mark style="color:green;">`p`</mark>, is equal to the True Odds of their side of the pool <mark style="color:green;">`o`</mark>, multiplied by the percentage shift in the reference price since the last Value Transfer Event <mark style="color:green;">`s`</mark>, multiplied by their Mime’s position size <mark style="color:green;">`m`</mark>.&#x20;

$$
p = o*s*m
$$

Conversely, a loser’s losses <mark style="color:green;">`l`</mark>, is equal to the percentage shift in the reference price since the last Value Transfer Event, multiplied by their Mime’s position size, without factoring True Odds at all.

$$
l = s * m
$$

### Token Flow Illustration

The following chart illustrates how tokens might flow between two sides of a Pantomime at different Value Transfer Events.&#x20;

> **In this example:** <mark style="color:purple;">Let’s assume for a given Pantomime that Alice represents all bulls who believe the reference price will rise, and Bob represents all bears who think the price will fall. And they are both using USDT. As you can see below, losers always lose at a 1:1 ratio of reference price movement, while winners earn at the rate of reference price movement relative to their True Odds.</mark>

<table data-header-hidden><thead><tr><th width="114"></th><th width="117"></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td><br></td><td><strong>Reference Price % Change</strong> </td><td><strong>True Odds</strong></td><td><strong>Alice (Long)</strong></td><td><strong>Bob (Short)</strong></td><td><strong>Value Transfer Event</strong></td></tr><tr><td>Time 0</td><td>n/a</td><td>n/a</td><td>100</td><td>0</td><td>Alice opens a position</td></tr><tr><td>Time 1</td><td>n/a</td><td>0.5x vs. 2x</td><td>100</td><td>50</td><td>Bob opens a position</td></tr><tr><td>Time 2</td><td>50%</td><td>0.16x vs. 6.25x</td><td>125</td><td>20</td><td>Bob withdraws 5 USDT</td></tr><tr><td>Time 3</td><td>-50%</td><td>n/a</td><td>62.50</td><td>0</td><td>Bob withdraws 82.50 USDT</td></tr></tbody></table>

{% hint style="success" %}
**Related:** [Skew Change Risk](../risks-and-mitigations/skew-change-risk.md)
{% endhint %}
