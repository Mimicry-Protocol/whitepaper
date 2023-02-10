# 💰 Rewards

### **Overview**

In addition to unlocking special features, Actors and Producers who use $MIMIC to open positions will also be eligible to earn rewards in the form of additional $MIMIC tokens. Rewards will be paid using Pantomime revenue, and using [an allocation](distribution.md) of the initial token supply.

### **Time-Weighted & Size-Weighted Earning**

It is in the best interest of the protocol to incentivize players to open large positions for long periods of time. This is especially true for Producers who want to maximize reward earnings while providing liquidity. Accordingly $MIMIC token yield will be determined based on a weight assigned to each Mime. Players may lock their Mimes when opening their position, or after their position is open, for a selectable time-lock <mark style="color:green;">`tl`</mark> in one-week increments, where <mark style="color:green;">`tl`</mark> ≥ one week, <mark style="color:green;">`tl`</mark> < max time-lock <mark style="color:green;">`m`</mark>, and <mark style="color:green;">`m`</mark> = 4 years. After locking, the weeks left to unlock is <mark style="color:green;">`t`</mark> ≤ <mark style="color:green;">`tl`</mark>, and <mark style="color:green;">`t`</mark> will be rounded to the nearest whole week. Reward earning weight decreases linearly from the moment of locking. The amount of $MIMIC in their Mime <mark style="color:green;">`a`</mark>, may change with market dynamics. Additionally, there is a second reward multiplier <mark style="color:green;">`b`</mark>, applied from the moment a position is opened with a time-lock, where <mark style="color:green;">`b`</mark> = 1 + 100% annually, calculated weekly. The earning weight is equal to:

$$
w = a * b * (t / m)
$$

> **For example context using this formula:** <mark style="color:purple;">A two-year-old Mime that extends its time-lock to four years using $1,600 worth of $MIMIC will have the same reward-earning weight during the first week of its time-lock as a newly minted Mime with $998,400 worth of $MIMIC and a one week time-lock, or a newly minted Mime with $4,800 worth of $MIMIC and a four-year time-lock.</mark>&#x20;
>
> <mark style="color:purple;"></mark>
>
> <mark style="color:purple;">**Because:**</mark>
>
> <mark style="color:purple;">`998,400 * 1 * (1/208) === 4,800 * 1 * (208/208) === 1,600 * 3 * (208/208)`</mark>

In other words, the reward-earning weight is both amount- and time-weighted, where the time counted is how long the tokens cannot be moved in the future and how long ago the Mime was first minted.&#x20;

{% hint style="info" %}
The size of a [leveraged](../advanced-features/leverage.md) position will not be used when calculating reward-earning power.
{% endhint %}

We imagine this approach will also create a secondary market for Mimes, where Mimes that have been open for a long time will be more valuable than newly minted Mimes.

The time-lock for a Mime can be extended at any time, up to the max time-lock, and the amount of $MIMIC within a time-locked Mime can also be increased at any time. Further, all features available to $MIMIC-backed Mimes, other than reducing position sizes and automated stop-loss, will be available to all time-locked Mimes. Concretely this means that a time-locked Mime can earn a cash flow of profits using the automated take-profit feature or by manually harvesting profits earned. Deposited $MIMIC may be withdrawn from a Mime after the time-lock expires.&#x20;

### Reward Distribution

Rewards are distributed pro-rata based on Mime weight. Accordingly, the amount of revenue-based rewards earned during a two-week earning-epoch within each Pantomime will be equal to the sum of a Mime’s reward-earning weight <mark style="color:green;">`w`</mark>, on each day of the earning-epoch, divided by the sum of reward-earning weight from all Mime’s in the Pantomime on all days of the an earning-epoch <mark style="color:green;">`W`</mark>, multiplied by the total Pantomime exit fee and advertising revenue earned during the earning-epoch that is earmarked for community rewards <mark style="color:green;">`r`</mark>.

![{( sum w)/( sum W), r}](https://lh4.googleusercontent.com/qglvGVzSfYW2mcSszJE4E4PCuA7Zgi5gLfOsFG3YhQ3Z5QIhIlKcyJdmc4JLQdODz1uWEuru-nw\_AIIGZkkaq5knhSbX2lZdV50OokI5WKXqFUOrx2GlIi\_DP1OtWE3W0V\_XB-3SHsoZqclhA3-EdqM)

$MIMIC distributed for community rewards as part of our initial token supply will be distributed using a similar function, except where <mark style="color:green;">`W`</mark> represents the sum of reward-earning weight from all Mime’s in all Pantomimes on all days of an earning-epoch.

{% hint style="info" %}
Note that this design is based heavily on the Curve governance model. See the [Curve DAO white paper](https://classic.curve.fi/files/CurveDAO.pdf) for additional implementation details.
{% endhint %}

### **Claiming Rewards**

$MIMIC community and revenue rewards earned by Actors, Producers, and Directors may be claimed weekly. All claimed tokens will vest linearly for 12 months using a constant linear stream. This claiming and vesting mechanism will help to prevent players from receiving rewards and immediately selling them on the open market.
