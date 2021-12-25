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

Bond payout determines the number of SANCT sold to a bonder. For \[reserve bonds], the market value of the assets supplied by the bonder is used to determine the bond payout. For example, if a user supplies 1000 DAI and the bond price is 250 DAI, the user will be entitled 4 SANCT.

$$
bondPayout_{lpBond} = marketValue_{lpToken}\ /\ bondPrice
$$

For \[liquidity bonds], the market value of the LP tokens supplied by the bonder is used to determine the bond payout. For example, if a user supplies 0.001 SANCT-DAI LP token which is valued at 1000 DAI at the time of bonding, and the bond price is 250 DAI, the user will be entitled 4 SANCT.

## SANCT Supply

$$
SANCT_{supplyGrowth} = SANCT_{stakers} + SANCT_{bonders} + SANCT_{DAO} + SANCT_{pSANCTExercise}
$$

SANCT supply does not have a hard cap. Its supply increases when:

* SANCT is minted and distributed to the stakers.
* SANCT is minted for the bonder. This happens whenever someone purchases a bond.
* SANCT is minted for the DAO. This happens whenever someone purchases a bond. The DAO gets the same number of SANCT as the bonder.
*   SANCT is minted for the team, investors, advisors, or the DAO. This happens whenever

    the aforementioned party exercises their pSANCT.

$$
SANCT_{stakers} = SANCT_{totalSupply} * rewardRate
$$

At the end of each epoch, the treasury mints SANCT at a set \[reward rate]. These SANCT will be distributed to all the stakers in the protocol. You can track the latest reward rate on the \[Sanctuary Policy dashboard].

$$
SANCT_{bonders} = bondPayout
$$

Whenever someone purchases a bond, a set number of SANCT is minted. These SANCT will not be released to the bonder all at once - they are vested to the bonder linearly over time. The bond payout uses a different formula for different types of bonds. Check the [bonding section above](equations.md#bonding) to see how it is calculated.

$$
SANCT_{DAO} = SANCT_{bonders}
$$

The DAO receives the same amount of SANCT as the bonder. This represents the DAO profit.

$$
SANCT_{pSANCTExercise} = pSANCT + DAI
$$

The individual would supply 1 pSANCT along with 1 DAI to mint 1 SANCT. The pSANCT is subsequently burned.

## Backing per SANCT

$$
SANCT_{backing} = treasuryBalance_{stablecoin} + treasuryBalance_{otherAssets}
$$

Every SANCT in circulation is backed by the Sanctuary treasury. The assets in the treasury can be divided into two categories: stablecoin and non-stablecoin.

$$
treasuryBalance_{stablecoin} = RFV_{reserveBond} + RFV_{lpBond}
$$

The stablecoin balance in the treasury grows when bonds are sold. \[RFV]is calculated differently for different bond types.

$$
RFV_{reserveBond} = assetSupplied
$$

For reserve bonds such as DAI bond and FRAX bond, the RFV simply equals to the amount of the underlying asset supplied by the bonder.

$$
RFV_{lpBond} = 2sqrt(constantProduct) * (\%\ ownership\ of\ the\ pool)
$$

For LP bonds such as SANCT-DAI bond and SANCT-FRAX bond, the RFV is calculated differently because the protocol needs to mark down its value. Why? The LP token pair consists of SANCT, and each SANCT in circulation will be backed by these LP tokens - there is a cyclical dependency. To safely guarantee all circulating SANCT are backed, the protocol marks down the value of these LP tokens, hence the name _risk-free_ value (RFV).
