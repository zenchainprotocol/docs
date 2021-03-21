# Metamask

MetaMask is an extension for accessing ZenChain enabled distributed applications or "Dapps" in your browser!

The extension injects the web3 API into every website's javascript context so that dapps can read from the blockchain.

## Installing Metamask <a id="installing-metamask"></a>

Click [here](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn) to install the Metamask extension on your browser. It can be installed using the Google Chrome Browser. Just click on the installation button and it should be automatically installed.

## Setting up Metamask <a id="setting-up-metamask"></a>

By default Metamask supports the Ethereum blockchain, but since ZenChain is EVM compatible with Ethereum, it can be used the same way by setting a custom RPC endpoint.

### 1. Adding a Custom RPC Endpoint <a id="1-adding-a-custom-rpc-endpoint"></a>

In order to connect to the ZenChain Network, a custom RPC Endpoint needs to be added. On top click on the network you are connect to and and then on **Custom RPC**:![](https://gblobscdn.gitbook.com/assets%2F-LlEOlYqEG_GKuO5Rehq%2F-MSiDsMgX_nzpe3GMUWo%2F-MSiGgaeYvXA0Ekamwnq%2Fmetamask_custom_rpc1.png?alt=media&token=a7a47120-5345-4d02-8a00-816d428ed4a9)Adding a Custom RPC

### 2. Filling the Endpoint Information <a id="2-filling-the-endpoint-information"></a>

Fill it accordingly to the ZenChain Network you want to to connect to.

Use the RPC URL of Shard 0 if you want to send/receive transactions from exchanges or do any staking transaction type.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Mainnet</th>
      <th style="text-align:left">Testnet</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Network Name</b>
      </td>
      <td style="text-align:left">ZenChain Mainnet</td>
      <td style="text-align:left">ZenChain Testnet</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>New RPC URL</b>
      </td>
      <td style="text-align:left">&#x200B;https://rpc.zenchain.network&#x200B;</td>
      <td style="text-align:left">&#x200B;https://rpctest.zenchain.network</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Chain ID</b>
        </p>
        <p>(use number only)</p>
      </td>
      <td style="text-align:left">0x1</td>
      <td style="text-align:left">0x2</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Currency symbol (optional)</b>
      </td>
      <td style="text-align:left">ZEN</td>
      <td style="text-align:left">ZEN</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Block Explorer URL (optional)</b>
      </td>
      <td style="text-align:left">&#x200B;<a href="https://scan.zenchain.co">https://scan.zenchain.co</a>
      </td>
      <td style="text-align:left">&#x200B;&#x200B;<a href="https://scantest.zenchain.co">https://scantest.zenchain.co</a>
      </td>
    </tr>
  </tbody>
</table>

Click now on the Save button and your configuration should be done!

## Creating a New Account <a id="creating-a-new-account"></a>

In order to create a new account, click on the icon on top as shown by the image below and then on **Create Account**:![](https://gblobscdn.gitbook.com/assets%2F-LlEOlYqEG_GKuO5Rehq%2F-MSiOV7Y4hnCYH2nrBMk%2F-MSiR_c_xSkagNurF9Vo%2Fmetamask_create_account1.png?alt=media&token=3a36d493-2097-4dda-b7ac-b62f66fa9d74)Create Account

On next window, fill it with the account you want to choose and click on **Create** button. You should have succesfully created a new account!

## Importing an Account <a id="importing-an-account"></a>

### 1. Using a Private Key <a id="1-using-a-private-key"></a>

Click on the icon on top as shown by the image below and then on **Import Account**:![](https://gblobscdn.gitbook.com/assets%2F-LlEOlYqEG_GKuO5Rehq%2F-MSiOV7Y4hnCYH2nrBMk%2F-MSiPPqBKW0_Z-pIK6no%2Fmetamask_import_account1.png?alt=media&token=478b43a1-924f-4191-9d51-1469af259bf9)Importing Account

On next window, select the option to import from a Private Key, paste your key and click on **Import** button:![](https://gblobscdn.gitbook.com/assets%2F-LlEOlYqEG_GKuO5Rehq%2F-MSiOV7Y4hnCYH2nrBMk%2F-MSiQ7DiAJuD4QjaPyuC%2Fmetamask_import_account2.png?alt=media&token=537a88a3-13c3-4fed-9b42-081c4b2c60b7)

You should have successfully imported your account from the Private Key!

