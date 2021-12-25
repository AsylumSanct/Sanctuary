# Staking

## Distributor

The distributor contract receives minted REAP from the treasury in order to drip-feed rewards to stakers. The reward rate target as of time of writing is set to TBA, which translates to TBA of total supply, since the reward rate is defined in tens of thousands. Note that the reward rate determines the rebase rate and that the rebase rate determines the APY.

## Staking

When the "stake" function is called, SOW is put into a warmup phase and all the information about how much SOW a user has staked is stored in the new staking contract. When the "claim" function is called, SOW is retrieved from the warmup and then sent to the user's wallet.
