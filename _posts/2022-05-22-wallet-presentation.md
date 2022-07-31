---
title: Wallets
categories: Notes
author_staff_member: Sybil
date: 2022-05-22
---
Notes on a presentation about Bitcoin Wallets, given on the meeting of May 22nd, 2022.

## Wallet Presentation
+ A Bitcoin Wallet Should: 
    + Store your private keys (which help make valid transactions)
    + Generate addresses
    + Keep track of your bitcoin
    + Construct and broadcast  transactions
+ Private Keys
    + Make private keys from seed with cryptography
    + Using this you can make a bitcoin address
    + The address type specifies how your bitcoin is locked and spending conditions
+ You get a recovery/seed phrase, which is around 12+ 24 random words
+ Master private key helps derive multiple private keys using cryptography magic
+ Private Key+ Very Big Number You Should Keep Secret
+ What is a private key? What is an address?
    + Private key allows you to derive addresses
    + Bitcoin address allows you to lock bitcoin in a certain way so that only someone with your private key can spend it
+ There are different types of addresses with different specifications
+ What is an unspent transaction output (UTXO)?
    + A piece of bitcoin, kinda like a coin, but its value is customizable
    + You can’t spend only part of a UTXO
    + You can break a UTXO is by making a transaction sending a part to someone and a part to yourself
    + Part sent to yourself is its own UTXO
+ The Wallet Keeping Track of Your Bitcoin
    + Different ways to interact and get info from the network:
        + Run full node
        + Run an SPV node (not a full node)
        + Use a trusted 3rd party
+ Fees are the remainder of a transaction
+ Wallet talks to a node or something else to confirm transaction
+ Construct + Broadcast Transactions
    + Who needs to be able to spend?
    + What UTXOs work best for this transaction (coin selection)?
    + Will I have any bitcoin leftover?
+ Wallet Needs To:
    + Make sure they have enough bitcoin
    + Decide which UTXO to spend
    + Construct Transactions, which creates signatures, spending conditions, specifications, provides change output that spend bitcoin back to sender, and confirms UTXOs to use
+ Wallet broadcasts the transaction somehow
+ Makes sure no UTXOs are double spent

### Questions: 
+ Can you go more into how addresses are created?
    + You can get public key by multiplying private key with generator point, can’t go from public key to private key
    + Hash Function+ Something that outputs a consistent length of characters unique to a certain value
    + PKH+ Public Key Hash
    + Address is base58_encode(PKH)
    + You can go from address to a PKH
    + Base58_encode is not the only way to get an address
    + Bech32_encode(PKH) is another method of generating an address

### Additional Resources:
+ Thread about the presentation w/ resources: [link](https://twitter.com/IshaanaMisra/status/1537539567959556097)
+ Recommended reading for learning more about elliptic curves, keys, and addresses: [link](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch04.asciidoc)

#### Meeting notes written by Sybil
