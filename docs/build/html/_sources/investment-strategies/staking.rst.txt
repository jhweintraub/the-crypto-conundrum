Mining and Staking
======================
If you've been on Coinbase, or any major exchange, you may have noticed an option presented to holders of certain coins known as "staking". This is a core concept for for ethereum and for many large cryptocurrencies. Hopefully, in this article you can get a new understanding of what staking is, how it works, and why you should do it. 

"Staking" is the term used for people participating in a `Proof-of-Stake based Cryptocurrency <https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/>`_. This is a consensus algorithm that is used to run the network. 

However, to explain what Proof-of-Stake is and why its important, we need to understand its predecesors and underlying technology.

What is consensus
------------------
**Consensus Algorithm:** A software algorithm used in the blockchain to maintain the security and continuity of the network. Without a centralized authority to keep track of records, the task falls to each member of the network. In order for any change to the network to occur and new transactions be confirmed, each member of the network must agree on it. This is known as consensus, and the best way to achieve it is the subject of heavy research and debate. This occurs very frequently, whenever a block is added to the chain, at a pre-determined interval.

`What is Consensus? <https://academy.binance.com/en/articles/what-is-a-blockchain-consensus-algorithm>`_

Proof of Work
---------------

In Bitcoin, this algorithm is known as Proof-of-Work (link needed). This algorithm allows any person to add a block to the chain, provided they first solve a difficult mathematical puzzle. In its simplest terms, this involves using computers to guess a very large secret number, very quickly. Being the first person to guess this number successfully gets to add the block to the chain. This privilege comes with a substantial monetary reward, paid out in cryptocurrency. The people who do this are known as "miners". For people in the tech-world, this is done using the `SHA-256 Hash algorithm <https://en.wikipedia.org/wiki/SHA-2>`_.

The person who adds the block to the chain gets two things:
	#. The sum of all the transaction fees of the transactions included in the block.
	#. A special transaction, that creates coins out of thin air, and gives free coins to the block-creator. This is known as the "coinbase reward" (sound familiar?)

The problem is that these miners do not cooperate with eachother. They are competing to find the number fastest. This creates a lot of redundancy in the system as they may guess the same number, multiple times, without communication. This is alao what people talk about when they talk about energy usage. To run the Bitcoin network, thousands of people around the world are running these computations trillions of times per second on specially-made large computers. Those take a lot of energy to run 24-hours a day.

.. image:: images/pow.png

Halvings
---------

This coinbase reward is present in all currencies, regardless of its consensus algorithm. However, in coins like bitcoin, the value can change. In Bitcoin's algorithm, this number decreases over time, until eventually it reaches zero. When the value of the reward drops, this is known as a "halving", because the reward gets cut in half.

.. image:: images/halving_chart.png

Using math, this system works out to the last new bitcoin being created at a supply of 21 Million. This won't happen for a very long time. When it does though, this doesn't mean miners won't have anything to do. When the last bitcoin is mined, miners will still receive the transaction fees for each transaction they confirm. 

In coins like Ethereum, this halving doesn't occur. This is because the reward is set by the community and has no hard cap of coins. However, and I will explain this in a later article, it is expected that with current supply and changes to the network, ethereum's supply should stablize at around ``~120 Million Ether``


Proof of Stake
----------------

In Proof of Stake, this system is more streamlined. Anyone can still propose a block to the chain, provided they put up a bond, known as "stake". 

You need a stake in the outcome and skin in the game to prevent people from acting dishonestly. There are no miners, only "stakers". You first put up a bond in cryptocurrency for the right to propose blocks. If you propose a block that is rejected by the network, or act dishonestly, your bond is liquidated and you forfeit the right to it. This creates a financial incentive to be honest. 

The network then randomly selects a person from the pool of stakers to propose each block. However, unlike a Proof-of-Work system, where only the person who approves the block profits, everyone profits in a proof of stake system. 

Even if you don't propose a block, by confirming valid blocks and rejecting invalid ones proposed by others, you are rewarded with a small amount of cryptocurrency. You still must put up a "bond" to do this. This amount earned by stakers fluctuates based on the number of stakers in the network and the community-designated reward. There is no longer a coinbase-reward, for each block. However, because the people creating the block no longer need to expend large amounts of energy to do so, there is no major loss on profitability.


This system has 3 main advantages:
	#. Energy Efficiency - By eliminating the competition aspect, energy is no longer wasted trying to guess the secret number. This makes the system ``~99%`` more efficient in terms of energy consumption. 
	#. Security - The biggest risk to a blockchain is a `51% attack <https://www.investopedia.com/terms/1/51-attack.asp>`_. In proof of work, by acquiring enough computing power, this is possible and occurs on smaller networks all the time. However, in a Proof of Stake network, to succesfully pull of a 51% attack, someone would need to hold 51% of all staked coins in the network. This is because they would be able to propose 51% of blocks and have them verified successfully by 51% of nodes. However, This is incredibly incredibly expensive, and creates a financial incentive to be honest. If you owned 51% of all coins, attempting to attack its security would instantly crash the price and devalue your own holdings significantly.
	#. It rewards everyone, not just the largest actors. In Proof-of-Work, only people with the largest mining power will profit, as they can produce more blocks than the person mining on their personal PC. In Proof of Stake, anyone can profit by verifying blocks. It can be run with as little as a `Raspberry Pi <https://www.amazon.com/s?k=raspberry+pi+raspberry+pi+3+model+b&hvadid=409975553966&hvdev=c&hvlocphy=9032778&hvnetw=g&hvqmt=b&hvrand=10553800046473860534&hvtargid=kwd-300229776225&hydadcr=18067_11398848&tag=googhydr-20&ref=pd_sl_49xbvsep4m_b>`_ and a `1-2TB HD <https://www.amazon.com/s?k=2+tb+hard+drive&crid=1EHT4BEWHCTOJ&sprefix=2+tb+hd%2Caps%2C-1&ref=nb_sb_ss_ts-doa-p_1_6>`_.

Why should I stake my coins?
------------------------------

If you plan on holding your coins for a long time, thinking they'll appreciate, then staking is a no-brainer. It's basically like earning interest on them, while also helping to secure the network. By staking Ethereum, you can earn `anywhere from 4-22% APY <https://ethereumprice.org/eth-2-calculator/>`_. It also helps to secure the network you are invested in by making it harder for a hacker to attack it. The amount earned fluctuates depending based on the number of people currently staking at any given time. 

.. image:: images/staking_rewards.png

How do I stake
----------------

This has several answers, and much like everything, the solution depends on your situation. 

There are several ways to do this with their own pros-and-cons. 

Exchanges:
	This is the simplest. If you're using an exchange like Kraken or Coinbase, you simply go to their page on the website and click "stake my coins", and they go through the process for you. They will stake the coins, earn rewards, and issue them to your account. This is the best option for beginners and holders of small amounts. For example, many currencies, such as ethereum, require you stake multiples of 32-ether. This can be financially very difficult for most, and exchange staking can allow you to stake your smaller amounts and earn rewards. These exchanges do take fees though, and very from site to site. In coinbase, it is roughly ``~25%`` of the rewards. On Kraken it's ``~15%``. You should also be aware that this carries normal exchange risks such as security, and account lockouts. As usual, these risks are not very large but do exist and should factor into your decisions. If you care about decentralization, consider the other options, as too many people staking on exchanges can increase that network risk.

Pools:
	This is a more technical option, typically involving a series of smart contract applications. It involves you supplying your coins to a pool, where it is then used by others to stake on your behalf, and issue you rewards. Like exchanges, it can be advantageous to people willing to earn rewards through staking, but don't have enough to do it themselves. The program will have its own ways to ensure that the people receiving your coins are trustworthy, typically using their own system of bonds and stakes. This can be a great option for the slightly more tech-savy user, as it incurs lower fees, is more decentralized, and operates entirely on-chain. On Ethereum, the largest is `Rocketpool <https://www.rocketpool.net/>`_. It can be as simple as sending your coins to a smart contract. The protocol then issues you a token known as rETH. This is a token that represents the coins you have staked on rocketpool. It's a full token that can be exchanged for an equivalent value of regular ETH in the future, traded, used in DeFi, etc.

.. image:: images/rocketpool.png

Self-Staking:
	This is the most technically-difficult and only recommended for advanced users. It involves running a computer with the validating-node software yourself. This can be done on the cloud through services like AWS, or locally on your own machine. This gives the user the highest reward, as they don't have to pay any fees to anyone. However, there is an upfront cost that must be paid in order to run the machine. If it's on the cloud, it's an AWS bill. If it's building a machine at-home, its the cost of materials, etc. It's also important to make sure you are capable of maintaining a sufficiently fast and stable internet connection, as well as constant 24-hour power supply. Any outtages will reduce your earnings and miss blocks to validate. It's important to note that by running it yourself, you won't earn any more raw coins than anyone else, you simply get to keep more as you don't have to pay fees to anyone. If you are staking on ethereum, Keep that in mind before doing so. In terms of actually doing so, there are many `great guides <https://someresat.medium.com/guide-to-staking-on-ethereum-2-0-ubuntu-prysm-56f681646f74>`_ to staking, and is not very difficult. However, due to its complexity only power users and those with technical background are advised to do so.

Use `this site <https://www.stakingrewards.com/earn/ethereum-2-0>`_, to find out what your staking rewards could be, and the best choice for you

**If you are plannong on staking ethereum, those coins are going to be LOCKED AND ILLIQUID for at least the next 1-2 years until the upgrade to ethereum 2.0 is complete.**

