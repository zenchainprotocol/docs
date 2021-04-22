# Delegator commands

### Staking delegate <a id="iris-tx-staking-delegate"></a>

Delegate tokens to a validator.

```text
zenchaind tx staking delegate [validator-addr] [amount] [flags]
```

```text
zenchaind tx staking delegate <zen...> <amount> --chain-id=lotus-testnet --from=<key-name> --fees=30000uzen
```

### Staking unbond <a id="iris-tx-staking-unbond"></a>

Unbond tokens from a validator.

```text
zenchaind tx staking unbond [validator-addr] [amount] [flags]
```

#### Unbond some tokens from a validator <a id="unbond-some-tokens-from-a-validator"></a>

```text
zenchaind tx staking unbond <zen...> 100000000uzen --from=<key-name> --chain-id=lotus-testnet 
```

### Staking redelegate <a id="iris-tx-staking-redelegate"></a>

Transfer delegation from one validator to another.

There is no `unbonding time` during the redelegation, so you will not miss the rewards. But you can only redelegate once per validator, until a period \(= `unbonding time`\) exceed.

```text
zenchaind tx staking redelegate [src-validator-addr] [dst-validator-addr] [amount] [flags]
```

#### Redelegate some tokens to another validator <a id="redelegate-some-tokens-to-another-validator"></a>

```text
zenchaind tx staking redelegate <zen...> <zen...> 1000000000uzen --chain-id=lotus-testnet --from=<key-name> 
```



