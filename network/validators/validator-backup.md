# Validator backup

## Overview

You need to backup 2 things when move to new machine

+ Your zenwallet: is keep your token

+ Your validator private file: **`priv_validator_key.json`** this is file to using sign when produce blocks. If you lost it, your validator will never sign block and will got jail and slashing

## Backup your zenwallet

Have 2 types to backup zenwallet: using mnemonic or using file key. 

Using mnemonic: Mnemonic seed words just show ONE TIME when you create a wallet. If you did not use the export function

```text
zenchaind keys export <Wallet_name>
```

Then type your password and your backup key will show on screen, then copy it and save to file. 

## Restore your zenwallet

1. Using mnemonic 

```text
zenchaind keys add <YourWalletName> --recover
```

Then typing your seed words to recover

2. Using import command

```text
zenchaind keys import <YourWalletName> path_to_key_file
```

Example: With your backup key is key.txt, and your name is Jove

`zenchaind keys import Jove key.txt`

## Backup & Restore your node privatekey

Copy file .zenchain/config/priv\_validator\_key.json

In new machine, replace priv\_validator\_key.json in .zenchain/config/ folder

