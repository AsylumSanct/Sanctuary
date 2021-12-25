# Treasury

The treasury contract is a simple vault implementation holding all the funds collected by the protocol. If for instance a user purchases a USDC bond, the bonded USDC is fully taken in by the treasury in return of the market equivalent of REAP bonded for. New REAP will be minted based on the RFV of the treasury assets.

The treasury contract is guarded by a 4 of 7 multisig. That means any transaction for the treasury must be approved by at least 4 signers, of which we have 7 signers in total. The operation security for our treasury assets is thus protected from a single actor going rogue, because it takes a quorum of 4 to authorize any transaction like moving funds in and out. The 7 signing addresses for our treasury are listed below.\


Note that all signers can be verified:

1. 0xPoo
2. Asylum
3. Ki
4. Derrell
5. Brian
6. Star-Lord
7. TBA

