---
description: >-
  Mimicry is an exceptionally complex financial instrument and certain risks
  exist within the system.
---

# ⚠ Risks & Mitigations

### Summary

There are several risks in the current architecture, as Mimicry is still an experimental system and complex systems require both empirical observations and theoretical analysis. Empirical observation and theoretical analysis ensure the mechanism design aligns incentives for all players.

### **Price Manipulation Risk**

Perhaps the most notable risk is price manipulation. This may occur if a bad actor mints a new Mimic that is pegged to an NFT collection who's assets can easily be wash traded by the same bad actor. For example this could happen if the actor pegs their Mimic to a collection where they control most or all of the NFTs in that collection. We mitigate this risk by limiting the collections that can be Mimic'd, and through the use of a standardized collection appraisal algorithm.&#x20;

#### Collection Inclusion Algorithm

Best efforts must be taken to prevent bad actors from manipulating collection peg prices. As such, at launch our algorithmic inclusion solution will be conservative in nature and require that NFT collections meet the following criteria:&#x20;

* OpenSea verified
* No wallet owns more than 3% of the collection
* \>= 30 days since first listed
* \>= 5,000 tokens in the collection
* \>= 10% of the collection listed for sale
* \>= 1 wallet for every 5 tokens in the collection
* \>= 0.5% of the total tokens traded within the last seven days
* \>= $1M in trading volume during the prior 7 days

This inclusion algorithm will mature over time through the use of machine learning. New features for the forthcoming ML algorithms may include: minimum trading volume requirements in USD terms, certain trend-following measurements, certain social signals, evaluation of historic trades, evaluation of metrics of similar collections, etc. This is a non-exhaustive list of possible improvements.&#x20;

#### Collection Appraisal Algorithm

At launch we will use the time-weighted average pricing (TWAP) from all sales from the prior thirty days. In time we will improve the sophistication of this appraisal algorithm by shifting to a volume-weighted average pricing (VWAP) and removing the outlier transactions, represented as the top and bottom 5% of transactions when ordered by price in USD. Additionally we will also analyze all items for sale by each owner and determine the average floor price amongst their collection tokens that have been listed for sale for at least 24 hours ("Owner Floors"). We'll then determine the average floor price of the bottom 20% of Owner Floors. This value will be multiplied by the TWAP, less outliers. The final value will be the v2 collection appraisal peg.

### **Data Feed Downtime Risk**

Price data must be reliable in order for the liquidation contracts to be able to function properly. At launch this risk will be present because we are leveraging third-party APIs in order to evaluate price data, and these feeds may experience downtime.

### Centralization Risk

At launch there will be the risk that a government or corporate actor may disrupt services by disabling services that Mimicry depends on for hosting front-end web assets and blockchain relayer nodes. In time this risk will be mitigated with the use of a private relayer node to replace Alchemy and decentralized file storage to replace Google.

### **Data Feed Manipulation Risk**

The the smart contracts that monitor collateral and process liquidations must leverage trustworthy off-chain data when making decisions. Accordingly, we will leverage the Chainlink request & receive model for processing information from our collection inclusion and appraisal algorithms.

### **Smart Contract Risks**

We've forked the Synthetix codebase and thus most of our contract code benefits from their prior audits. However, we have made edits and our contracts remain unaudited for now.&#x20;

### **Deleveraging Spiral Risk**

Stablecoin markets face deleveraging feedback effects that may cause illiquidity during crises and exacerbate collateral drawdown, and characterize stable dynamics of the system under particular conditions. The possibility of such 'deleveraging spirals' were observable during the Black Thursday' crisis in Dai in 2020.&#x20;

We aim to reduce this risk by routing 25% of protocol revenue to dedicated liquidity pools for $MIME/(DAI:USDC:USDT) and siphoning the farming revenue into a smart contract that will serve as an insurance fund for crises. Funds from this contract will be used to repay debt in the event that a participant closes a position and is owed more profit than is locked in the system.

It's also worth noting that while participants will be able to use the protocol at collateralization ratios lower than 8:1, participants are economically incentivized to deposit $MIME at an 8:1 ratio.

### **Macro Economic Risk**

Participants who deposit non-stable collateral are at risk of having their positions liquidated due to the value of their underlying collateralized assets reducing in price relative to the price of other collateral deposited into the network.&#x20;
