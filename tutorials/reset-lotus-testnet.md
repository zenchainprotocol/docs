# Reset Lotus-testnet

#### Time to start new Lotus-testnet

{% hint style="info" %}
**Fri, 08 May 2021 00:00:00 GMT**

\*\*\*\*[**https://www.timeanddate.com/countdown/roadtrip?iso=20210507T12&p0=%3A&msg=Lotus-testnet+reset&font=cursive**](https://www.timeanddate.com/countdown/roadtrip?iso=20210508T00&p0=%3A&msg=Lotus-testnet+reset&font=cursive)\*\*\*\*
{% endhint %}

#### Overview <a id="download-the-genesis-file"></a>

To reset Lotus-testnet, you just clear data of the old blockchain and replace genesis.json file, don't need to download zenchaind again. Your wallet keys will not clear. You can still access it. 

{% hint style="warning" %}
You must install success fullnode and run it. If you did not install zenchaind application, please install it. Please check this link to install your full node

[https://docs.zenchain.co/network/validators/node-setup](https://docs.zenchain.co/network/validators/node-setup)
{% endhint %}



### Steps:

#### Step1: Download the Genesis File <a id="download-the-genesis-file"></a>

Download the New Lotus-testnet [genesis.json](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json) file to replace the old genesis.json file in .zenchain config directory.



{% tabs %}
{% tab title="Linux & MacOS" %}
```text
cd $HOME/.zenchain/config
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

