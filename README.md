---
description: Mimicry is a decentralized derivatives protocol for NFT collections.
---

# 👨🏫 Protocol Overview

{% hint style="info" %}
**Mimicry's mission is to help protect speculators from getting rekt. We believe this protocol needs to exist so people have a safer alternative to buying and holding NFTs.**

This protocol aims to solve the following problems:

* I want to invest in an expensive NFT collection but I can't afford to buy any
* I want an NFT portfolio that is _actually_ liquid
* I want to bundle NFT indexes by artist, utility, visual features, etc.
* I want to short the NFT market
* I want to build trade bots for NFTs using social media sentiment indicators
{% endhint %}

### Introduction

`Mimics` are fully-collateralized derivative tokens on Polygon that leverage oracles to mirror the appraised price NFT collections. Anyone can mint new Mimics using the Mimicry platform. Mimics are collateralized by ERC-20 tokens. Network participants may collateralize their positions using the Mimicry Network Token ($MIME) to receive rewards.

Mimicry is inspired by the Synthentix protocol's pooled collateral model. Mimics may be traded with infinite liquidity and zero slippage due to their relative P\&L algorithm against the global collateral pool. Trades between Mimics generate a small fee. This mechanism effectively solves the liquidity issues that plague NFT investors.

### Why is this needed?

![Gary V on NFTs](<.gitbook/assets/GaryVee on NFTs (1).png>)

### Why Not Just Use Synthetix?

Mimicry would not exist without the prior work of the Synthetix team, and so it almost goes without saying that we are extremely grateful for their work. However, there are several notable differences between the two protocols:

1. Mimicry is designed to mimic non-fungibles, where Sythentix is designed primarily with fungible tokens in mind. We believe the nature of the game of the global debt pool necessitates two distinct networks.
2. We use a different profit and loss algorithm.
3. Synthetix has no mechanism available for depositors to be able to rapidly create new Synths that mimic the floor price of an NFT collection. Instead the network requires an improvement proposal and DAO vote in order to introduce each new synth.
4. Synthetix requires that participants begin with $SNX and mint sUSD, and then swap sUSD for another synth. We believe this UX can be simplified and aim to do so by allowing Mimicry participants to use a wide array of ERC-20 tokens to mint any Mimic.
5. Synthetix is designed to scale using Optimism, while Mimicry is built for Polygon.
