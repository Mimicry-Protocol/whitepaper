# 🗓 Roadmap

### Mimicry Protocol

Our engineering team is in the early stages of forking Synthetix. This task is nontrivial because Synthetix is one of the most complex smart contract protocols in the Ethereum ecosystem. Our approach is as follows:

* Fork Synthetix to Polygon's Mumbai testnet
* Develop and deploy proxy contract for OpenSea NFT collection floor price discovery
* Refactor Synthetix to support NFT Mimics
* Refactor Synthetix to support $MIME instead of $SNX
* Refactor Synthetix to remove support for every asset except sUSD and Mimics
* Refactor Synthetix to change all instances of Synth to Mimic, Synthetix to Mimicry, sUSD to USDm, etc.
* Release documentation for Mimicry smart contracts
* Release Mimicry.js NPM module to simplify interaction with the Mimicry network

### Mimicry Dapp MVP

Once the Mimicry smart contracts are ready for testing we'll release our consumer platform. This platform will be initially optimized for simplicity and ease of use, and specifically user-tested with personas that are NFT-native. MVP features may include:

* Ability to connect MetaMask wallet
* Mechanism to select OpenSea NFT collection, deposit collateral, and mint a Mimic
* Mechanism to deposit $MIME to earn rewards
* Mechanism to swap Mimics
* Mechanism to view collateral balances
* Mechanism to claim staking rewards
* Mechanism to burn Mimics and release deposited collateral

### Non-Exhaustive Potential Product Expansion

First and foremost, it almost goes without saying that Mimicry can be extended to support NFT Mimics on any blockchain network as long as there is a decentralized marketplace with an available API (as is the case with OpenSea).

Another possible platform expansion is the ability to support inverse Mimics so that traders may short the price of NFT collections.

Of course, we intend to add a governance component and dissolve into a truly decentralized DAO.

Finally, our intent is to also release revenue-generating features for asset managers who actively manage collections of Mimics. For these features we'll draw inspiration from both TokenSets and dHedge.
