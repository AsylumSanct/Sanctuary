# Alpha State

The initial network features a one-way treasury (money goes in, none comes out), the bonding contract (through which supply increases and profits are produced), and the staking contract (where profits are distributed).

The following are the initial policy states:

*   **BCV**

    BCV varies based on bond types. It is tuned regularly to meet the protocol goals. For example, if the protocol wants to accumulate more liquidity into its treasury, it can lower the BCV for LP bonds to increase their capacity.
*   **Bond vesting term**

    It is set to approximately five days for all bond types.
*   **REAP distribution**

    Every time someone purchases a bond, the proceed will go to the the treasury. A corresponding amount of REAP will be minted and distributed to three parties:

    *   Bonder

        The bond purchaser will receive the quoted amount of REAP linearly over the vesting term.
    *   Stakers

        After accounting for the REAP distributed to the bonder, the rest will be distributed among all stakers in the protocol.
