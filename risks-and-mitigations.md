---
description: >-
  Mimicry is a complex financial instrument and certain risks exist within the
  system.
---

# ⚠ Risks & Mitigations

### Summary

There are several risks in the current architecture, as Mimicry is still an experimental system and complex systems require both empirical observations and theoretical analysis. Empirical observation and theoretical analysis ensure the mechanism design aligns incentives for all players.

### **Price Manipulation Risk**

Perhaps the most notable risk is price manipulation. This may occur if a bad actor mints a new Mimic that is pegged to an NFT collection who's assets can easily be wash traded by the same bad actor. For example this could happen if the actor pegs their Mimic to a collection where they control most or all of the NFTs in that collection. We mitigate this risk by limiting the collections that can be Mimic'd, and through the use of a standardized collection appraisal algorithm.&#x20;

#### Collection Inclusion Algorithm

Best efforts must be taken to prevent bad actors from manipulating collection peg prices. As such, at launch our algorithmic inclusion solution will be conservative in nature and require that NFT collections meet the following criteria:&#x20;

* No wallet owns more than 3% of the collection
* \>= 30 days since first listed
* \>= 5,000 tokens in the collection
* <= 10% of the collection listed for sale
* \>= 1 wallet for every 5 tokens in the collection
* \>= $1M in trading volume during the prior 7 days

This inclusion algorithm will mature over time. New features may include: minimum trading volume requirements in USD terms, certain trend-following measurements, certain social signals, evaluation of historic trades, evaluation of metrics of similar collections, etc. This is a non-exhaustive list of possible improvements.&#x20;

#### Collection Appraisal Algorithm

At launch we will use the time-weighted average pricing (TWAP) from all sales from the prior thirty days. In time we will improve the sophistication of this appraisal algorithm by shifting to a model that mimics the [Card Ladder Player Indexes.](https://drive.google.com/file/d/1rOY3tagsT7axRRxZWECh-0zWoMbaYbNp/view)

### **Data Feed Downtime Risk**

Price data must be reliable in order for the liquidation contracts to be able to function properly. At launch this risk will be present because we are leveraging third-party APIs in order to evaluate price data, and these feeds may experience downtime.

### Centralization Risk

At launch there will be the risk that a government or corporate actor may disrupt services by disabling services that Mimicry depends on for hosting front-end web assets and blockchain relayer nodes. In time this risk will be mitigated with the use of a private relayer node to replace Alchemy and decentralized file storage to replace Google.

### **Data Feed Manipulation Risk**

The the smart contracts that monitor collateral and process liquidations must leverage trustworthy off-chain data when making decisions. Accordingly, we will leverage an oracle for processing information from our collection inclusion and appraisal algorithms.

### **Smart Contract Risks**

Our smart contract code has been written by former smart contract auditors, however, the code has not been audited by third-party auditors. Our contracts remain unaudited for now.&#x20;

### **Macro Economic Risk**

Participants who deposit non-stable collateral are at risk of having their positions reduced due to the value of their underlying collateralized assets reducing in price relative to the price of other collateral deposited into the network.&#x20;
