---
title: Why is Git not considered a "block chain"?
url: https://stackoverflow.com/questions/46192377/why-is-git-not-considered-a-block-chain
---
## Question
Git's internal data structure is a tree of data objects, wherein each objects only points to its predecessor. Each data block is hashed. Modifying (bit error or attack) an intermediate block will be noticed when the saved hash and the actual hash deviate.

> How is this concept different from block chain?  

Git is not listed as an example of block chains, but at least in summaries, both data structure descriptions look alike: data block, single direction reverse linking, hashes, ...).

So where is the difference, that Git isn't called a block chain?
## Answer

### First Answer
The reason why Git and blockchains appear similar is because they are both using [merkle trees](https://en.wikipedia.org/wiki/Merkle_tree) as their underlying data structure. A merkle tree is a tree where each node is labeled with the cryptographic hash value of their contents, which includes the labels of its children.

### Second Answer
To sum it up (for me):
**While Git offers you complete full freedom of choice, Blockchains are a highly political system, where you are forced to trust in others**:
- Git is a Merkle Tree without a predefined consensus algorithm.
- Blockchains are Merkle Trees with a predefined consensus algorithm.

Hence if you are all alone, there is no difference between Git and a Blockchain. As you trust Git and yourself, you already have that predefined consensus.

But things start to become different, when you are in a Network.

### Third Answer
There is no reason to not consider Git as a blockchain. Git is focused in a very particular (and important) set of assets: source code. The consensus in this case is manual, and we can consider that a transaction (commit) is accepted when it is merged into the release branch. Actually, considering the number of transactions (commits), Git is by far the most successful blockchain.