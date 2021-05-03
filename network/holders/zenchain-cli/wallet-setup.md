# Wallet setup

Overview: 

1. Download zenchaind app
2. Create or import wallet
3. Interact with zenchain

## Download zenchaind app

{% tabs %}
{% tab title="Linux " %}
Run wget

```text
wget https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.4/build-linux-amd64.zip
```

Exact zip

```text
unzip build-linux-amd64.zip
```

Run zenchaind

```text
cd build-linux-amd64
./zenchaind
```

If it return value is installed successfully

> Stargate CosmosHub App
>
> Usage: zenchaind \[command\]
>
> Available Commands:
>
> add-genesis-account Add a genesis account to genesis.json collect-gentxs Collect genesis txs and output a genesis.json file debug Tool for helping with debugging your application export Export state to JSON gentx Generate a genesis tx carrying a self delegation help Help about any command init Initialize private validator, p2p, genesis, and application configuration files keys Manage your application's keys migrate Migrate genesis to a specified target version query Querying subcommands start Run the full node status Query remote node for status tendermint Tendermint subcommands tx Transactions subcommands unsafe-reset-all Resets the blockchain database, removes address book files, and resets data/priv\_validator\_state.json to the genesis state validate-genesis validates the genesis file at the default location or at the location passed as an arg version Print the application binary version information
>
> Flags: -h, --help help for zenchaind --home string directory for config and data \(default "/root/.zenchain"\) --log\_format string The logging format \(json\|plain\) \(default "plain"\) --log\_level string The logging level \(trace\|debug\|info\|warn\|error\|fatal\|panic\) \(default "info"\) --trace print out full stack trace on errors
>
> Use "zenchaind \[command\] --help" for more information about a command.
{% endtab %}

{% tab title="MacOS" %}
Run wget

```text
https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.4/build-darwin-amd64.zip

```

Exact zip file

```text
unzip build-darwin-amd64.zip
```

Run zenchaind

```text
cd build-darwin-amd64
./zenchaind
```

If it return value is installed successfully

> Stargate CosmosHub App
>
> Usage: zenchaind \[command\]
>
> Available Commands:
>
> add-genesis-account Add a genesis account to genesis.json collect-gentxs Collect genesis txs and output a genesis.json file debug Tool for helping with debugging your application export Export state to JSON gentx Generate a genesis tx carrying a self delegation help Help about any command init Initialize private validator, p2p, genesis, and application configuration files keys Manage your application's keys migrate Migrate genesis to a specified target version query Querying subcommands start Run the full node status Query remote node for status tendermint Tendermint subcommands tx Transactions subcommands unsafe-reset-all Resets the blockchain database, removes address book files, and resets data/priv\_validator\_state.json to the genesis state validate-genesis validates the genesis file at the default location or at the location passed as an arg version Print the application binary version information
>
> Flags: -h, --help help for zenchaind --home string directory for config and data \(default "/root/.zenchain"\) --log\_format string The logging format \(json\|plain\) \(default "plain"\) --log\_level string The logging level \(trace\|debug\|info\|warn\|error\|fatal\|panic\) \(default "info"\) --trace print out full stack trace on errors
>
> Use "zenchaind \[command\] --help" for more information about a command.
{% endtab %}

{% tab title="Windows" %}
Link download  
[https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.4/build-windows-amd64.zip](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.4/build-windows-amd64.zip)  
Unzip it

Start cmd at location unzip and try to run command

```text
zenchaind
```

If return value is installed successfully

> Stargate CosmosHub App
>
> Usage: zenchaind \[command\]
>
> Available Commands:
>
> add-genesis-account Add a genesis account to genesis.json collect-gentxs Collect genesis txs and output a genesis.json file debug Tool for helping with debugging your application export Export state to JSON gentx Generate a genesis tx carrying a self delegation help Help about any command init Initialize private validator, p2p, genesis, and application configuration files keys Manage your application's keys migrate Migrate genesis to a specified target version query Querying subcommands start Run the full node status Query remote node for status tendermint Tendermint subcommands tx Transactions subcommands unsafe-reset-all Resets the blockchain database, removes address book files, and resets data/priv\_validator\_state.json to the genesis state validate-genesis validates the genesis file at the default location or at the location passed as an arg version Print the application binary version information
>
> Flags: -h, --help help for zenchaind --home string directory for config and data \(default "/root/.zenchain"\) --log\_format string The logging format \(json\|plain\) \(default "plain"\) --log\_level string The logging level \(trace\|debug\|info\|warn\|error\|fatal\|panic\) \(default "info"\) --trace print out full stack trace on errors
>
> Use "zenchaind \[command\] --help" for more information about a command.
{% endtab %}
{% endtabs %}

## Create wallet

```text
zenchaind keys add <new key>
```

![](../../../.gitbook/assets/image%20%2820%29.png)

{% hint style="danger" %}
Please save mnemonic on a safe place to restores wallet, this mnemonic just show **`ONE`** time
{% endhint %}

## Restore wallet

```text
zenchaind keys add <new key> --recover
//Type your mnemonic to restore
[root@Binann ~]# zenchaind keys add RecoverName --recover
> Enter your bip39 mnemonic
choice toilet hood soft program finish protect game enter orchard enjoy phone bone divert almost aspect cabbage cube mountain couple erupt short scrub own
```

## Run command

You have 2 options to interact with zenchain

1. Run your fullnode and interact with zenchain by your full node

{% page-ref page="../../validators/node-setup.md" %}

2. Connect zenchaind to remote RPC at http://node1.zenchain.network:26657

Each command just add **`--node tcp://node1.zenchain.network:26657`**

Example 

```text
//Query block
zenchaind q block --node tcp://node1.zenchain.network:26657
```

```text
//Query balance
zenchaind q bank balances <your zen address> --node tcp://node1.zenchain.network:26657
```

