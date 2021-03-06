# Full Node Setup

## Prerequisites <a id="9cbf"></a>

* Make sure your provisioned EC2 machine meets the following requirements:
  * **Hardware:**
    * Minimum**:** 2 vCPU, 4 GB RAM
    * Recommended: 4vCPU, 8 GB RAM
  * **Storage**:
    * Minimum: 50GB SSD
    * Recommended: &gt;= 100 GB SSD. 200GB to be on the safer side.
    * Notes:
      * An archival node \(pruning = "nothing" \) grows at a rate of ~50 GB per month
      * A fully pruning node \(pruning = "everything" \) grows at a rate of ~10 GB per month
      * A default pruning node \(\`pruning = “default”\) grows at a rate of ~20 GB per month

## 

{% hint style="info" %}
You have 2 options to setup

1. Start node from prebuild node application
2. Build from source code
{% endhint %}



## Options 1. Start node from prebuild node application

We will follow these steps

1. Download built zenchaind
2. Init zenchaind
3. Download genesis file and replace local file
4. Add persistent peers 
5. Run node

## 1.1 With Linux amd 64bit

Step 1: Download SetupNode.sh

```bash
wget https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign-dex/SetupNode.sh
```

Step 2: Allow run SetupNode.sh

```text
chmod 777 ./SetupNode.sh
```

Step 3: Make sure you have `unzip` app installed

Step 4: If you want to run zenchaind in background. Your system needs to install **`tmux`**. 

Start a new session with tmux, just type command tmux. 

```text
tmux
```

The terminal will begin green in the bottom, this is tmux opened. 

![\(Tmux open success with green at the bottom\)](../../.gitbook/assets/image%20%2821%29.png)

If your system doesn't know `tmux` please install it. 

[https://linuxize.com/post/getting-started-with-tmux/](https://linuxize.com/post/getting-started-with-tmux/)

**Step 5:** Run SetupNode.sh to download **`zenchaind`**, genesis file and persistent peers information. 

```text
./SetupNode.sh
```

**Step 6:** Zenchain will ask your moniker's name. This is your node name. 

**Step 7:** After that, your node will sync with the network. If you want to run this chain in background, you can detach this tmux session. 

{% hint style="info" %}
If you want to run zenchaind in background, you can detach this tmux session by command

Press **`<ctr+b>`** then press **`d`** 

**More information here:** [**https://superuser.com/questions/249659/how-to-detach-a-tmux-session-that-itself-already-in-a-tmux**](https://superuser.com/questions/249659/how-to-detach-a-tmux-session-that-itself-already-in-a-tmux)\*\*\*\*
{% endhint %}

**Step 8:** If you want to become a validator you need to [add your wallet](add-your-wallet.md) \(this will store all your ZEN token\), and make [create a validator transaction](creating-a-validator.md) to the network.

### 1.2 With Window amd64bit

**Step 1:** Download prebuild zenchaind at link 

[https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.5/build-windows-amd64.zip](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/build/v1.1.5/build-windows-amd64.zip)

Exact zip file, we will get **`zenchaind.exe`** binary 

**Step 2:** Open cmd, and cd to folder contain zenchaind.exe file and init node

```text
zenchaind init <your_moniker_name> --chain-id=lotus-testnet
```

* **Notice: Replace &lt; your\_** _**moniker\_**_ **name&gt; with any name you want. This is your node name.** 

This command will create .zenchain folder at **`%UserProfile%/.zenchain`** to store node data and config

**Step 3:** Download genesis.json and replace file at **`%UserProfile%/.zenchain/config/genesis.json`**

Link to download genesis.json: [**https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json**](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign/genesis.json)\*\*\*\*

**Step 4:** Add persistent\_peers to config.toml file.   
Open **`%UserProfile%/.zenchain/config/config.toml`**

 Find line begin with **`persistent_peers`** and replace like this. 

```text
persistent_peers = "78f903fd4bd8c110ffbe05e1e21028827723bb2e@seeds.zenchain.network:26656"
```

**Step 5:** Run your node

```text
zenchaind start
```

**Step 6:** After that, your node will sync with the network. If you want to become a validator you need to [add your wallet](add-your-wallet.md) \(this will store all your ZEN token\), and make [create a validator transaction](creating-a-validator.md) to the network.

{% hint style="warning" %}
If you want to run zenchaind in the background, **`you do not close this cmd window`**, to run another zenchaind command just open a new cmd window and run zenchaind command.
{% endhint %}

## **Option 2. Build from source \(More complicated - For advanced users\)**

### Install `go` <a id="install-go"></a>

{% hint style="info" %}
**Go 1.15+** is required for building and installing the zenchaind software.

Install `go` by following the [official docs](https://golang.org/doc/install).
{% endhint %}

Remember to set your `$GOPATH`, `$GOBIN`, and `$PATH` environment variables, for example:

```text
mkdir -p $HOME/go/bin
echo "export GOPATH=$HOME/go" >> ~/.bashrc
source ~/.bashrc
echo "export GOBIN=$GOPATH/bin" >> ~/.bashrc
source ~/.bashrc
echo "export PATH=$PATH:$GOBIN" >> ~/.bashrc
source ~/.bashrc
```

Verify that `go` has been installed successfully

```text
go version
```

### Install `zenchaind` <a id="install-iris"></a>

After setting up `go` correctly, you should be able to compile and run `zenchaind`.

Make sure that your server can access to google.com because our project depends on some libraries provided by google. \(If you are not able to access google.com, you can also try to add a proxy: `export GOPROXY=https://goproxy.io`\)

```text
git clone https://github.com/zenchainprotocol/zenchain
cd zenchain
git checkout v1.1.4
make build
```

If your environment variables have set up correctly, you should not get any errors by running the above commands

Your **`zenchaind`** will build and save to **`zenchain/build/`** folder. 

Add runable right for zenchaind   

```text
chmod 777 ./build/zenchaind
```

\(Optional step\) To run zenchaind we will copy zenchaind to /usr/local/bin folder to run zenchaind command

```text
cp -f ./build/zenchaind /usr/local/bin/
```

Now check your `zenchaind` version.

```text
zenchaind version
```

### Init node and join testnet

**Step 1:** You will  get zenchaind

**Step 2:** Init node

```text
zenchaind init <your_moniker_name> --chain-id=lotus-testnet
```

This command will create .zenchain folder at **`~/.zenchain`** to store node data and config

**Step 3:** Download genesis.json and replace file at **`~/.zenchain/config/genesis.json`**

\*\*\*\*[**https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign-dex/genesis.json**](https://raw.githubusercontent.com/zenchainprotocol/Launchpad/main/Lotus-testnet-campaign-dex/genesis.json)\*\*\*\*

**Step 4:** Add persistent\_peers to config.toml file.   
Open **`~/.zenchain/config/config.toml`**

 Find line begin with **`persistent_peers`** and replace like this. 

```text
persistent_peers = "78f903fd4bd8c110ffbe05e1e21028827723bb2e@seeds.zenchain.network:26656"
```

**Step 5:** Run your node

```text
zenchaind start
```

