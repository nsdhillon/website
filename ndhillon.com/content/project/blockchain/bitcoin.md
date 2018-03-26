+++
# This is the frontmatter on all post when you create using:
#  hugo new project/test.md

title = "Bitcoin"
date = 2018-03-02T21:55:17-05:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["bitcoin", "blockchain", "distributed ledger"]

# Project summary to display on homepage.
summary = "Bitcoin is a cryptocurrency and worldwide payment system. It is a decentralized digital currency, as the system works without a central bank or single administrator"

# Optional image to display on homepage.
image_preview = ""

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Does the project detail page use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = ""
caption = ""

+++
## Why the success
Bitcoin allows user-to-merchant and user-to-user transactions. In fact, the protocol doesn’t have a notion of merchant that’s separate from the notion of user. The support for user-to-user transactions probably contributed to Bitcoin’s success. There was something to do with your bitcoins right from the beginning: send it to other users, while the community tried to drum up support for Bitcoin and get merchants to accept it.

The first property that we need from a cryptographic hash function is that it’s collision‐resistant. A collision occurs when two distinct inputs produce the same output.

 The second property that we want from our cryptographic hash functions is that it’s hiding. The hiding property asserts that if we’re given the output of the hash function y = H (x), there’s no feasible way to figure out what the input, x , was.

## The transactions/consensus
All the nodes in the peer‐to‐peer network have a ledger consisting of a sequence of blocks, each containing a list of transactions, that they’ve reached consensus on. Additionally, each node has a pool of outstanding transactions that it has heard about but have not yet been included on the block chain. For these transactions, consensus has not yet happened, and so by definition, each node might have a slightly different version of the outstanding transaction pool. In practice, this occurs because the peer‐to‐peer network is not perfect, so some nodes may have heard about a transaction that other nodes have not heard about.

## Problems
1. Latency
There’s a lot of latency in the system because it’s distributed all over the Internet. The network is highly imperfect as it is a peer‐to‐peer system, and not all pairs of nodes are connected to each other.

2. Consensus is hard.
Nodes might crash or be outright malicious and put invalid transactions into their blocks.

3. Lack of global time
This constrains the algorithms that can be used in the consensus protocols.

4.  Consensus - Byzantine Generals Problem
 In this classic problem, the Byzantine army is separated into divisions, each commanded by a general. The generals communicate by messenger in order to devise a joint plan of action. Some generals may be traitors and may intentionally try to subvert the process so that the loyal generals cannot arrive at a unified plan. The goal of this problem is for all of the loyal generals to arrive at the same plan without the traitorous generals being able to cause them to adopt a bad plan. It has been proven that this is impossible to achieve if one‐third or more of the generals are traitors.

5. Lack of identities for nodes
Bitcoin nodes do not have persistent, long‐term identities a difference from traditional distributed consensus algorithms. One reason for this lack of identities is that in a peer‐to‐peer system, there is no central authority to assign identities to participants and verify that they’re not creating new nodes at will. This creation of false identities is called a *Sybil attack* where that a malicious adversary can create to look like there are a lot of different participants, when in fact all those pseudo‐participants are really controlled by the same adversary. This a


## Bitcoin consensus algorithm (simple)

This algorithm is simplified in that it assumes the ability to select a random node in a manner that is not vulnerable to Sybil attacks.
1. New transactions are broadcast to all nodes
2. Each node collects new transactions into a block
3. In each round a random node gets to broadcast its block
4. Other nodes accept the block only if all transactions in it are valid (unspent, valid signatures)
5. Nodes express their acceptance of the block by including its hash in the next block they create

## Nodes get paid
### Block reward
The node that creates a block gets to include a special transaction in that block called a coin‐creation transaction. In this the recipient address of this transaction is itself which acts as a payment to the node in exchange for the service of creating a block on the consensus chain. In bitcoin the block reward is cut in half every four years limiting the total supply of bitcoins to 21 million.

### Transaction Fee
The creator of any transaction can choose to make the total value of the transaction outputs less than the total value of its inputs. Whoever creates the block that first puts that transaction into the block chain gets to collect the difference, which acts a transaction fee. So if you’re a node that’s creating a block that contains, say, 200 transactions, then the sum of all those 200 transaction fees is paid to the address that you put into that block.

## Proof of work
To stop the creation of too many nodes (Sybil problem); Bitcoin uses Proof of Work concept where they introduced a resource that nobody can monopolize. This resource was to select nodes in proportion to their computing power. It is a piece of data which is difficult (costly, time-consuming) to produce but easy for others to verify and which satisfies certain requirements. Producing a proof of work can be a random process with low probability so that a lot of trial and error is required on average before a valid proof of work is generated.

### Hashcash (used by Bitcoin) ryptographic hash function
Bitcoin mining uses the hashcash proof of work cryptographic hash function; The hashcash algorithm is SHA-256^2 (double hashed) which requires the following parameters: a service string, a nonce (an arbitrary number that can only be used once - often a random number), and a counter. In bitcoin the service string is encoded in the block header data structure, and includes a version field, the hash of the previous block, the root hash of the merkle tree of all transactions in the block, the current time, and the difficulty.




 Bitcoin also gets rid of signatures, relying only on hash pointers to ensure the integrity of the data structure
