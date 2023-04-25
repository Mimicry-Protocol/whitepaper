---
description: Anyone can launch Mimicry Markets using this simple guide.
---

# 🎪 Markets

## 1. Request Access

At this time your wallet must be approved in order to launch a new market on Mimicry. Please apply for approval [here](https://v593x222y0p.typeform.com/to/q76aaHsv?utm\_source=docs.mimicry.org) and then ping the team on Discord in the [mimicry-markets channel](https://discord.com/channels/931357054218666005/1100530833074438244).

## 2. Create a New Data Feed

**a)** Refer to the [contracts reference](../../for-devs/contracts-and-wallets.md#off-chain-reporting-oracle) for the address of the OpenMarketsOracle contract on Polygon PoS or Mumbai.&#x20;

**b)** From there you'll need to call the `createDataFeed()` function the contract, passing the data feed _nickname_ and a list of one or more _allowed scribes_.&#x20;

> **Pro Tip:** The most secure data feeds will only authorize a single scribe and that will be the [dedicated msg.sender](http://localhost:5000/s/1bgWuA312BXaMSughVVw/disclaimer) associated with your Gelato Web3 Functions (W3F) account.

**c)** Inspect the logs after the `createDataFeed()` transaction is successful in order to find the `dataFeedId`. The ID will be used later when setting up the W3F.

<figure><img src="../../.gitbook/assets/Screenshot 2023-04-25 at 3.18.53 PM.png" alt=""><figcaption></figcaption></figure>

## 3. Create an Automated Task in Gelato

**a)** Visit [this page](https://beta.app.gelato.network/new-task) in the Gelato W3F application and connect your wallet. You can also reach this page by clicking the New Task button on the dapp homepage.

<figure><img src="../../.gitbook/assets/Screenshot 2023-04-25 at 3.19.36 PM.png" alt=""><figcaption></figcaption></figure>

**b)** You'll need to start off by pasting the IPFS CID of your W3F. We recommend using the _Mashup_ function that we've officially published and maintain. Please see the [Contracts Reference](../../for-devs/contracts-and-wallets.md#gelato-web3-functions) for the latest CID of the function you'd like to use.

**c)** Each W3F schema is different, but assuming you're using one of our officially supported functions, you'll need to add the following parameters:

> **Pro Tips:** See the enums in the [Off-Chain Reporting Oracle repository](https://github.com/Mimicry-Protocol/off-chain-reporting-oracle/blob/master/src/web3-functions/libs/enums.ts) for a complete list of supported _chainIds_, _consensus methods_, _currencies_, _metrics_, and _providers_.&#x20;
>
> And all arrays of strings must be formatted as follows: `["value","value"]`

* `oracleAddress` See the [contracts reference](../../for-devs/contracts-and-wallets.md#off-chain-reporting-oracle) for the appropriate OpenMarketsOracle contract.
* `dataFeedId` Paste the _dataFeedId_ that you previously created in step 2.c. above.
* `nftCollections` This field accepts a comma-separated array of one or more NFT collections pointers, in the following format: `["chainId:contractAddress","chainId:contractAddress"]`&#x20;
* `tokens` This field operates the same way as `nftCollections`, expect that it expects contract address of ERC-20 tokens.
* `currency` Expects a currency string, like _usd._
* `metric` Expects a metric string, like _market-cap._
* `providers` Expects an array of strings, where each provider is used to query market data about NFTs, tokens, etc.
* `consenusMethod` Expects string that includes a filter and a methodology, formatted as _filter:methodology._ Ultimately this defines how to distill down to a single number when various providers disagree on the metric related to an NFT collection, token, etc. In nearly all cases we recommend using `meanAverageDeviation:mean`.&#x20;
* `deviation` Expects a number between 0 – 10,000, where 10,000 equals 100%. This parameter instructs the data feed to write a tick on-chain anytime the new value returned by the provider APIs changes by more than the deviation threshold. We generally recommend using a value of 25 to represent a deviation threshold of 0.25%.
* `heartbeat` Expects a number greater than 0, where the number is the amount of seconds to wait between on-chain ticks before writing a new value. Generally we recommend setting this value to _3600_ to represent one hour.

## 4. Set Environment Variables

API keys must be set for each provider. The easiest way to do this is to clone the Mimicry Off-Chain Reporting Oracle repository, setup your local .env file, and run the command , as described in the [Secrets section of the repository README](https://github.com/Mimicry-Protocol/off-chain-reporting-oracle/tree/master#re-secrets).

## 5. Fund Your Task

The last step is to [fund](http://localhost:5000/s/1v4pHmBLW0tkrfgW1nyn/tips-and-tricks/speed-up-with-quick-find) your Gelato W3F account so there is ample money available for gas. We generally recommend funding approximately $1,000 per task per year, which assumes an average of $0.078 per transaction, and 35 transactions per day.\
