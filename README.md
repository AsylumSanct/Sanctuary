# FAQ

## How does Sanctuary work?

Sanctuary consists of its protocol managed treasury, protocol owned liquidity, bond mechanism, and staking rewards that are designed to control supply expansion, along with it's native integrated NFTs (Cultists & Ghosts).

Bond sales generate profit for the protocol, and the treasury uses the profit to mint REAP and distribute them to stakers. Thanks to liquidity bonds, the Sanctuary protocol is able to accumulate its own liquidity. \
\
Additionally, the protocol takes roughly 2% of each rebase, and funnels it down to a much smaller group; the NFT holders. Distributing this rebase diversion amongst the 789 Cultist and 789 Ghosts respectively, means each holder receives a substantial stream of income. Additionally, thanks to Magic Eden's NFT marketplace, anyone has the opportunity to become a holder of Cultists and/or Ghosts to start receiving their share of the rewards. Sanctuary offers participants to benefit from not only the high APY staking and discount bonding, but from owning an ever-appreciating asset that provides on-going rewards.

## Is REAP a stable coin?

No, REAP is not a stable coin. Rather, REAP aspires to become an algorithmic reserve currency backed by other decentralized assets. Similar to the idea of the gold standard, REAP provides free floating value its users can always fall back on, simply because of the fractional treasury reserves REAP draws its intrinsic value from.

## REAP is backed, not pegged.

Each REAP will be backed by at least 1 USDC, not pegged to it. Because the treasury backs every REAP with at least 1 USDC, the protocol would buy back and burn REAP when it trades below 1 USDC. This has the effect of pushing REAP price back up to 1 USDC. REAP could always trade above 1 USDC because there is no upper limit imposed by the protocol.

## Why is PCV important?

As the protocol controls the funds in its treasury, REAP can only be minted or burned by the protocol. This also guarantees that the protocol can always back 1 REAP with 1 USDC. You can easily define the risk of your investment because you can be confident that the protocol will indefinitely buy REAP below 1 USDC with the treasury assets until no one is left to sell.

As the protocol accumulates more PCV, more runway is guaranteed for the stakers. This means the stakers can be confident that the current staking APY can be sustained for a longer term because more funds are available in the treasury.

## Why is the market price of REAP so volatile?

It is extremely important to understand how early in development the Sanctuary protocol is. A large amount of discussion has centered around the current price and expected a stable value moving forward. The reality is that these characteristics are not yet determined. The network upon launch will be tuned for expansion of REAP supply, which when paired with the staking, bonding, and yield mechanics of Sanctuary, result in a fair amount of volatility.

REAP could trade at a very high price because the market is ready to pay a hefty premium to capture a percentage of the current market capitalization. However, the price of REAP could also drop to a large degree if the market sentiment turns bearish. We would expect significant price volatility during our growth phase so please **do your own research** whether this project suits your goals.

## What is the point of buying it now when REAP trades at a very high premium?

When you buy and stake REAP, you capture a percentage of the supply (market cap) which will remain close to a constant. This is because your staked REAP balance also increases along with the circulating supply. The implication is that if you buy REAP when the market cap is low, you would be capturing a larger percentage of the market cap.

## What is a rebase?

Rebase is a mechanism by which your staked REAP (the staked REAP variant is called SOW) balance increases automatically. When new REAP are minted by the protocol, a large portion of it goes to the stakers. Because stakers only see SOW balance instead of REAP, the protocol utilizes the rebase mechanism to increase the SOW balance so that 1 SOW is always redeemable for 1 REAP.

## What is reward yield?

Reward yield is the percentage by which your staked SOW balance increases on the next block. It is also known as _rebase rate_. Sanctuary employs dynamic rebasing, which means your balance will increase with each block, factoring in the per-block APY.

## What is APY?

APY stands for annual percentage yield. It measures the real rate of return on your principal by taking into account the effect of compounding interest. In the case of Sanctuary, your SOW represents your principal, and the compound interest is added on every block, thanks to the dynamic rebase mechanism.

One interesting fact about APY is that your balance will grow not linearly but exponentially over time. Assuming a daily compound interest of 2%, if you start with a balance of 1 SOW on day 1, after a year, your balance will grow to about 1377.

## How is the APY calculated?

The APY is calculated from the reward yield (rebase rate) using the following equation:

$$
APY = ( 1 + rewardYield )^{78840000}
$$

It raises to the power of 78840000 because a rebase happens upon each block. On Solana, there are \~2.5 blocks per second, or 216000 blocks daily. Multiplying by 365 days in a year gives a rebase frequency of 365 \* 216000 = 78840000. Per block (2.5/s) APY of 0.000006% - 0.000009% is expected.

Reward yield is determined by the following equation:

$$
rewardYield = REAP_{distributed} / SOW_{totalStaked}
$$

The number of SOW distributed to the staking contract is calculated from total supply using the following equation:

$$
REAP_{distributed} = {totalSupply} \times rewardRate
$$

The reward rate is subject to change under authority of the DAO and policy team.

## Why does the price of REAP become irrelevant in long term?

As illustrated above, your balance will grow exponentially over time thanks to the power of compounding. Let's say you buy REAP for $400 now and the market decides that in 1 year time, the intrinsic value of REAP will be $2. Assuming a daily compound interest rate of 2%, your balance would grow to about 1377 REAP by the end of the year, which in this case would be worth around $2754.&#x20;

## What will be REAP's intrinsic value in the future?

There is no clear answer for this, but the intrinsic value can be determined by the treasury performance. For example, if the treasury could guarantee to back every REAP with 100 USDC, the intrinsic value will be 100 USDC.

## What are the rewards for holding the NFTs?

Each wallet holding at least 1 Cultist or Ghost will be distributed a share from the total rebase. Roughly 1% is diverted to the Cultists and 0.25% or 0.5% to the Ghosts:\
\
Cultists: 1% / 789\
Ghosts (Paired): .5% / 789\
Ghosts (Unpaired): .25% / 789

## Do I need to hold a Cultist or Ghost NFT to stake in the Sanctuary?

No. Staking is open to anyone, at any time. Holding the NFTs is completely optional.

## Where can we purchase the NFTs?

The links to each collection (Cultists & Ghosts) on Magic Eden can be found in the links section. We are only officially listed on Magic Eden. It is possible to purchase on the other marketplaces, but caution is required as there are many unverified copycats that will not receive rewards.

## Are we staking the NFTs?

No. Sanctuary has it's own native token called REAP. The staked variant of REAP is called SOW.&#x20;
