---
description: >-
  Leverage in Mimicry is unique, in that, players can never go into debt and
  there is never any need for the system to manage liquidations.
---

# 🎚 Leverage

When Actors open positions with leverage <mark style="color:green;">`L`</mark>, their Mime’s position size <mark style="color:green;">`s`</mark>, will equal their deposited capital <mark style="color:green;">`c`</mark>, multiplied by their selected leverage between an integer range of 1-30.

$$
s = c * L
$$

Levered positions respond to Pantomime reference-price changes in accordance with their leverage.

> **For example:** <mark style="color:purple;">Let’s assume the True Odds within a hypothetical market are 1:1. A bullish Mime with a $1,000 worth of tokens, previously opened by Alice using 5x leverage, will impact the skew as if $5,000 worth of collateral was deposited on the bullish side of the market. Accordingly, a 10% change in the reference price in this hypothetical example would yield a gain of $500.</mark>&#x20;

{% hint style="info" %}
The leveraged size of a position will be used when calculating [exit fees](../fees.md#exit-fees). So assuming a 0.5% exit fee for the hypothetical Pantomime above, Alice would pay the protocol $27.50 worth of tokens to close her position. The value returned to Alice would be her original deposit of $1,000, plus $472.50 in profits.&#x20;
{% endhint %}

{% hint style="success" %}
**Related:** [Leverage Risk](../risks-and-mitigations/leverage-risk.md) and [Liquidation Risk](../risks-and-mitigations/liquidation-risk.md)
{% endhint %}
