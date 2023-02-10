---
description: >-
  Balancers call public smart contract functions to rebalance two-sided Producer
  positions and help automate advanced trading features for Actors.
---

# ⚖ Balancers (Keepers)

The second-to-last subset of players in our game are Balancers. Balancers serve a critical role, which is to rebalance the Producers’ positions to match the True Odds of a Pantomime anytime the Pantomime bull vs bear skew changes beyond a threshold perviously set by a Producer at the time that the Producer opened their Mime position.&#x20;

Skew changes can happen anytime (a) Actors add or remove capital, (b) the value of the ERC-20 tokens deposited within a Pantomime change in USD terms, or (c) a Pantomime’s reference price deviates. This mechanic causes Producers’ positions to remain as close to delta-neutral as possible by continuously moving part of their deposited collateral from long to short, or short to long, as appropriate based on the True Odds in a pool.&#x20;

A detailed illustration of this rebalancing mechanism is as follow…

{% embed url="https://docs.google.com/spreadsheets/d/1lhXid1p62Dum8wF61xRZpf7x2uKZWINEsJtqUiRf6KY/edit#gid=1919431724" %}
Detailed illustration of Producer rebalancing
{% endembed %}

Producers pay Balancers a [tip](../fees.md#balancer-fees) in exchange for Balancers hosting and maintaining servers that automate the process of monitoring Pantomime health and paying gas costs to call a smart contract function which rebalances a Producer’s assets, where Producers may specify that the more time a Producer’s position spends out of balance, the greater the tip. An economic disincentive will prevent Balancers from rebalancing Pantomime liquidity when their tip will not exceed their gas and operational costs, and at the same time game theory will also prevent greedy Balancers from waiting to rebalance a Pantomime until it is far out of balance because Balancers effectively race each other to win tips.&#x20;

Balancers may also [earn fees](../fees.md#balancer-fees) by triggering [automated events](../advanced-features/automations/) for the benefit of Actors.

{% hint style="success" %}
**Related:** [Balancer Shortage Risk](../risks-and-mitigations/balancer-shortage-risk.md)
{% endhint %}
