# Validator commands

### Query staking validator <a id="iris-query-staking-validator"></a>

#### Query a validator by validator address <a id="query-a-validator-by-validator-address"></a>

```text
zenchaind query staking validator <zen...>
```

### Query staking validators <a id="iris-query-staking-validators"></a>

#### Query all validators <a id="query-all-validators"></a>

```text
zenchaind query staking validators
```

### Query staking delegation <a id="iris-query-staking-delegation"></a>

Query a delegation based on delegator address and validator address.

```text
zenchaind query staking delegation [delegator-addr] [validator-addr]
```

#### Query a delegation <a id="query-a-delegation"></a>

```text
zenchaind query staking delegation <zen...> <zen...>
```

Example Output:

```text
Delegation:
  Delegator:  zen13lcwnxpyn2ea3skzmek64vvnp97jsk8qrcezvm
  Validator:  zenva15grv3xg3ekxh9xrf79zd0w077krgv5xfzzunhs
  Shares:     1.0000000000000000000000000000
  Height:     26
```

### Query staking delegations <a id="iris-query-staking-delegations"></a>

Query all delegations delegated from one delegator.

```text
zenchaind query staking delegations [delegator-address] [flags]
```

#### Query all delegations of a delegator <a id="query-all-delegations-of-a-delegator"></a>

```text
zenchaind query staking delegations <iaa...>
```

### Query staking delegations-to <a id="iris-query-staking-delegations-to"></a>

Query all delegations to one validator.

```text
zenchaind query staking delegations-to [validator-address] [flags]
```

#### Query all delegations to one validator <a id="query-all-delegations-to-one-validator"></a>

```text
zenchaind query staking delegations-to <zen...>
```

### Query staking unbonding-delegation <a id="iris-query-staking-unbonding-delegation"></a>

Query an unbonding-delegation record based on delegator and validator address.

```text
zenchaind query staking unbonding-delegation [delegator-addr] [validator-addr] [flags]
```

#### Query an unbonding delegation record <a id="query-an-unbonding-delegation-record"></a>

```text
zenchaind query staking unbonding-delegation <zen...> <zen...>
```

### Query staking unbonding-delegations <a id="iris-query-staking-unbonding-delegations"></a>

#### Query all unbonding delegations records of a delegator <a id="query-all-unbonding-delegations-records-of-a-delegator"></a>

```text
zenchaind query staking unbonding-delegations <zen...>
```

### Query staking unbonding-delegations-from <a id="iris-query-staking-unbonding-delegations-from"></a>

#### Query all unbonding delegations from a validator <a id="query-all-unbonding-delegations-from-a-validator"></a>

```text
zenchaind query staking unbonding-delegations-from <zen...>
```

### Query staking redelegations-from <a id="iris-query-staking-redelegations-from"></a>

Query all outgoing redelegations of a validator

```text
zenchaind query staking redelegations-from [validator-address] [flags]
```

#### Query all outgoing redelegatations of a validator <a id="query-all-outgoing-redelegatations-of-a-validator"></a>

```text
zenchaind query staking redelegations-from <zen...>
```

### Query staking redelegation <a id="iris-query-staking-redelegation"></a>

Query a redelegation record based on delegator and source validator address and destination validator address.

```text
zenchaind query staking redelegation [delegator-addr] [src-validator-addr] [dst-validator-addr] [flags]
```

#### Query a redelegation record <a id="query-a-redelegation-record"></a>

```text
zenchaind query staking redelegation <zen...> <zenva...> <zenva...>
```

### Query staking redelegations <a id="iris-query-staking-redelegations"></a>

#### Query all redelegations records of a delegator <a id="query-all-redelegations-records-of-a-delegator"></a>

```text
zenchaind query staking redelegations <zen...>
```

### Query Staking pool <a id="iris-query-staking-pool"></a>

#### Query the current staking pool values <a id="query-the-current-staking-pool-values"></a>

```text
zenchaind query staking pool
```

Example Output:

```text
Pool:
  Loose Tokens:   1409493892.759816067399143966
  Bonded Tokens:  590526409.65743521209068061
  Token Supply:   2000020302.417251279489824576
  Bonded Ratio:   0.2952602076
```

### Query staking params <a id="iris-query-staking-params"></a>

#### Query the current staking parameters information <a id="query-the-current-staking-parameters-information"></a>

```text
zenchaind query staking params
```

### Query staking historical-info <a id="iris-query-staking-historical-info"></a>

#### Query historical info at given height <a id="query-historical-info-at-given-height"></a>

```text
zenchaind query staking historical-info <height>
```

### Create-validator <a id="iris-tx-staking-create-validator"></a>

Send a transaction to apply to be a validator and delegate a certain amount of zen to it.

```text
zenchaind tx staking create-validator [flags]
```

**Flags:**

| Name, shorthand | type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- |
| --amount | string | Yes |  | Amount of coins to bond |
| --commission-rate | float | Yes | 0.0 | The initial commission rate percentage |
| --commission-max-rate | float |  | 0.0 | The maximum commission rate percentage |
| --commission-max-change-rate | float |  | 0.0 | The maximum commission change rate percentage \(per day\) |
| --min-self-delegation | string |  |  | The minimum self delegation required on the validator |
| --details | string |  |  | Optional details |
| --genesis-format | bool |  | false | Export the transaction in gen-tx format; it implies --generate-only |
| --identity | string |  |  | Optional identity signature \(ex. UPort or Keybase\) |
| --ip | string |  |  | Node's public IP. It takes effect only when used in combination with |
| --node-id | string |  |  | The node's ID |
| --moniker | string | Yes |  | Validator name |
| --pubkey | string | Yes |  | Go-Amino encoded hex PubKey of the validator. For Ed25519 the go-amino prepend hex is 1624de6220 |
| --website | string |  |  | Optional website |
| --security-contact | string |  |  | The validator's \(optional\) security contact email |

#### Create a validator <a id="create-a-validator"></a>

```text
zenchaind tx staking create-validator --chain-id=lotus-tesnet --from=<key-name> --fees=300000uzen --pubkey=<validator-pubKey> --commission-rate=0.1 --amount=1000000000uzen --moniker=<validator-name>
```

### Staking edit-validator <a id="iris-tx-staking-edit-validator"></a>

Edit an existing validator's settings, such as commission rate, name, etc.

```text
zenchaind tx staking edit-validator [flags]
```

**Flags:**

| Name, shorthand | type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- |
| --commission-rate | float |  | 0.0 | Commission rate percentage |
| --moniker | string |  |  | Validator name |
| --identity | string |  |  | Optional identity signature \(ex. UPort or Keybase\) |
| --website | string |  |  | Optional website |
| --details | string |  |  | Optional details |
| --security-contact | string |  |  | The validator's \(optional\) security contact email |
| --min-self-delegation | string |  |  | The minimum self delegation required on the validator |

#### Edit validator information <a id="edit-validator-information"></a>

```text
zenchaind tx staking edit-validator --from=<key-name> --chain-id=lotus-testnet --fees=30000uzen --commission-rate=0.10 --moniker=<validator-name>
```

#### Unjailed 

```text
zenchaind tx slashing unjail --from <wallet_name>
```

