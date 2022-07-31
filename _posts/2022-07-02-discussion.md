---
title: Discussion Questions 1
categories: Notes
author_staff_member: Sybil
date: 2022-07-02
---
Notes about the discussion session on July 2nd, 2022.

## 7/2/2022 Discussion
#### Regarding: Sybil attacks vs eclipse attacks, the costs of running a node, global remittance markets, and more
+ Satoshi solves the Byzantine Generals Problem
+ The way in which Satoshi used PoW was his real innovation
    + Helps defend from a Sybil Attack
    + Sybil Attack - Dishonest node gives you wrong information, how can you tell what’s right and what's wrong without prioritizing/a voting system
    + Proof of Work remedies this
    + You only need to be connected to one honest node to defend from this attack on the Bitcoin Network
    + Eclipse Attack - When a node is only connected to sybil nodes
    + This means that while sybil attacks aren’t a problem for Bitcoin nodes, eclipse attacks are because they break the security assumption that our node is always connected to at least one honest node
+ Are there costs or risks with running a full node?
    + There are costs, but the benefits outweigh the negatives
    + Cons: 
        + Eats through disk space and RAM
        + Initial sync requires downloading the full blockchain, which takes up loads of space
        + Eats up bandwidth, not viable with limited bandwidth
        + Could be illegal in your country
        + Hassle to maintain the node once it’s up and running
    + Pros:
        + Keeps network honest
        + Less trust in third parties
        + Makes sure your transactions are being broadcast
        + Choice autonomy, you choose what code you run
        + You don't get the true bitcoin P2P advantage without a node of your own
+ Can Bitcoin and Lightning disrupt global remittance markets?
    + Remittance - Sending money across a great distance
        + Costs a lot of money and time consuming
        + Makes up a lot of countries’ GDPs
        + Not efficient with the current system
    + Bitcoin and Lightning take a couple of minutes and a small fee
    + Almost a trillion dollars in the remittance market
    + It has already started disrupting the market
+ What is the difference between SPV Nodes and Full Nodes?
    + SPV Node doesn’t have the entire blockchain
        + Allows resource-constrained devices to smaller transactions with less disk space
        + They have to trust other nodes more than full nodes, even though they can verify that a transaction has been included in a block with a certain number of additional blocks mined on top of it
        + It’s not private
        + Have to constantly contact other nodes for info, prone to Eclipse Attacks
    + Running a full node is safer because you don’t have to trust others as much and its more private
    + Merkle root - Transaction IDs hashed together into one hash
    + Better SPV solutions are being implemented, but they still have issues
        + Neutrino is one said solution
    + Pruning - Practice in full nodes, once you verify a block you don’t have to keep it once a certain number of block havebeen mined on top of it

#### Meeting notes written by Sybil
