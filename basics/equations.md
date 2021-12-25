# Equations

## Staking

$$
deposit = withdrawal
$$

Swaps between REAP and SOW during staking and unstaking are always honored 1:1. The amount of REAP deposited into the staking contract will always result in the same amount of SOW. And the amount of SOW withdrawn from the staking contract will always result in the same amount of REAP.

$$
rebase = 1 - ( REAPDeposits / SOWoutstanding )
$$

The treasury deposits REAP into the distributor. The distributor then deposits REAP into the staking contract, creating an imbalance between REAP and SOW. SOW is rebased to correct this imbalance between REAP deposited and SOW outstanding. The rebase brings SOW outstanding back up to parity so that 1 SOW equals 1 REAP.

## Bonding

$$
bond Price = 1 + Premium
$$

REAP has an intrinsic value of 1 USDC, which is equivalent to $1. In order to make a profit from bonding, Sanctuary charges a premium for each bond.

$$
Premium = debt Ratio * BCV
$$

The premium is derived from the debt ratio of the system and a scaling variable called BCV. The BCV allows us to control the rate at which bond prices increase.

The premium determines profit due to the protocol and in turn, stakers. This is because new REAP is minted from the profit and subsequently distributed among all stakers.

$$
debt Ratio = bondsOutstanding/REAPSupply
$$

The debt ratio is the total of all REAP promised to bonders divided by the total supply of REAP. This allows us to measure the debt of the system.

$$
bondPayout_{reserveBond} = marketValue_{asset}\ /\ bondPrice
$$

Bond payout determines the number of REAP sold to a bonder. For reserve bonds, the market value of the assets supplied by the bonder is used to determine the bond payout.&#x20;

$$
bondPayout_{lpBond} = marketValue_{lpToken}\ /\ bondPrice
$$

For liquidity bonds, the market value of the LP tokens supplied by the bonder is used to determine the bond payout. For example, if a user supplies 0.001 REAP-USDC LP token which is valued at 1000 USDC at the time of bonding, and the bond price is 250 USDC, the user will be entitled 4 REAP.

## REAP Supply

$$
REAP_{supplyGrowth} = SOW_{stakers} + REAP_{bonders}
$$

REAP supply does not have a hard cap. Its supply increases when:

* REAP is minted and distributed to the stakers.
* REAP is minted for the bonder. This happens whenever someone purchases a bond.

$$
SOW_{stakers} = REAP_{totalSupply} * rewardRate
$$

At the end of each rebase, the treasury mints REAP at a set reward rate, to be distributed to all the stakers in the protocol. You can track the latest reward rate on the Sanctuary dashboard.

$$
REAP_{bonders} = bondPayout
$$

Whenever someone purchases a bond, a set number of REAP is minted. These REAP will not be released to the bonder all at once - they are vested to the bonder linearly over time. The bond payout uses a different formula for different types of bonds. The Bonding section has more information.



## Backing per REAP

$$
REAP_{backing} = treasuryBalance_{stablecoin} + treasuryBalance_{otherAssets}
$$

Every REAP in circulation is backed by the Sanctuary treasury. The assets in the treasury can be divided into two categories: stablecoin and non-stablecoin.

$$
treasuryBalance_{stablecoin} = RFV_{reserveBond} + RFV_{lpBond}
$$

The stablecoin balance in the treasury grows when bonds are sold. RFV is calculated differently for different bond types.

$$
RFV_{reserveBond} = assetSupplied
$$

For reserve bonds such as USDC, the RFV simply equals to the amount of the underlying asset supplied by the bonder.

$$
RFV_{lpBond} = 2sqrt(constantProduct) * (\%\ ownership\ of\ the\ pool)
$$

For LP bonds such as REAP-UDSC, the RFV is calculated differently because the protocol needs to mark down its value. Why? The LP token pair consists of REAP, and each REAP in circulation will be backed by these LP tokens - there is a cyclical dependency. To safely guarantee all circulating REAP are backed, the protocol marks down the value of these LP tokens, hence the name _risk-free_ value (RFV).
