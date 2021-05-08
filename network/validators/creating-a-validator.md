# Creating Validators

### Acquiring ZEN to bond:

In order to acquire ZEN you can: 

* 1\) Purchase some from our token sale 
* 2\) Attract delegations 
* 3\) Acquire ZEN via other decentralized exchanges
* 4\) For testnet, please follow each campaign to request a test token. 

### Requirements

1. You need to have zenchaind application
2. Start and sync successfully with network
3. You have a wallet with enough balance
4. You must know your validator wallet 

   * `zenchaind tendermint show-validator`

   \`\`

### Create validator

Now that you have your node up and running and you have ZEN to stake with, you must now execute the following command:

* `zenchaind tx staking create-validator` 
  * In order to execute this command, there are several decisions that must be made in relation to your node. Some of these settings will not be editable after creation \(pointed out below\), so please be sure about the values you are setting:
    * **commission-max-change-rate &lt;max-rate-change&gt;**
      * This is the most that you will be able to change your commission rate at a time. This value IS NOT editable after validator creation. Commission rates can be changed only once every 24 hours.
    * **commission-max-rate &lt;max-rate&gt;**
      * This is the highest rate that your validator node will be able to charge. This value IS NOT editable after validator creation.
    * **commission-rate &lt;rate&gt;**
      * This is the starting commission rate that your validator node will charge its delegators. This value IS editable after validator creation.
    * **amount &lt;amount&gt;** 
      * This is the amount of your starting self-delegation. This can be both unbonded and added to later. We accept uzen token \(this is smallest unit for ZEN token, 1000000uzen=1 zen\) 
    * **pubkey** 
      * This is the public validator key associated with your node. You can get your public validator key with command **`$(zenchaind tendermint show-validator)`** 
    * **moniker &lt;moniker&gt;**
      * This is the publicly viewable name of your node.
    * **chain-id &lt;chain-id&gt;**
      *  This is the identifier of the network the node is connecting to.
    * **min-self-delegation 1** 
      * This is the minimum number of tokens that the node must delegate to itself.
    * **gas auto** 
      *  ****This is the amount of gas submitted for the create validator transaction.
    * **from &lt;moniker&gt;** 
      * This is a reference to the signer of this transaction \(your validator address/moniker\).
    * **keyring-backend file**
      * This specifies the location of your node’s keyring.

Example: 

```text
zenchaind tx staking create-validator --chain-id=lotus-testnet --commission-max-change-rate=0.1 --commission-max-rate=0.1 --commission-rate=0.1 --amount=25000000000uzen --min-self-delegation=1 --pubkey=$(zenchaind tendermint show-validator) --from=elon --moniker=Teslaaa
```

* Next, you can verify that this was executed correctly by running this command:  `zenchaind query staking validator <validator-address> .` This will return information about your validator.

After you have setup your node and successfully staked it with ZEN, you are now considered eligible to be a part of zenchain's validator set. 

