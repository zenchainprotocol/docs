# Reset Lotus-testnet

#### Time to start new Lotus-testnet

{% hint style="info" %}
**Fri, 08 May 2021 00:00:00 GMT**

\*\*\*\*[**https://www.timeanddate.com/countdown/roadtrip?iso=20210507T12&p0=%3A&msg=Lotus-testnet+reset&font=cursive**](https://www.timeanddate.com/countdown/roadtrip?iso=20210508T00&p0=%3A&msg=Lotus-testnet+reset&font=cursive)\*\*\*\*
{% endhint %}

#### Overview <a id="download-the-genesis-file"></a>

To reset Lotus-testnet, you just clear data of the old blockchain and replace genesis.json file, don't need to download zenchaind again. 

### Steps:

#### Step1: Download the Genesis File <a id="download-the-genesis-file"></a>

Download the New Lotus-testnet [genesis.json](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json) file to replace old genesis.json file in .zenchain config directory.

```text
cd $HOME/.zenchain/config
wget https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json
```

#### Step 2: Reset your node <a id="download-the-genesis-file"></a>

```text
zenchaind unsafe-reset-all
```

#### Step 3: Start your node

```text
zenchaind start
```

#### Step 4: Create validator transaction

After you got sync with the new blockchain 

1. Check your balance
2. Make create validator transaction again.

