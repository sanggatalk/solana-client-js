# solana-client-js

Solana library for managing wallet and transfering tokens.

## Installation

```bash
  npm install solana-client-js
```

## Initialize

```javascript
  const { Solana } = require('solana-client-js');

  const conn = new Solana();
```

## APIs

### Store wallets

``` javascript
  // Add wallet(name, secretKeyArray)
  conn.addWallet('myWallet', [106,241,17,...,25,111,29,121,118]);

  // Add destination (name, publicKey)
  conn.addDestination('myReceiver', "8z4Wq1gz1u...kNZcDS77KLq");

  console.log(conn.wallets['myWallet'], conn.destinations['myReceiver']);
```

### Transfer tokens

``` javascript
  /*
    ...
    store sender's wallet, payer's wallet and receiver's publicKey
    ...
  */

  const transfers = [
    {walletName: 'sender', destinationName: 'receiver', amount: 1},
    {walletName: 'sender', destinationName: 'receiver', amount: 2}
  ]

  const res = await conn.transferTokens(transfers, 'payer');

  console.log('signatures:', res);
```

## To do

1. Configurations
2. Get Infoes
3. Get Transaction Histories
4. Divide payer wallets and normal wallets. (like destination pubKey)

## Contributors

[GGULBAE][link_to_GGULBAE]

[link_to_GGULBAE]: https://github.com/GGULBAE "Go GGULBAE GIT"
