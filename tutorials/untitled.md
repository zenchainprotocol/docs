# Reset Lotus-testnet

#### Time to start new Lotus-testnet

{% hint style="info" %}
**Fri, 07 May 2021 12:00:00 GMT**

\*\*\*\*[**https://www.timeanddate.com/countdown/roadtrip?iso=20210507T12&p0=%3A&msg=Lotus-testnet+reset&font=cursive**](https://www.timeanddate.com/countdown/roadtrip?iso=20210507T12&p0=%3A&msg=Lotus-testnet+reset&font=cursive)\*\*\*\*
{% endhint %}

#### Download the Genesis File <a id="download-the-genesis-file"></a>

Download the New Lotus-testnet [genesis.json](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json) file to replace old genesis.json file in .zenchain config directory.

```text
cd $HOME/.zenchain/config
wget https://raw.githubusercontent.com/binance-chain/node-binary/master/fullnode/te
```

#### Reset your node <a id="download-the-genesis-file"></a>

```text
zenchaind unsafe-reset-all
```

#### Start your node

```text
zenchaind start
```



