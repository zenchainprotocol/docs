# Add your wallet

The keyring holds the private/public keypairs used to interact with a node. For instance, a validator key needs to be set up before running the blockchain node, so that blocks can be correctly signed. The private key can be stored in different locations, called "backends", such as a file or the operating system's own key storage.

### Create or import a wallet

Assume you setup successful **`zenchaind`** application

To add a new key using the following command

```text
zenchaind keys add <name-your-wallet> 
```

This command will generate your wallet and your mnemonic words, keep this 

In case you have a mnemonic backup, you can recover sing command

```text
zenchaind keys add <name-your-wallet> --recover
```

###  Show your wallet <a id="available-backends-for-the-keyring"></a>

```text
zenchaind keys list
```



