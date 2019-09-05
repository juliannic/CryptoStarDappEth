# Build CryptoStar Dapp On Ethereum

## Supply Chain Management Service

### Contract Address

- Migrations: 
- StarNotary Token: 
### My Token

- Name: 
- Symbol: 
- ID: 

### Library

- `truffle-hdwallet-provider`:  used to deploy the contract to Rinkeby Network

### `lite-server`

This project uses `lite-server` module to deploy Web Front-end Interface.

### Program Version Numbers

- Truffle v5.0.30 (core: 5.0.30)
- Solidity v0.5.0 (solc-js)
- Node v10.14.2
- Web3.js v^1.2.0

## How to Run

1. Compile contract codes

```bash
$ truffle compile
```

2. Migrate

```bash
$ truffle migrate
```

3. Test

```bash
$ truffle test
```
![](./test/test.png)

4. Deploy

  1. Make an `Infura` Project, get `ENDPOINT` of `Rinkeby`

  2. add `truffle-hdwallet-provider` npm module
  ```bash
  $ npm install --save-dev truffle-hdwallet-provider
  ```

  3. Use HD Wallet Provider in `truffle.js`
  ```js
  const HDWalletProvider = require('truffle-hdwallet-provider')
  require('dotenv').config() // DO NOT PROVIDE CREDENTIAL DIRECTLY
  module.exports = {
    networks: {
      // ...
      rinkeby: {
        provider: new HDWalletProvider(wallet, apiKey),
        network_id: 3
      }
    }
  }
  ```

  4. Create `.env` file to provide secret credentials
  ```
  apiKey=<INFURA_API_KEY>
  wallet=<MNEMONIC_OF_WALLET>
  ```

  5. Check if the wallet used has enough ETH. If not, get from public faucet.

  6. Deploy in the network
  ```bash
  $ truffle migrate --network rinkeby
  ```

![](./test/deploy.png)

5. Run Web UI

```bash
& npm run build
$ npm run dev
```
