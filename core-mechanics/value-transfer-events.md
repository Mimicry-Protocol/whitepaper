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

| <p><br></p> | **Reference Price % Change**  | **True Odds**   | **Alice (Long)** | **Bob (Short)** | **Value Transfer Event** |
| ----------- | ----------------------------- | --------------- | ---------------- | --------------- | ------------------------ |
| Time 0      | n/a                           | n/a             | 100              | 0               | Alice opens a position   |
| Time 1      | n/a                           | 0.5x vs. 2x     | 100              | 50              | Bob opens a position     |
| Time 2      | 50%                           | 0.16x vs. 6.25x | 125              | 20              | Bob withdraws 5 USDT     |
| Time 3      | -50%                          | n/a             | 62.50            | 0               | Bob withdraws 82.50 USDT |

{% hint style="success" %}
**Related:** [Skew Change Risk](../risks-and-mitigations/skew-change-risk.md)
{% endhint %}
