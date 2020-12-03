# Overview

This ~100 lines of bash code enables anyone using Daedalus to send metadata-rich transactions today.

We encourage you to try on Testnet first. For this, you can download [Daedalus for Testnet][daedalus-testnet], ask for some funds in [the faucet][testnet-faucet] and, maybe, check the metadata went through using GimbaLabs' [postgREST][gimbalabs-postgrest] endpoint!

[daedalus-testnet]: https://developers.cardano.org/en/testnets/cardano/get-started/wallet/
[testnet-faucet]: https://developers.cardano.org/en/testnets/cardano/tools/faucet/
[gimbalabs-postgrest]: https://gimbalabs.com/#/open-source-apis/postgrest-api

# Requirements

* Daedalus
* bash (or [baids][baids])
* jq
* lsof (linux only) 

[baids]: https://github.com/rcmorano/baids

# Installation

* Clone this repository:
```
git clone https://github.com/GimbaLabs/baids-daedalus.git ~/.baids/functions.d/baids-daedalus
```
* Load functions using baids/bash
```
# Using baids
baids-reload
# Using plain bash
source baids-daedalus/*
```

# Usage

* Open Daedalus wallet app
* Add any wallet (hardware or not) and write down its name (upper/lower case matters!)
* Open a terminal window and bring up a `cardano-wallet` instance that uses Daedalus' db
```
daedalus-cli-run-cardano-wallet
```
* Open another terminal and try to send a transaction tagged with some metadata (it will ask you for your spending password):
```
daedalus-cli-send-tx-with-metadata-string \
  $DAEDALUS_WALLET_NAME \
  $LOVELACE_AMOUNT \
  $DESTINATION_ADDRESS \
  maybe,put,some,csv,row,here,order_id=42
```

# Example

[![asciicast](https://asciinema.org/a/377053.svg)](https://asciinema.org/a/377053)
