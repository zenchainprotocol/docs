# Terms & Concepts

For those validators or delegators who would like to join ZenChain open staking, this section will help you get started and learn about how everything works. 

### **Becoming a Validator in the ZenChain network**

To become a validator in the ZenChain network, please refer to our tutorials linked below. These will guide you through the steps of setting up the ZenChain network and setting up your node

### **Validator Set**

ZenChain's active validator set consists of the top 100 nodes, as measured by the total stake. The calculated total stake includes both the validator’s individual stake and all of its delegations. This validator set is refreshed every block, so changes to a validator’s total stake that would shift it in or out of the validator set will be reflected in consensus almost immediately. There is no explicit minimum stake amount required to be a validator on ZenChain. The amount staked by the lowest validator in the set serves as an implicit minimum.

In order to be a validator in ZenChain, you must have a ZenChain wallet address. This is so the validator can have ZEN and use that ZEN to stake their node. When validators stake their ZEN, that ZEN gets bonded to the network and cannot be transferred to any other address.

### **Fees**

Validators are responsible for setting their own minimum fee price. This price is the minimum fee amount that the validator’s node will accept when receiving a transaction or adding a transaction to a block for proposal.

### Block Rewards

Validator block rewards consist of network fees from transactions. These fees are pooled globally and distributed to validators proportionally based on voting power. The validator that proposed a particular block also receives a bonus for the fees collected in that block. Fees are collected and added to the reward pool every block.s

### Claiming & Restaking Block Rewards

Validators and delegators must manually submit a transaction to withdraw their rewards from the reward pool. Because of this, automatic redelegation of rewards is not possible on-chain. Validators and delegators are therefore responsible for withdrawing and redelegating their rewards manually when desired.  
  
When withdrawing, all of the claimant’s available rewards are withdrawn from the reward pool. Delegators can, however, withdraw only the rewards from a particular validator if they choose.

### **Unbonding**

Validators and delegators can submit an unbonding transaction to remove their staked tokens. Once the transaction is processed the staked tokens will enter an unbonding period of 21 days. During the unbonding period the staked tokens will not earn any validator income, but are still susceptible to slashing penalties. After the unbonding period the tokens will be fully released to the user.

### Slashing

Validators committing a slashable offense will have their stake removed by a slash factor. ZenChain currently only penalizes validators for downtime. If a validator misses more than 50 blocks in any 100 block window, they will be slashed and jailed. The slash penalty for downtime is 1% of the validator’s total stake including delegations; these tokens will be burned. The offending validator will be jailed for 10 minutes. While the validator is jailed they are removed from the validator set and cannot participate in consensus and thus will not receive block rewards. After the 10 minute jail period is over the validator must submit a transaction to unjail, at which point they will rejoin consensus.

## **Inflationary Block Rewards**

 ****Inflationary block rewards will be minted per block based on a schedule set by governance. These rewards will be added to and distributed by the same global reward pool as fee rewards.

## Validator Subsidy Rewards

ZenChain will run a 1**-week** validator subsidy program for validators to incentivize early adoption. Rewards are subject to change based on evaluations of the network from the ZenChain core team, community feedback, and governance over time.

To learn more about this program and what you can expect to earn as part of this program, reference our announcement articles. 



