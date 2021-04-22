# Add your wallet

The keyring holds the private/public keypairs used to interact with a node. For instance, a validator key needs to be set up before running the blockchain node, so that blocks can be correctly signed. The private key can be stored in different locations, called "backends", such as a file or the operating system's own key storage.

### Create or import wallet

Assume you setup successful **`zenchaind`** application

To add new key using following command

```text
zenchaind keys add <name-your-wallet> 
```

This command will generate your wallet and your mnemoic words, keep this 

Incase you have mnemonic backup, you can recove sing command

```text
zenchaind keys add <name-your-wallet> --recover
```

###  Show your wallet <a id="available-backends-for-the-keyring"></a>

```text
zenchaind keys list
```



