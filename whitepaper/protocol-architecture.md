---
description: >-
  Eventually our contracts will be open-sourced and upgradability will be
  removed. For now we're publishing notes here.
---

# 👨💻 Contract Architecture

### How Data Flows

Players may take positions by selecting a number of variables and depositing ERC-20 collateral. New positions are represented as ERC-721 tokens (Mimes).&#x20;

![Mimicry data flow diagram](<../.gitbook/assets/Mimicry Swim Lanes (2).png>)

### Mimics as NFTs

Each minted Mimic will contain specialized metadata written to the blockchain. When rendered within a wallet, that data, along with real-time performance information, will be visible in the NFT itself. Some of the data recorded may include:

* The NFT collection to peg value against
* The direction of the collection's price prediction (long or short)
* The USD liquidation value of the position, after fees
* The amount of profit, expressed as a percentage
* The amount of rewards earned

| ![](<../.gitbook/assets/nft card (1).png>) | ![](<../.gitbook/assets/Frame 108.png>) |
| ------------------------------------------ | --------------------------------------- |

