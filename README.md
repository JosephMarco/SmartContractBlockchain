# SmartContractBlockchain

---------WORK STILL IN PROGRESS--------


Instructional start to finish of ETH based blockchain smart contract build

###Terminology to know:
- Node: examples of independent users -- aka a signle instance in a decentrilized system (aka one server running the technology or one peer group)
- Consensus: the mechanism used to agree on the state of a blockchain. Consensus protocol can be broken down into 2 pieces. 
    - a chain selection
    - a sybil resistance - blockchain's ability to defend against users creating fake identities to prevent influence over said system. Ex preventing people from creating fake blockchains to get more and more rewards
- Proof of Work (PoW): falls under umbrella of consensus. A sybil resistance mechanism cause it defines the way to figure out who is the block author. single node has to go through computational ecpensive process called mining to find the correct nonce or whatever the blockchain has in place. Some blockchains make the "riddle" intentionally hard or easy depending on the need to change the block time. Problems can chance depending on the system needs for the block time, Verifiable way to figure out who the block author is and be sybil resistant combined with chain selection rule. Also tells us where trnx fees and reward go to (has recently changed as of EIP 1559). In a PoW network called miners, in PoS they are validators. All nodes trying to get the answer first, if successful they will get the TRX fee and the block reward from the protocol or block reward.
- 
- Chain Selection rule: how do we know which blockchain is the real blockchain
- Bitcoin and ETH use Nakamoto Consensus is a combo of PoW and longest chain rule. Decent network decides whichever network has longest chain or longest blocks on it is the one it will use. 
- Block confirmations: number of additional blocks added on after our transaction went through in a block. Ex if we see confirmations 2, then the block our transaction was in has 2 blocks ahead of it in the longest chain
- 
- Proof of State (PoS): falls under umbrella of consensus. HAs pros and cons. Pros are that is a great sybil resistance mechanism, and great way to figure out who author of block should be. Another major pro is that it is WAY less computationally expensive to figure out the new block, since all nodes on network DO not need to do it, only one node needs to do it and rest of the nodes are just validators. CONs include being slightly less decentrilized network due to the upfront staking costs it costs to participate. General consensus still is that this is still very decentrilized and very secure. POS reduces environmental impact by 99% in the example of ETH2.
- 
- Bitcoin halving - referring to block reward being cut in half, reward cut in half every 4 years. Ex block rewards give out rewards on their specific protocol.
- Gas fees paid by whoever runs the transaction
- Sybil attack: when user creates a bunch of fake accounts to try to influence a network. On BTC and ETH really difficult. single node or entity looking to pretend to be multiple different people
- 51% attack: become harder when the size of the blockchain is larger, refers to 51% of the blockchain miners or validators working in a dishonest way and influencing the protocol. More nodes in a blockchain - harder to attack
- Validators: in POS nodes are randomly chosen to propose the new block in which validators verify the proposal or transaction is honest
- Randow: being used in ETH2 implementation ewhich is a decentrilizaed autonomous org that collectively chooses the randomness then chooses which node is going to run next (this might change in the future)
- Sharding: solution to the scaleability problem. Being implemented in ETH2, a sharded blockchain just means a "blockchain of blockchains". Main chain that coordinates everything amongst serveral chains that hook to the main chain. Sharding can greatly increase the number of transactions on a blockchain layer 1
- Layer 1: Base layer blockchain implementation (examples include bitcoin, etherium, avalanche, etc.) the base layer blockchain solutions
- Layer 2: anything application added on top of a layer 1 blockchain, a good example is chainlink, arbitram, optomizm. Arbitram and optomism are known as rollups because they rollup their transactions into a layer 1. 
- Rollup is kind of like a sharded chain. They derive security from layer 1 and send their transactions to the layer 1. This is different from side chains. Rollups derive their security from their base layer 1 blockchains.

- ETH and BTC are POW blockchains that follow nakimoto consensus
- ETH 2.0 will be POS sharded blockchain
- Sybil sttacks prevented by POW and POS
- Sharding and rollups are solutions to scaleability solutions on layer 1s (not enough blockspace for the amount of transactions that want to get in them, resulting in high gas prices)
- Gas prices: how much it costs to interact with the blockchain
- 



1 - download ETH wallet, I used metamask.io follow steps to store secure keys offline

<b>NAvigate to https://faucet.rinkeby.io/ for requesting of rinkeby eth sent to private address for test funds</b>

Hash: unique fixed length string, meant to identify a piece of data. They are created by placing said data into a "hash function"
Example data input into SHA256 Hash will alter hash algorithm to unique fixed length string thats going to represent the data within the hash. Same length of hash size, for most purposes any amount of data will be contained withiin the same length uniqued fixed length string in the hash

<b>Defining what a "Block" is on blockchain"</b>
Building off of above exercise we move into Hashing:
-Block
-Nonce:
-Data:
To generate a unique hash from the hashing algorithm. This is where backend mining comes into play where miners must solve problems or challenges and thus be rewarded for "mining"
The ETH protocol problem to solve is there will be the bunch of data, the block number and the Nonce (NONCE = miner solution used to complete the solution to the problem
Example miners looking for a NONCE that solves the hash problem or defined hash based off what was given.

Moving on to defining a BLOCK-CHAIN
- in an exampled visual representation of a blockchain - this hashed protocol showcases us a "previous" parameter within the block
- previous section points to the hash of the last block that preceeded the current block
- These "blockchains" will link prev hash all the way back to the first block in the blockchain also known as the <b>Genesis BLOCK</b>

A good showcase for how blockchains are immutable, is due to the fact that given blocks in a blockchain, once chained together, cannot be changed. When changes, it causes the NONCE in connected "blocks" to become invalidated. In simpler terms, any time you change one thing in the blockchain, you RUIN the entire chain itself.

However if you do decide to change something on the blockchain in the past, you can re mine the entire blocks within the blockchain but may become computationally expensive.

Peer to peer transactions refere to different Peers running blockchains aka "nodes" each of them has exact same power as anyone else. HAsh in the last block is going to encompass all the blocks before. all peers, independent nodes etc all Match up accordingly when final blockchain hash matches up with other nodes.
-when someone ex one peer adds something like some new data, the other peers or nodes example would not matchup to this altered blockchain peer.
Ex - if peer a adds data or changes something, they may now spend the computational power to correct their blockchain and get the hashing blocks completed. But now when comparing Peer A to B/C who didnt change anything. B and C would win out to cause A to be forked out
