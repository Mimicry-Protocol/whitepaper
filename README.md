---
description: >-
  Mimicry is a decentralized prediction game that helps anyone discover the odds
  of any market.
cover: .gitbook/assets/Twitter Background Pattern 2x.png
coverY: 0
---

# 👨🏫 Protocol Overview

{% hint style="info" %}
**Mimicry's mission is to accelerate universal adoption of free markets.**&#x20;

**We believe this protocol needs to exist so people have a safer alternative to buying and holding illiquid assets like NFTs.**

This protocol operates as a [hyperstructure](https://jacob.energy/hyperstructures.html) and aims to solve common problems within illiquid and inefficient asset classes such as NFTs, distilled spirits, trading cards, and more. For example, we address the following desires:

* I want liquid exposure to \[NFTs, distilled spirits, etc.] as an asset class
* I want an index-like product that lets me short NFT collections, or the entire NFT market
* I want exposure to my favorite NFT collections without having to buy-and-hold any of their NFTs
* I want a simple way to long or short every ERC-20/721/1155 ever created by a specific creator
* I want to better understand the odds of an NFT collection’s market cap going up or down
{% endhint %}

## ✏️  Introduction

Every market on earth has two sides; bulls who think the price of something is going up, and bears who think the price is going down. Very often those two sides disagree about which outcome is more likely and this can lead to inefficient and illiquid markets. **** We’ve developed a novel system that leverages game theory and economic incentives to solve this difficult problem.

### 🎭 Positions and 🎪 Markets

Players in our game can use ERC-20 tokens to open perpetual positions, called <mark style="color:orange;">`Mimes`</mark>, that represent their exposure to one or both sides of a market, which we sometimes call a <mark style="color:orange;">`Pantomime`</mark>.

> **A concrete example of a Mime is:** _<mark style="color:purple;">a perpetual long position opened on 12/15/2022 at 12:01 p.m. GMT within a given Pantomime market, using 1,000 DAI tokens.</mark>_

Mimes gain or lose value as the [reference price](#user-content-fn-1)[^1] for a Pantomime changes relative to the skew of at-risk capital provided by bulls and bears, within their respective long and short positions. All reference prices are known using deterministic on-chain oracle feeds that update when new transaction data is available within a market. Players may choose to have their deposited capital, plus or minus any profits/losses, returned at any time by destroying their Mime and paying a small exit fee to the protocol.

> **A concrete example of a Pantomime Market is:** _<mark style="color:purple;">the market capitalization of the World of Women NFT collection, updated whenever the market capitalization for the entire World of Women collection changes by 0.5%, or once per 60 minutes, whichever comes first.</mark>_

{% hint style="info" %}
Note that most Chainlink price-feeds on the Ethereum Mainnet update whenever there is a 0.5% deviation in the reference price, or once per 60 minutes, whichever comes first. Hence the reference used here.
{% endhint %}

<figure><img src=".gitbook/assets/Screen Shot 2023-02-08 at 12.37.01 PM.png" alt=""><figcaption><p>Mime minting and burning process</p></figcaption></figure>

{% hint style="info" %}
Although Mimes are delivered to player wallets as ERC-721 tokens, they are not the NFTs that were minted as part of a collection like _World of Women_ or _Bored Ape Yacht Club_. A Mime is simply a perpetual position within a market.
{% endhint %}

[^1]: For example, the total market capitalization of the Bored Ape Yacht Club NFT collection.
