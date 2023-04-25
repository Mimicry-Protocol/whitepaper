---
description: >-
  The Mimicry contracts are modular, and together comprise the core
  functionality of the network.
---

# Contracts Overview

## Mimicry Protocol

### Mimicry

A contract which keeps track of the markets that have been created, and is responsible for facilitating communication between the markets and the PositionToken contract explained below.

### Market

A contract that defines a market. Primarily used to keep track of positions, as well as acting as the interface between users and markets.

### Accountant

A contract that lives alongside a Market contract and is used to do the math necessary to run value transfer events; as well as other math heavy operations.

### Value Providers

Each Value Provider contract tells the market what the latest value of an asset is. The value provider is used by the market to determine how the value of an asset moved, and to calculate how to transfer funds between the long and short positions.

### Position Token

The ERC721 contract that creates and burns position tokens when positions are opened and closed.

## Off-Chain Reporting Oracle

### Open Markets Oracle

This contract is a catch-all data repository for Mimicry Market data feeds. Our community can use this contract to write new data feeds on chain from secure sources, such as Gelato's web3 functions.
