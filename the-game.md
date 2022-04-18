---
description: >-
  The goal of Mimicry is to always be holding whatever Mimic'd NFT collection
  happens to be moving in price the fastest, in the direction the holder
  predicted.
---

# 🎲 The Game

### It's Sort of Like Fantasy Football

Mimicry can be quite confusing to people unfamiliar with pooled collateral models, so we've created an illustration using a modified version of fantasy football.&#x20;

Suppose the game you're playing with 10 friends goes like this…

* Each player deposits $100 worth of ERC-20 collateral.
* Each player picks one NFL quarterback per week over the course of a 16-week season. Players can change their quarterback selection anytime.
* Each week we'll keep track of how many yards the selected quarterback runs for, where lost yards from sacks count against the run total. So a quarterback could have positive or negative running yards each week.
* When selecting their quarterback, each player also must designate if they want to use the actual yards ran, or the inverse of the actual yards ran.
* The player who tallies the greatest number of combined yards wins the largest portion of the $1,000 prize pool. The remaining portion of the prize pool is split between the other players using our relative P\&L algorithm.

### Fantasy NFT Collections

Now suppose instead of the football game above, your aim is to select the NFT collection that will be accelerating in price the fastest during any period of time. Or the collection that is decelerating the fastest, if you happened to pick the inverse position. Your earned rewards will be a function of your ability to swap between NFT collections as their percentage-based gains speed up or slow down, much like trying to pick the fastest runner in a race at any given time.

The main difference between the fantasy football example above and Mimicry is that with Mimicry (a) players can open or close positions at any time, (b) deposited collateral value will change in USD-terms depending on the macro price movement of the deposited collateral, and (c) winnings are not linearly distributed.

### The Payoff Algorithm, Explained

Most people are familiar with order books, or trading systems where each position has at least one participant on each side of a trade. In our system we can have as few as two participants taking two distinctly different positions against two distinctly different assets, with positions of any size, and with different deposit collateral. And they can still play against each other because we have a global collateral pool and a relative payoff profile.

**For example…**

1. Alice deposits $100 and picks BAYC to go up in price
2. Bob deposits $100 and picks Doodles to go up in price
3. Some time later Doodles goes up by 10x and Bob wants to cash out
   * _In a standard derivatives model, Bob could not exit his position because there is no liquidity on the opposite side of his trade._
   * _In a linear payoff profile for a pooled collateral model, Bob would have liquidated Alice's $100 and also been owed $900 that the system couldn't afford to pay him. This liquidity problem persists even with over-collateralized systems like Synthetix._
   * _In our relative payoff profile we determine how much of the collateral pool Alice and Bob have "rights" over based on their paper winnings relative to available collateral._
4. Alice has "rights" to 9% of the $200 collateral pool, while Bob has "rights" to 91% of the $200 collateral pool. Therefore, Bob cashes out $182, and Alice is left with $18.
