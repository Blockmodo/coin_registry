<p align="center">
    <img 
        width="400px"
        src="https://github.com/Blockmodo/art/blob/master/coin_registry/output/coin_registry_logo@3x.png"
        srcset="https://github.com/Blockmodo/art/blob/master/coin_registry/output/coin_registry_logo@2x.png.png 2x,
                                 https://github.com/Blockmodo/art/blob/master/coin_registry/output/coin_registry_logo@3x.png.png 3x"
    />
</p>

[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)
[![Chat on Telegram](https://img.shields.io/badge/Chat%20on-Telegram-brightgreen.svg)](https://t.me/blockmodo_developers)
[![Twitter blockmodo](https://img.shields.io/badge/twitter-blockmodo-green.svg)](http://twitter.com/blockmodo)

## Introduction

Coin Registry is a collection of JSON formatted information files that is primarily used by website developers, exchange operators, terminal developers, and news publications to show accurate information about different coins. 

### The Payload

A COINREGISTRY JSON information file: 

```javascript
{
	"type": "COINREGISTRY",
	"version": 1,
	"name": "Ethereum",
	"fromSymbol": "ETH",
	"toSymbol":"ALL",
	"website": "https://www.ethereum.org/",
	"images": {
		"image64": "https://image_path/img.jpg",
		"image128": "https://image_path/img.jpg",
		"image256": "https://image_path/img.jpg",
		"image512": "https://image_path/img.jpg",
		"image1024": "https://image_path/img.jpg"
	},
	"network": {
		"t_total_supply": 17104062,
		"t_available_supply": 17104062,
		"t_max_supply": 21000000,
		"t_block_reward": 12.5
	},
	"wallets": [
    	"https://neptune.so"
  	],
	"is_crypto": true,
	"is_minable": true,
	"proof_type": "PoW",
	"algorithm": "Ethash",
	"description": {
		"en": "Ethereum is an open-source, public, blockchain-based distributed computing platform and operating system featuring smart contract functionality. It supports a modified version of Nakamoto consensus via transaction-based state transitions."
	},
	"quote": [
		"https://blockmodo.com/quotes/ETH"
	],
	"explorer": [
		"https://etherscan.io/"
	],
	"chat": [
		"https://telegram.me/joinchat/AyAwgj-vtnMdUxRvCgicuQ"
	],
	"social": [
		"https://twitter.com/ethereum",
		"https://www.facebook.com/ethereumproject/"
	],
	"community": [
		"https://www.reddit.com/r/ethereum",
		"https://www.reddit.com/r/ethtrader"
	],
	"source_code": [
		"https://github.com/ethereum/go-ethereum",
		"https://github.com/ethereum/cpp-ethereum"
	]
}
```

### Description of Fields

> root → type

The Blockmodo API always assigns type names to Payloads for easy parsing. In this particular case, the type will always be "COINREGISTRY" for this payload.

> root → version

The version of the payload. From time to time, Blockmodo, or its contributors, might change the schema of the JSON payload when adding or removing fields. In such a scenario, the version number will be incremented.

> root → name

The name of the currency.

> root → fromSymbol

Each Blockmodo payload must have a fromSymbol and toSymbol unless otherwise specified. In this case, the fromSymbol will be the symbol of the currency being described. 

> root → fromSymbol

Like above, the toSymbol will describe the relation to some other currency. In this case, since we are describing a currency with no relation to another, the toSymbol will always be 'ALL'.

> root → website

The website for the currency.

> root → network

This block holds network related statistics. 

> root → images

A hash that holds images of the currency with different sizes. Hosting provided by Blockmodo. 

> root → network → t_total_supply

The number of coins that are currently available in some form.

NOTE: This is a temporal value and might change frequently. If you wish to update this field, please make sure to update it no more than once a day via a pull request. 

> root → network → t_available_supply

The number of coins that are available to trade. For example, if a currency has coins locked up in escrow the available supply will be a subset of the total supply. 

NOTE: This is a temporal value and might change frequently. If you wish to update this field, please make sure to update it no more than 3 times a day via a pull request. 

> root → network → t_max_supply

The max number of coins that can be mined or generated.

NOTE: This is a temporal value and might change frequently. If you wish to update this field, please make sure to update it no more than 3 times a day via a pull request. 

> root → network → t_block_reward

The number of coins that are rewarded per mined block.

NOTE: This is a temporal value and might change frequently. If you wish to update this field, please make sure to update it no more than 3 times a day via a pull request. 

> root → wallets

The list of supported wallets for the given token/coin.

> root → is_crypto

If the fromSymbol being described is a cryptocurrency. Typically this value will be 'true'.

> root → is_minable

Is the coin minable using a proof_type.

> root → proof_type

The type of work required to verify blocks of transactions. 

> root → algorithm

The algorithm used to sign blocks.

> root → description

Hash of description types. The key in this block will be the language code and the value will be a string. 

> root → quote

An array of URLs of where users can get quotes for the given fromSymbol.

> root → explorer

An array of URLs of where users can get blockchain related information.

> root → chat

An array of URLs where users can find information about chat communities. For example, Telegram or Rocket chat links would be listed here.

> root → social

An array of social media URLs. For example, Facebook pages or groups would be listed here. 

> root → social

An array of community URLs. For example, Sub-Reddit's would be listed here or forums.

> root → source_code

An array of repo URLs. For example, GitHub repos would be listed here.

## Contributions

We are always looking for help. If you have a relevant edit, please feel free to issue a pull request. Some things to keep in mind:

1. Please do not change the schema. If you wish to suggest a schema enhancement, please open an issue.

2. Temporal value changes should be done no more than three times a day. If you would like to update temporal values, please drop open an issue.

## Contributors

Icon: [cryptocurrency by mikicon](https://thenounproject.com/mikicon/uploads/?i=1601185)

## Looking for real-time streaming pricing data?

Blockmodo provides real-time streaming pricing data on over 1500+ coins straight from exchanges. In addition, the API also streams news, code checkins, and social posts. Feel free to check out [Blockmodo API docs.](https://blockmodo.com/docs/api)

## Community

Coin Registry is maintained by Blockmodo and we're on Telegram. Visit us [on Telegram](https://t.me/blockmodo_developers)
