# Requirements

* bash (or [baids][baids])
* jq
* lsof (linux only) 

# Installation

* Clone this repository:
```
git clone https://github.com/GimbaLabs/baids-daedalus.git ~/.baids/functions.d/baids-daedalus
```
* Load functions using baids/bash

## Using baids

`baids-reload`

## Plain bash

```
source baids-daedalus/*
```

# Usage

* Open Daedalus wallet app
* Add any wallet (hardware or not) and write down its name (upper/lower case matters!)
* Open a terminal window and bring up a `cardano-wallet` instance that uses Daedalus' db
```
daedalus-cli-run-cardano-wallet
```
* Open another terminal and try to send a transaction tagged with some metadata (it will ask you for your passphrase):
```
daedalus-cli-send-tx-with-metadata-string \
  $DAEDALUS_WALLET_NAME \
  $LOVELACE_AMOUNT \
  $DESTINATION_ADDRESS \
  write anything here and it will be attached as metadata, for example: ORDER_ID=42
```

# Example

[![asciicast](https://asciinema.org/a/377053.svg)](https://asciinema.org/a/377053)

[baids]: https://github.com/rcmorano/baids
