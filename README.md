---
description: Mimicry is a decentralized derivatives protocol for NFT collections.
---

# 👨🏫 Protocol Overview



{% hint style="info" %}
**Mimicry's mission is to unlock illiquid markets. We believe this protocol needs to exist so that retail speculators have a safer alternative to buying and holding NFTs.**

This protocol aims to solve the following problems:&#x20;

* I want to invest in Punks & BAYCs but I can't afford to buy any
* I want an NFT portfolio that is _actually_ liquid
* I want to bundle NFT indexes by artist, utility, visual features, etc.
* I want to short the NFT market
* I want to build trade bots for NFTs using social media sentiment indicators
{% endhint %}

### Introduction

`Mimics` are fully-collateralized derivative tokens on Polygon that leverage oracles to mirror the floor price of one or more NFT collections on OpenSea. Anyone can mint new Mimics using the Mimicry platform. Mimics are collateralized by the Mimicry Network Token ($MIMIC).

Mimicry is inspired by the Synthentix protocol's pooled collateral model, allowing Mimics to be traded with near infinite liquidity and zero slippage. Trades between Mimics generate a small fee that is distributed to $MIMIC collateral providers. This counterpartyless mechanism solves the liquidity issues that plague NFT investors.

### Why is this needed?

![Gary V on NFTs](<.gitbook/assets/GaryVee on NFTs (1).png>)

### Why Not Just Use Synthetix?

Mimicry would not exist without the prior work of the Synthetix team, and so it almost goes without saying that we are extremely grateful for their work. However, there are several notable differences between the two protocols:&#x20;

1. First, Mimicry is designed to mimic NFTs exclusively, where Sythentix is designed primarily with ERC20 tokens, commodities, and stocks in mind. We believe the nature of the game of the global debt pool necessitates two distinct networks.
2. Second, Synthetix has a very limited number of synthetic assets, and there is no mechanism available for depositors to be able to rapidly create new Synths that mimic the floor price of an NFT collection.
3. Synthetix is designed to scale using Optimism, while Mimicry is built for Polygon.
