---
description: >-
  The Mimicry Protocol consists of a series of open-source smart contracts and a
  GUI web application.
---

# ⚙ Core Mechanics

<figure><img src="../.gitbook/assets/Screen Shot 2023-02-08 at 1.45.43 PM.png" alt=""><figcaption><p>Illustration of Mimicry GUI with description of each component</p></figcaption></figure>

## **🔎 Overview**

Each Pantomime is a smart contract that manages a pool of tokenized collateral supplied by liquidity providers ([Producers](../players-and-participants/producers-liquidity-providers.md)) and traders ([Actors](../players-and-participants/actors-traders.md)) based on the price movement of an on-chain reference-price feed.&#x20;

Theoretically, the skew of collateral deposited into a Pantomime at a given time could be exactly split, 50/50, between bulls and bears. However, in practice this will be rare. More commonly there will be an asymmetric skew of capital, because a group of bullish or bearish Actors will collectively predict that the reference price of a Pantomime will be more likely to go up or down. This creates a situation where the “underdog” side of a pool has less capital at risk than the “favorite” side, and thus each side will have unique odds. We call the unique odds of each side of the market the [True Odds](true-odds.md).
