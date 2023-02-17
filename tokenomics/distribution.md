# 📊 Distribution

### **Overview**

The supply of $MIMIC will be reserved as follows: 40% for community rewards, 22.5% for existing and future investors, 20% for existing and future Crew, 14% for the Mimicry Foundation’s treasury and exchange listings, 2% for strategic market makers, and 1.5% for an airdrop sometime in the future. This distribution will be programmed into the $MIMIC smart contract and may not be changed in the future.

<figure><img src="https://lh5.googleusercontent.com/JsXGgb_CUEvkBpmr86BrFvCdY1y9h35BfnhU1KbVc9jEHPbGcQ7hpSh227UR7KRx8giFoH7ymiiNeG1M-ARYlWruXZHyc2B1Re6EptyxddhYTlVs4DCLKeg3TU5mNbQocBaUzh_KDoEQb9Egg1j21BA" alt=""><figcaption></figcaption></figure>

The community rewards tokens will be distributed using a decay curve that operates as an approximately-having schedule annually, calculated weekly, where \~48.54% of the community rewards will be distributed during the first year, \~24.98% during the second year, and so on.&#x20;

A detailed code example that illustrates the exact number of weekly rewards for the 30 years following the TGE is available below.

```runkit  nodeVersion="14.x.x"
// CONSTANTS WE CAN CHANGE TO MODEL DIFFERENT CURVES
const startingTokenSupply = 400000000;
const periodsPerYear = 52;
const years = 30;

let totalTokens = 0;
const totalPeriods = periodsPerYear * years;
const decayMeasure = 1 / startingTokenSupply;

// I ASSUME WE WILL SET THE DECAY RATE AS A 
// CONSTANT IN THE SMART CONTRACT TO SAVE ON GAS
const decayRate = 1 - (-Math.log(decayMeasure) / totalPeriods);
// console.log(decayRate); // e.g. 0.9873032210864922

// OUTPUT THE MAX NUMBER OF CLAIMABLE TOKENS DURING THIS PERIOD
function getClaimableTokenAmount(
	period, 
  decay = decayRate,
  startingSupply = startingTokenSupply
  ) {
		const previousSupply = startingSupply * (decay ** (period - 1))
  	const currentSupply = startingSupply * (decay ** period);
		return previousSupply - currentSupply;
}

// LOGGING FOR CONVENIENCE
for (let i = 1; i <= totalPeriods; i++) {
  const claimableTokens = getClaimableTokenAmount(i);
  totalTokens += claimableTokens;
  
  console.log("Claimable tokens for period " + i + ": " + claimableTokens);
  if (i % periodsPerYear === 0) {
  	console.log("    End of Year " + (i / periodsPerYear) + ". Total tokens distributed: "
      + totalTokens + " ( " + ((totalTokens / startingTokenSupply) * 100) + "%" + " ).");
  }
}


```

Using this curve, 92.99% of the 400,000,000 $MIMIC tokens allocated to community rewards will be available to Producers and Actors who time-lock their $MIMIC-funded Mimes at any point over the first four (4) years following the token generation event (TGE), and the remaining 7.01% of community reward tokens will be distributed during the next 26 years after that. The nature of this design provides economic incentive for the earliest adopters of the protocol to earn the greatest share of token rewards.&#x20;

<figure><img src="https://lh4.googleusercontent.com/KKpMbQLvA8e7Lb-tyAnr3UmbFEPbGuHPGuGMfEhfBTujl6wuhzFM8f2piiL_IoTAgOljqa5EcxbB8GOZiwUbyU75d1Wtk9xLpd7VNDRgI0azKgvBLHEIORqTT8Fwf9Yb_Q4a1DGkI8C_9rGnmSWCMCI" alt=""><figcaption></figcaption></figure>
