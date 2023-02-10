# Automated Swap-Sides

We hope all Actors will do their own research to determine what [True Odds](../../core-mechanics/true-odds.md) they believe are most favorable to their situation. Accordingly, some Actors may decide that they want to be long if the True Odds of the bullish side of a market are below `x`, and short if the True Odds of the bullish side are above `x`.

> **For example:** <mark style="color:purple;">Suppose that Debbie fundamentally believes that the market capitalization of the World of Women NFT collection is twice as likely to go down in value than go up in value, and the current skew within that Pantomime is $20k long and $100k short. Here the bulls have 5x True Odds, and the bears have 0.2x True Odds. In this case Debbie would want to have her capital working on the long side of this Pantomime until the bearish True Odds shifted to be above 0.5x, simply because she would believe that 0.2x odds are not favorable based on her fundamental research. To accomplish this she can open her Mime with the automatic swap-side feature set to 2x bullish and 0.5x bearish. When enough capital is added to the bullish side, such that the bearish odds would move above 0.5x if her capital was swapped from the bullish side to the bearish side of the Pantomime, her position would automatically shift from bullish to bearish.</mark>

{% hint style="success" %}
**Related:** [Skew Change Risk](../../risks-and-mitigations/skew-change-risk.md)
{% endhint %}
