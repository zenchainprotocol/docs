# Delegator commands

### Staking delegate

Delegate tokens to a validator.  
Validator-addr is address of the validator start with **`zenvaloper.`** You can find it on [https://scan.zenchain.network/validators](https://scan.zenchain.network/validators)

![](../../.gitbook/assets/image%20%2831%29.png)

```text
zenchaind tx staking delegate [validator-addr] [amount] [flags]
```

```text
zenchaind tx staking delegate <zen...> <amount> --chain-id=lotus-testnet --from=<key-name> 
```

### Staking unbond

Unbond tokens from a validator.

```text
zenchaind tx staking unbond [validator-addr] [amount] [flags]
```

#### Unbond some tokens from a validator <a id="unbond-some-tokens-from-a-validator"></a>

```text
zenchaind tx staking unbond <zen...> 100000000uzen --from=<key-name> --chain-id=lotus-testnet 
```

### Staking redelegate

Transfer delegation from one validator to another.

There is no `unbonding time` during the redelegation, so you will not miss the rewards. But you can only redelegate once per validator, until a period \(= `unbonding time`\) exceed.

```text
zenchaind tx staking redelegate [src-validator-addr] [dst-validator-addr] [amount] [flags]
```

### Redelegate some tokens to another validator

```text
zenchaind tx staking redelegate <zen...> <zen...> 1000000000uzen --chain-id=lotus-testnet --from=<key-name> 
```



