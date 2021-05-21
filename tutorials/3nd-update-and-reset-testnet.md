# \[3nd\] Update and reset testnet



#### Time to start new Lotus-testnet

{% hint style="info" %}
**21 May 2021 16:00:00 GMT**

**Check here** [**https://scan.zenchain.network/**](https://scan.zenchain.network/)\*\*\*\*
{% endhint %}

#### Overview <a id="download-the-genesis-file"></a>

To upgrade and reset Lotus-testnet, you need backup your zenwallet and start over.  

+ Step 1: Backup zenwallet.

+ Step 2: Clear old data

+ Step 3: Setup fullnode

+ Step 4: Import your wallet

+ Step 5: Start your node 

+ Step 6: Create validator

### Steps:

**Step1: Backup zenwallet**

If you save your bip39 mnemonic, you can move next step.

In case you don't save your bip39 mnemonic, run this command to export your private key

```text
zenchaind keys export <your_wallet_name>
```

With &lt;your\_wallet\_name&gt; is name of wallet store on your machine. If you don't remember it, please run 

**`zenchaind keys list`** 

To show all wallet in your machine

Then zenchaind will ask password, please input the password \(password must be at least 8 characters\). Your export content will show on the console. 

Copy content and save new file with name **zenkey**

`-----BEGIN TENDERMINT PRIVATE KEY----- kdf: bcrypt salt: 0334FDC79D23EDFD3849E121F5A6595C type: secp256k1`

`vApAKO4ARAeEba4Hjb7unUl7HAXfIGNYNZln9LkYXKrG5Uqi37HdDw3nYM0a2++K e4MbVcVqVD6dPfsr/pQ9++BVl8FwiCIvnxL2tEo= =dL63 -----END TENDERMINT PRIVATE KEY-----`

#### Step 2: Clear old data <a id="download-the-genesis-file"></a>

{% hint style="danger" %}
This command will delete all data include your private key. Please backup before do it
{% endhint %}

{% tabs %}
{% tab title="Linux" %}
```text
rm -rdf ~/.zenchain
```
{% endtab %}

{% tab title="window" %}
```text
rmdir /s %UserProfile%/.zenchain
```
{% endtab %}
{% endtabs %}



#### Step 3: Setup new node

{% tabs %}
{% tab title="Linux & MacOS" %}
Ensure your system installed **`wget, unzip`** app

```text
cd ~
wget https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign-dex/SetupNode.sh
chmod 777 SetupNode.sh
./SetupNode.sh
```
{% endtab %}

{% tab title="Window" %}
**1.Download zenchaind.exe app**

Access [link ](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.5/build-windows-amd64.zip)with to download zenchaind v1.1.15

Unzip file you will get zenchaind.exe

**2. Init your node**

Open cmd, and cd to folder contain zenchaind.exe file and init node

```text
zenchaind init <your_moniker_name> --chain-id=lotus-testnet
```

* **Notice: Replace &lt; your\_** _**moniker\_**_ **name&gt; with any name you want. This is your node name.** 

This command will create .zenchain folder at **`%UserProfile%/.zenchain`** to store node data and config

**3. Download genesis file**

Download genesis.json and replace file at **`%UserProfile%/.zenchain/config/genesis.json`**

Link to download genesis.json: 

[https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign-dex/genesis.json](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign-dex/genesis.json)

**4: Add persistent\_peers to config.toml file.**   
Open **`%UserProfile%/.zenchain/config/config.toml`**

 Find line begin with **`persistent_peers`** and replace like this. 

```text
persistent_peers = "78f903fd4bd8c110ffbe05e1e21028827723bb2e@seeds.zenchain.network:26656"
```
{% endtab %}
{% endtabs %}

#### Step 4: Restore your zenwallet  <a id="download-the-genesis-file"></a>

If you have nmemnic run this command

```text
zenchaind keys add <new_name> --recover
```

If you using export to key file 

```text
zenchaind keys import <new_name> <link_to_key_file>
```

#### Step 5: Start your node

```text
zenchaind start
```

{% hint style="info" %}
If you run this command before **21 May 2021 16:00:00 GMT.**   
Your node will wait until **21 May 2021 16:00:00 GMT** to sync the network.
{% endhint %}

![](../.gitbook/assets/image%20%2823%29.png)

#### Step 6: Create validator transaction

After you got sync with the new blockchain 

1. Check your balance.
2. Make create validator transaction again. If you don't remember, please visit this [link](../network/validators/creating-a-validator.md)

{% hint style="danger" %}
Please using new validator address, to get the validator address using this command  
**`zenchaind tendermint show-validator`**
{% endhint %}

**\`\`**

