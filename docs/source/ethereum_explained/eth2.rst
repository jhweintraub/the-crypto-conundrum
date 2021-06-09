Ethereum 2.0
==============

If you follow tech news, you may have heard about something refered to as "Ethereum 2.0". There's a lot of buzz surrounding it, and for good reason. Ethereum 2.0 (or Eth2) is a series of large upgrades to the underlying protocols of the Ethereum platform. It's intended to make the network operate faster, more securely, and more efficiently. It is currently being rolled out in phases, with us in Phase 0.

The Problem & Proposed Solution
----------------------------------

In its current form, Ethereum suffers from a lot of the `same problems as bitcoin <https://thecryptoconundrum.net/introduction/bitcoin_vs_ethereum.html#scalability-issues>`_. However, this problem is endemic to `Proof of Work <https://thecryptoconundrum.net/investment-strategies/staking.html#proof-of-work>`_, and not Ethereum as a whole. Ethereum 2.0 is first step in a never-ending development process to make the network better. 

Let's look at the problems:

Innefficiency
	Unfortunately, Elon Musk was correct when he said that cryptocurrency mining is environmentally very damaging. Ethereum is the 2nd largest mined curreny currently, and its operation is incredibly wasteful. Building a cryptocurrency platform capable of powering the world's computations is going to require a radical restructuring to be more in line with traditional energy consumption. Ethereum 2.0 is expected to cut the network's power consumption by ``~99.5%``.

Scalability
		Without making sacrifices on decentralization or security, proof-of-work will never be able to handle the massive growth in transaction volume. In previous articles i've explained how block size limitations prevent transactions from occuring quickly without incurring high transaction fees. Using an architectural style known as `sharding <https://en.wikipedia.org/wiki/Shard_(database_architecture)>`_, Eth2 is expected to significantly increase its number of transactions/second without sacrificing decentralization.

Security and Centralization
		As cryptocurrencies have grown in population, so has the barrier-to-entry for mining. Today, major parts of mining profits are centralized to a few big players with warehouses of computers in remote parts of the earth. This creates a massive security risk, and prevents new players from entering the game profitably. By switching away from mining, to a different `consensus algorithm <https://thecryptoconundrum.net/investment-strategies/staking.html#what-is-consensus>`_, operating a node and validating blocks becomes more decentralized, with a much lower barrier to entry. This is best for security because it reduces the chances of 51% attacks by increasing decentralization. 

To solve all of these problems, Eth2 relies on 2 solutions: Proof of Stake and Sharding


Proof of Stake
----------------

I'm not going to explain here how proof of stake works, as I've already done so previously. I highly suggest checking it out `here <https://thecryptoconundrum.net/investment-strategies/staking.html>`_. The first part of the Eth2 upgrade is the switch from being Proof-of-Work based, to Proof-of-Stake based. This comes with all the aformentioned benefits of a more efficient consensus algorithm.

This however, is not happening all at once. It is a multi-step process that occurs over time. It starts with what is known as the *Beacon Chain*. Started in December 2020, the beacon chain is a seperate chain operating in parallel to the main Ethereum chain. It is operating with proof of stake, and is being used to build consensus. On pre-determined intervals, new *empty* blocks are being created and verified by all of the stakers.  Slowly and over time as the software is developed and tested, transactions are going to be introduced and tested on this beacon chain. At a point in ~2021/2022, the original Ethereum chain and this new Beacon Chain are going to merge. When this happens the beacon chain will be the new main chain, and all transactions will be routed through it. There will not be any more proof-of-work blocks when this occurs.

This new chain in terms of functionality, will be exactly the same as the original chain. It will be able to handle full transactions and smart contract integration. This upgrade is about changing how new blocks are created, not what they can do.

If you are regular user, you won't even realize this is happening. You will be able to keep sending transactions the same way you always have. **You do NOT have to do anything as a user to prepare for eth2**. Just continue to hold your coins. Scammers will attempt to get you to send them eth under the guide of exchanging for newer eth. Ignore these as they are scams.

Anyone can become a validator (the new term to replace miners), provided they stake their ether first. This must be done in multiples of **32 ether**. If you have ``> 32 ether``, you can only stake 32, and keep the rest to do as you please. Each multiple of 32 entitles you to run 1 validator node. If you stake ``64 ether``, then you can run 2 nodes, and receive ``~2x the reward``. 

Keep in mind, this does **NOT** mean that if someone with ``32 ether`` earns ``6% interest``, you will earn ``~12%``, only that you will earn ``6%`` of your ``64 ether``. Each node is independent of eachother and earns roughly the same amount. You just operate multiple of those nodes and collect the sum total of their rewards.

If you choose to stake, the ether to stake **WILL BE LOCKED** and unable to be withdrawn until eth2 is finished. When this is is uncertain, but will most likely be within the next ``~1.5-2 years``. 

I'm not gonna walk through the technicals of staking, but it is basically a 2 step process. I will give you a top-level explanation of how it works.
	1. You derive a new set of encryption keys. These are your validator keys, and are used to prove your identity in relation to your staked coins. They are generated with a 24-word mnemonic phrase. Even if you don't validate a single block, when the time comes you can withdraw your 32 ether exactly as long as you have these keys

	2. Send 32-ether or multiples of it to the `deposit contract <https://etherscan.io/address/0x00000000219ab540356cBB839Cbe05303d7705Fa>`_. This is a contract on the main chain that keeps track of the people who have staked their funds and how much.

	3. Run the validator software on a compatible machine. You have to connect to a full blockchain node which you can either do locally or with `infura <https://infura.io>`_. There are several different softwares built by different teams such as: `Teku <https://consensys.net/knowledge-base/ethereum-2/teku/>`_, `lighthouse <https://github.com/sigp/lighthouse>`_, `Prysm <https://prysmaticlabs.com/>`_, etc. 

	4. Rake in those sweet rewards.

One of the main benefits of Proof of Stake as well, is that it enables a sharded blockchain. 

Sharding
----------

While Proof of Stake is meant to solve a lot of problems for Ethereum, it does not help with scalability. This is where sharding comes into play.

Sharding is a common practice in database design and computer science. It involves splitting the information horizontally into "shards" to reduce congestion and distribute the computational load. Imagine a database. Instead of one server holding millions of records, it would distribute fractions of the storage requirements to 
other servers. These servers are constantly communicating to receive information when necesarry. In a blockchain context, it involves splitting the blockchain into 64 smaller chains, known as shards. Each node will only have to process and store information on their shard, instead of the entire chain. All of these shards are coordinated by the beacon chain (hence the name).

.. image:: images/sharding.jpg

*Original diagram by Hsiao-wei Wang, design by Quantstamp*

This allows greater throughput as nodes only have to validate and store transactions on their individual shard. This means that transactions can also occur much faster without sacrificing centralization or security. Distributing the storage and load therefore prevents the nodes from having to store incredibly large amounts of chain data as time goes on, preventing decentralization and making it easy for anyone to run a node regardless of hardware.

When sharding goes live, the original ethereum chain and all its data will be converted into one of the 64 shards.

However, some schematics as well also have the shards only for storing data, and not executing contracts. This is also a valid way of distributing load, because it means that the on-chain data will be able to grow faster without worrying about centralization risk. If the chain grows ``~2x`` as large everyday, but each we split the data storage responsibility upon 2 different shards, the ability for a node to process without overburdening the storage capacity roughly comes out about even.

The original version of this design included making several of these chains entirely executable, like the main ethereum chain. This would mean that say you have 5 shards operating in parallel, fully executing transactions and communicating with eachother, meaning a huge jump in speed. This is because many computationally-strenuous contracts can be processed on a shard without bogging down the others. 

Once again, as a holder of Ether, you will **NOT** have to do anything to prepare for this update. If you are running a node or a developer, consult the documentation for your node software for instruction.

The exact schematics of how these shards will operate in terms of execution vs. simple data storage is constantly evolving alongside other technologies and updates. Sharding is currently planned as "phase 2" of eth2, but it is entirely possible that with other scalability solutions, it will become unnecesarry.

The Future Post-2.0
---------------------

After Eth2 is finished deploying, the future of Ethereum is uncertain. The foundation and the community will continue to develop updates to the network over time, as new issues arise. Vitalik himself has also put together an extensive roadmap of issues and solutions that Ethereum will continue to work towards in the years to come such as: Post-Quantum Encryption Updates, More Layer-2 Support, Client updates, etc. 

Vitalik has created the following roadmap

.. image:: images/eth_roadmap.jpg

*Image Source: Vitalik Buterin Website, vitalik.ca*

**"Does Ethereum 2.0 mean the price of Ether is going to go up?"**

	I don't know. It's entirely possible. The last bull run began last year in anticipation of Eth2.0 Beacon Chain launch in December. I myself am very bullish on Ethereum for the foreseeable future, but I won't make any predictions on price just yet. However, for the long-term health, sustainability, and scalability of the network needed to flourish, this is a very exciting time for all holders and developers.

If you're still feeling a bit confused by all this, don't worry. It's a complicated subject and it took me a very long time to even understand it at a basic level. Keep working hard and feel free to check out this great video by `Finematics <https://www.youtube.com/channel/UCh1ob28ceGdqohUnR7vBACA>`_.

.. raw:: html

	<iframe width="560" height="315" src="https://www.youtube.com/embed/ctzGr58_jeI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>









