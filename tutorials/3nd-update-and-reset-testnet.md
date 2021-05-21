# \[3nd\] Update and reset testnet



#### Time to start new Lotus-testnet

{% hint style="info" %}
**Fri, 21 May 2021 16:00:00 GMT**

**Check here** [**https://scan.zenchain.network/**](https://scan.zenchain.network/)\*\*\*\*
{% endhint %}

#### Overview <a id="download-the-genesis-file"></a>

To upgrade and reset Lotus-testnet, you need backup your zenwallet and start over.  

+ Step 1: Backup zenwallet.

+ Step 2: Clear old data

+ Step 3: Setup fullnode

+ Step 4: Import your wallet

+ Step 5: Create validator

{% hint style="warning" %}
You must install success fullnode and run it. If you did not install zenchaind application, please install it. Please check this link to install your full node

[https://docs.zenchain.co/network/validators/node-setup](https://docs.zenchain.co/network/validators/node-setup)
{% endhint %}



### Steps:

Step1: Backup zenwallet

Ensure you still keep older

#### Step1: Download the Genesis File <a id="download-the-genesis-file"></a>

Download the New Lotus-testnet [genesis.json](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json) file to replace the old genesis.json file in `.zenchain` config directory.



{% tabs %}
{% tab title="Linux & MacOS" %}
```text
cd $HOME/.zenchain/config
rm genesis.json
wget https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json
```
{% endtab %}

{% tab title="Window" %}
Access [link ](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json)with browser and save it to your machine

Replace genesis.json in folder located in **%UserProfile%/ .zenchain/config** 

**`Notice:`**

_`%UserProfile%`_ `will automatic redirect to current user root folder.` 

**`Example:`** _`C:\Users\`**`<YourLoginNameWillHere>`**`\.zenchain`_
{% endtab %}
{% endtabs %}

#### Step 2: Reset your node <a id="download-the-genesis-file"></a>

```text
zenchaind unsafe-reset-all
```

#### Step 3: Start your node

```text
zenchaind start
```

{% hint style="info" %}
If you run this command before **Fri, 08 May 2021 00:00:00 GMT.**   
Your node will wait until **Fri, 08 May 2021 00:00:00 GMT** to sync the network.
{% endhint %}

![](../.gitbook/assets/image%20%2823%29.png)

#### Step 4: Create validator transaction

After you got sync with the new blockchain 

1. Check your balance.
2. Make create validator transaction again. If you don't remember, please visit this [link](../network/validators/creating-a-validator.md)

