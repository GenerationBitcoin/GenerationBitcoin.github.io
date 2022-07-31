---
title: Coin Selection
categories: Notes
author_staff_member: Ishaana
date: 2022-07-16
---
For this presentation we had [Murch](https://twitter.com/murchandamus), a Bitcoin Core developer at Chaincode Labs, as a guest speaker and he talked about different coin selection algorithms and their effects on a user's utxo pool

## Coin Selection Presentation

#### Slides can be found [here](https://docs.google.com/presentation/d/1TylejLl_8H_uR53T4cH62UrnPYs8tJs1RYFuFmVL8xA/edit#slide=id.p)

+ The UTXO model
    + UTXOs in Bitcoin are like coins and bills
    + every piece of bitcoin is distinct and we track them separately
    + this can be contrasted with the account-based model in most banks
    + ethereum also works with an account-based model
    + when you make a transaction with bitcoin, you always have to tell people which pieces of bitcoin you are spending
    + you can't tear a corner off of a ten dollar bill
        + you take the 10 "dollar" bitcoin, and they keep the 7 bitcoin and return the 3 bitcoin
    + "change" to return the bitcoin
    + the sender encodes the transaction in a way that they get their bitcoin back in the form of change
    + advantages:
        + simpler to reason about
        + each coin is unique
        + either a piece of bitcoin is spent, or it is not
        + promotes private behavior
            + you don't have to resuse addresses
            + w/ an account model you are incentivised to use the same addresses

+ Transactions
    + we already know which recipient address to create: we have been given and address and know how to construct output
    + what we don't know, is what pieces of Bitcoin we want to spend: this is called coin selection
    + primary goal:  pick enough money to pay the recipient the desired amount
    + secondary goals:
        + minimize the current fees
        + minimize the fees over the lifetime of the wallet
        + financial privacy: we don't want to tell the recipient how much bitcoin we hold
        + flexibility: ex. we don't want all of our funds to be unconfirmed at the same time
    + unknown variables that are hard to predict:
        + exchange rates
        + feerates
        + payments

+ Approaches and Concepts:
    + feerate sensitivity
    + payment batching: paying a bunch of people at the same time
    + address resuse: don't do it
    + consolidation: consolidating small pieces of bitcoin when the feerate is lower than ususal
    + change avoidance
    + output type segregation: if you use multiple output types in a single transaction, then you reveal more information about the wallet then you had to

* you don't pay fees based off of the monetary value, but instead the size of the transaction

+ Methods of picking inputs (coin selection):
    + largest first:
        + you create a lot of change
        + you end up with smaller outputs: you always pick the biggest one, and chop off some of it, so we get left with a smaller piece
    + oldest first:
        + we have less outputs
        + we spend more pieces of bitcoin
        + our utxos have a more diverse range of amounts
    + branch and bound (srd fallback): try for no change
        + we have more scenarios where we don't create change, but the creation of a change-less solution isn't always possible
        + if we can't find a change-less solution, then we use srd instead
        + single random draw(srd):
            + pick utxos randomly until we have enough to pay the recipient

##### Meeting notes written by Ishaana
###### Note: Any errors in these notes are probably due to me misunderstanding the speaker.