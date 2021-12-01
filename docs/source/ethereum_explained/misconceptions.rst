Misinformation and Misconceptions
====================================

As Ethereum has grown in popularity, so has the amount of misinformation and misconceptions about it online. If you've spent any time on the crypto parts of social media, you might have been inundated with nonsensical information attempting to undermine confidence in Ethereum or cryptocurrency as a whole. That's why I decided it was important to write this article, to correct the record on things, make clearer how various aspects of it work, and help move the community forward.


Let's start with the most common complaint,

*"The transaction fees are too high"*
----------------------------------------

You're right. It is too expensive to do almost anything right now. I won't pretend it isn't

.. image:: images/eth_fud_images/Gasfeeshistory.png

But instead of blindly shouting about the fees are too high, let's look a little deeper as to why that is the case.

First, demand. Fees are high because block space is an asset subject to supply and demand. There is a limited supply and a very high demand. There's other chains with lower fees, because they're not being used nearly as much. Look at the total number of active wallets, daily transactions, number of applications, etc. on other chains compared to Ethereum.


Fees are high because people are continuing to pay them. Chains like Solana claim ability to handle hundreds to thousands of transactions per second (TPS), but that's not enough to scale entirely. It's not unreasonable to think that when they get bigger, they will encounter many of the same problems as Ethereum does right now. It is estimated that Visa can handle ``17k TPS``, any chain that wants to win the crypto race will need to exceed that. Bitcoin, Cardano and Tezos are `experiencing this right now <https://medium.com/tezos/marigold-layer-2-scaling-for-tezos-7445b5a3b7be>`_, and turning to layer-2 solutions as the future of their chains as well. There's a *LOT* of chains claiming to "be able to scale up to thousands of transactions per second". Whether or not they will actually get there is up for debate. A lot of systems people design to be fast don't hold up in the long term. Avalance, Solana, Cardano, Algorand, etc. all claim a huge amount of scalability, but they're working right now with nowhere near the same level of demand for block-space. Only time will tell whether they are right. But, by the time they figure that out, Ethereum will have figured out how to scale themselves.

.. image:: images/eth_fud_images/econ_curve.png

Second, Ethereum is above all else committed to decentralization as its main priority. The community, of users, miners, and developers all share this as being a higher priority than scalability as this very moment. This means that the architecture of the blockchain is built in such a way that decentralization comes first. It's entirely possible to re-architecture the blockchain so that it is faster and cheaper, but that involves tradeoffs. This is why you cannot just *increase block size*, because doing so would make it much more difficult for people to run a node, and increase **centralization**.

Recall the "scalability trilemma", coined by Vitalik Buterin. On the vertices there is scalability, decentralization, and security. You can pick two. We could build a chain with Scalability and decentralization, but that also opens it up to a variety of cyber-attacks that imperils your money, like `51% attacks <https://www.sofi.com/learn/content/51-attack/>`_ and `chain re-organization <https://en.bitcoin.it/wiki/Chain_Reorganization>`_. You could abandon decentralization, but then there would be no reason for a blockchain. Without decentralization it's no different than a bank of a `central-bank-digital-coin <https://www.cnet.com/personal-finance/crypto/central-bank-digital-currencies-everything-you-need-to-know/>`_. This leaves scalability as the only option worth temporarily ignoring.

*"But I don't care about decentralization, I just wanna use what's cheapest, easiest, and fastest"*

That might be the case, and a position that many people hold. However, I would argue that that is inherently a bad way of thinking about things, and ignores the benefits of decentralization
There are four main reason to care:

  **1. Security** - When information and responsibility not constrained to a single location is more secure. Imagine your bank, they have a server that they use to track customer information. it is a single point of failure. A good hacker could take it all down. It's a risk. Even minor bugs have the potential to spiral out of control.

  **2. Censorship** - When no single actor has the power to decide what is allowed, you cannot be censored. Your access cannot be arbitrarily cut off. Services and funds cannot be revoked, like with a centralized service. You cannot be banned. This is not a political statement, but rather an abject fact. In a decentralized blockchain, if even a single node operator chooses to pick up your transactions, you can't be cut off. And even in the wildly improbable world every node tries to cut you off, you can just run your own and submit your own transactions anyways. This obviously has big implications especially in countries with repressive political regimes. But, it has other moral implications as well. You are in control of your money and can't be separated from it. You are in control of cash, and this is the same. It is yours to do with it what you want.

  **3. Reliability** - As long as one copy of the blockchain is on someone's hard drive, the entire history and ecosystem can be rebuilt. As long as 1 node remains operational blocks can still be created and transactions processed. The blockchain never stops moving forward. Being run by entities all over the world, it will survive through political instability, electrical issues, cyberattacks, etc.

  **4. Reclaim your data -** Our current system is one where the few large tech companies responsible for hosting own all your data. Decentralization is about taking back control of your data, and the power over the internet. Taking away power over what data is collected, and what gets to be shown online was the original intent of the internet. `This article <https://onezero.medium.com/why-decentralization-matters-5e3f79f7638e>`_ does a good job explaining it as well.

That is not an exhaustive list but you get the point

*"OK fine, decentralization matters, but aren't other chains decentralized too?"*

You should think of decentralization on a sliding scale. It's not "decentralized or not", but rather that decentralization can exist on one of many different levels. On the one side you have virtually none, this is a central-bank-digital-currency, a cryptocurrency issued by a government or central bank. On the other hand you have complete equality. Every node is equal, with anyone able to run a node on as little hardware as a cell-phone. Different currencies are at different places on the scale.

.. image:: images/eth_fud_images/scale.png

*\*chart not to scale*

Ethereum is on the more decentralized end of that scale, whereas other higher-throughput chains like binance-smart-chain or Solana are more centralized. The way this is determined is complicated and depends on a bunch of factors, which I will explain lower down in the article. For now it's important to know that the crypto community cares about decentralization, with Ethereum caring more than most. When you make it easier for anyone to be part of block-creation, you are constrained by a bottleneck. The speed of your blockchain is equal to the speed of the slowest-node. So even if you have 100 Nodes capable of processing 1000 transactions-per-second (TPS), if the slowest one is only able to process 100, and every node needs to agree on each block, then you're stuck at 100 TPS.

This has led to two different strategies, adopted by a variety of chains.
  **1. Privileged Nodes** - The Binance-Smart-Chain (BSC), Crypto.com-Chain, Polygon, VeChain, etc. adopted this strategy. It means that they rely on a smaller number of high-capability nodes, selected through some arbitrary system. In the BSC, it is restricted to only 21 entities, determined by whomever has the most coins at any given time. However, because it relies on holding a lot of money, only corporations are able to support this. As a result, these nodes are operated by a `few companies <https://bscscan.com/validatorset/snapshot/13089718>`_. These entities are bonded, creating some incentive to be honest, but still not a great system. What happens if the companies decide it's more profitable to collude together than to be honest? They could sow chaos, and with such a low number of validators, it's not out of the realm of possibility. At any time Binance, which controls the chain, could make decisions to let people in or out, and that kind of unaccountable control, at least in my mind, is unacceptable. Other systems use something called *"delegated-proof-of-stake"* where the community votes for whom they want to have this power to create new blocks. This sounds good, but still falls prey to centralization, and bad-actors.

  **2. Higher startup cost** - This is what Solana does. Unlike the BSC, anybody can theoretically become a validator to help create blocks. However, it does enforce a minimum spec for what level of computation your machine can handle. It requires that you have a computer capable of running a very high amount of computation with often quite difficult to acquire specs. This creates a high startup cost to run a node, such that many people are effectively priced out of the market either by network bandwidth limitations, or hardware limitations. This is runs contrast to what Ethereum envisions. In a perfectly decentralized world, anyone on any level of limited hardware can run a node and validate blocks successfully. This makes it more secure, because the more validators there are, the harder it is to launch attacks on the chain.

There's also a variety of other aspects of decentralization, like client diversity. This means that there's several different pieces of software that can be run to validate/approve new blocks. This is the system Ethereum uses. The Ethereum community builds a `variety of different clients <https://ethereum.org/en/developers/docs/nodes-and-clients/#clients>`_ in different languages. When you want to run a node simply pick your language of choice or the one best suited to your system requirements. This is a superior system because it means that all bugs and security issues are localized. If all your eggs are in one-basket, then even a seemingly minor security vulnerability could potentially take down a large section of the network. This happened to Solana `earlier this year <https://solana.com/news/9-14-network-outage-initial-overview>`_. The Solana foundation makes the singular Solana client software, that everyone uses, so a bug was able to have a ripple effect throughout the network, which disabled the entire blockchain for several hours. Ethereum, on the other hand, had the opposite effect. When a `bug in the Prysm client-software <https://medium.com/prysmatic-labs/eth2-mainnet-incident-retrospective-f0338814340c>`_, was discovered, the network kept on working because it's effects were localized to a smaller number of clients, and no downtime user-downtime occurred.

This also doesn't even account for the fact that Ethereum is still the `first choice of developers <https://consensys.net/blog/developers/ethereum-has-4x-more-developers-than-any-other-crypto-ecosystem/>`_. By miles, Ethereum has the most development tools, coding-tutorials, application-standards, and much more. Solana and Cardano might be growing, but they lack many staples of a fully-featured smart-contract-platform. Part of the reason Ethereum is still growing, despite high fees, is that it's incredibly easy. There are `hundreds of easily-available tools <https://github.com/ConsenSys/ethereum-developer-tools-list>`_, `well defined code-standards for everything from tokens to governance <https://openzeppelin.com/starter-kits/>`_, and `tons of tutorials <https://ethereum.org/en/developers/tutorials/>`_. Solidity is an easy language to learn, sharing a lot of similarities with Java and Javascript. Solana's contracts however, are written in Rust, and Cardano's in Haskell. Both of those are **not beginner-friendly**, and do not have nearly as many developer options or tools available.

In terms of applications, it's not even a competition. Solana currently has `just 7 DeFi applications, compared to Ethereum's 213 <https://defiprime.com/solana>`_.

.. image:: images/eth_fud_images/defi_apps.png

Over time the number Solana has will go up sure, but how long does this take? It will take years for other ecosystems to approach anywhere near Ethereum, and by the time they do, Ethereum will have long solved scalability, and moved onto other big improvements.

The first mover advantage is big, and is what allowed Ethereum to get where it is. But it's the continued innovation and support that will propell it into the future. Bitcoin squandered it's first-mover-advantage, but not Ethereum.

Layer-2
**********

You've probably heard about this. Layer-2 is simply the name for the off-chain scaling solution for Ethereum. I've written a lot about it `here <https://thecryptoconundrum.net/ethereum_explained/layer2.html>`_. Instead, i'm going to focus on what it means for Ethereum vs. the rest of the crypto community.

First things first. The question of chains isn't "Ethereum vs. everyone-else". It's "Ethereum + rollups vs. everyone else". Rollups cannot be separated from Ethereum. They are not going away, and the community has acknowledged that this is where the future lies. Within a few years, everyone will be transacting 100% of the time on rollups. There will be no layer-1 transactions. This will definitively bring fees down to incredibly low points, when you factor in sharding. Any discussion of "Ethereum Killers" needs to reckon with this fact.

It's not useful to say "Solana will win long term because it is faster than Ethereum". You are correct, **for now**. You need to recognize that Solana wins in the current world, short-term, where Layer-1 fees on Ethereum are high, but not on Layer-2 long-term. This applies to every other coin you think challenges Ethereum. In a future where Layer-2 becomes the norm, what is the reason to use any Ethereum-clone? Take Polygon and BSC. They are EVM-compatible, which means that any code deployed on Ethereum can be deployed on them as well with little to no code changes. In a world of low layer-2 fees on Ethereum, what is the reason to deploy anywhere else? Especially given that Ethereum has the largest user-base and the most liquidity. Same with decentralization. If you're a user, and you're picking which blockchain to use, and the fees between BSC and Ethereum or Solana are all so low that it's negligible, Ethereum still wins because it's got the added benefit of being decentralized and more secure. The only way in which these chains win long-term, is that they need to overtake Ethereum in the short-term, before Layer-2 can solve scalability, and surpass it by so much that Ethereum becomes nothing compared to it's scale in comparison. Given how far ahead Ethereum currently is, and is still the choice of developers and investors, this is incredibly unlikely.

You don't need to wait. You can use Layer-2 right now (November 2021) and do almost exactly the same thing as on mainnet for much cheaper. On Hermez and ZKSync you can send Ether and tokens for Pennies, you can use DeFi on Arbitrum and Optimism for a few dollars, and token swaps for just $1, and those amounts will continue to go down as the technology matures.

.. image:: images/eth_fud_images/l2_fees.png

*Hold on $4.24 is still way too high to use, especially when Solana is fractions of a cent.*

Yes $4 is a lot, and it should be lower. But it will go lower over time.
  **1. This tech is new -** Optimistism and Arbitrum *didn't even exist* 1-year ago. The speed is temporarily throttled by developers to ensure it has time to be adequately tested and optimized, so that when it does launch, it's got no problems. When the throttle is removed, it will cost only a few pennies. To expect a fully-working and game-changing product out of the box on Version-1 is too much.

  **2. Fees are high because there's still a lot of activity on layer-1** Rollups currently compete for block space with layer-1 transactions. If everyone were to move today to Layer-2, then Ethereum would be able to achieve roughly *~3,000 TPS*, making it the fastest chain out there. As centralized-exchanges start to integrate layer-2 withdrawals, and people migrate liquidity, fees will come down further.

  **3. Data Sharding is still a work in progress -** When data sharding becomes fully-formed in the next 2-3 years, rollups will be supercharged to a level that can handle practically infinite scalability. It is estimated that rollups + data shards can handle **AT LEAST** *100,000 TPS*, and some even speculating as many as `14 Million TPS <https://polynya.medium.com/conjecture-how-far-can-rollups-data-shards-scale-in-2030-14-million-tps-933b87ca622e>`_.


This also doesn't take into account other factors like development and usability, which I will discuss more on later. If you're interested in learning more about rollups, I highly suggest either `this article I already put out <https://thecryptoconundrum.net/ethereum_explained/layer2.html>`_, or for a more technical breakdown `this article by Vitalik Buterin on the subject <https://vitalik.ca/general/2021/01/05/rollup.html>`_.




Ethereum is Centralized
--------------------------

I talked about this before, explaining why Ethereum is the most decentralized from an architecture standpoint, but now I think it's worth addressing some common criticisms and explaining the shortfalls in their arguments.


Proof of Stake vs. Proof of work
**********************************

Bitcoin uses Proof of Work (PoW). For the sake of this article, I'm going to say Ethereum uses Proof-of-Stake (PoS), because it will be switching over in <6 Months. By the time you read this, it might already have switched.

Bitcoin maximalists are slightly correct. Proof of Work has slightly more decentralization than Proof-of-Stake. This is because in theory, anyone can start mining, even on their cell phone. It won't be effective, because of the scale of mining in 2021, but it is feasible. On the other side, Proof-of-Stake requires you first put up a bond to validate and approve new blocks. Right now that amount is ``32 Ether (128k)``. $128,000 is a lot of money. I won't pretend it isn't, and it's very difficult for people to get that. A lot of the people who have that amount, got it by buying Ether a long time ago, or are corporations.

But to say that that is the whole story misses a lot:

  **1. Node Count -** It is estimated that Ethereum currently has `more active nodes than Bitcoin <https://cointelegraph.com/news/ethereum-flips-bitcoin-s-node-count#:~:text=According%20to%20Ethernodes.org%2C%2011%2C259,spiking%20from%208%2C086%20on%20Nov>`_.

  **2. Rocketpool and Exchanges-** `Rocketpool <https://rocketpool.net/>`_ is a protocol released for Ethereum that allows people to contribute their Ether to a pool, giving you the ability to stake your $10 of Eth and contribute to security. This gives a lot of people access to staking, and makes it easier for honest-people to join the process, counteracting the malicious actors. While not always the best option, exchanges have staking programs too, that introduce more honest nodes into the system and make it more secure.

  **3. Security -** In a PoW system, you would need to acquire 51% of all hashing-power (mining-power) to be successful. The marginal cost of each extra percent is the same. To go from 40->41% of hash power means buying one more GPU, the same as going from 41->42%. In a Proof of Stake system, the only way to launch a 51% attack is to acquire 51% of **all staked Ether**. The only realistic way to do this, would be to buy incredibly large numbers of Ether on the open-market, to acquire enough. As you buy more and more, the price of Ether would rise due to scarcity, which causes the margin cost of each additional ether to go up, until it eventually reaches an unattainable point. There's also the possibility that various exchanges could band together to prevent selling you the Ether you need. Similarly, if you manage to obtain thousands of Ether somehow, launching a 51% attack risks completely crashing the price of Ether, or getting you slashed and losing it all. With a massive financial stake, honesty is the more economical policy. At this very moment, there is roughly about ``$40B`` worth of Ether being staked. In order to pull off a 51% attack, you would need to acquire roughly **$41 Billion** in Ether. If you have *$41 Billion* to throw around trying to attack this, congrats to you. But in practice it's pretty nonsensical.

*"It's centralized and gives power to the elites, because 1 stake means 1 vote, the rich people with the most Ether can exert their will over the network against everyone else"*

You're correct, but that also misses nuance. There's a massive financial risk associated with acting poorly in the network, that comes from being slashed or devaluing the price. If you have 64-Ether, you can run 2-nodes, and have 2 votes, instead of 1. You get twice as many rewards, but that's how incentives work. This is why rocket-pool and other decentralized staking-protocols are so important, because it dilutes the power of the richest-people.

I would also direct you to the question of "who owns the most Ether?". The wealthiest single-address on Ethereum currently holds `only ~1.5% of Ethereum <https://etherscan.io/accounts>`_. That amount is not staked, and has not been interacted with. Even the Ethereum foundation and Vitalik have <1% of all Ethereum. To say that those people have in inordinate amount of power in this network, is simply false. In reality, the narrative of a wealthy elite is unsubstantiated fear-mongering.

All Core Devs
***************

*The All-Core devs are an unelected group of people who can add whatever features they want without consequences*

This is an idiotic argument. The All-core devs do not have any power over the network. They are simply a group of developers building software for nodes. They are well-known people in the Ethereum community who can be trusted and make decisions over the software they maintain. Let's take `EIP-1559 for example <https://thecryptoconundrum.net/ethereum_explained/eip_1559.html>`_. It was controversial over its changes to how miners get paid and the transaction fee-structure. After years of debate, the all-core devs decided to incorporate the feature into their software clients. If you didn't like EIP-1559, then you don't have to be a part of it. By simply not not updating your client, you won't acknowledge the update, and continue mining, but on your own chain. Being a hard-fork, where the chain splits in-two, you can choose to continue mining on the non-EIP-1559 chain. If enough people choose to do that, then the chain keeps going. The reason that didn't happen is because not enough people supported the idea of rebelling against 1559 like that. Ethereum is made up of people. If enough people agree to do something then it occurs. You might be outnumbered by the rest of the community, but you are able to make whatever decision you want on which version of the chain you want to be a part of.

We saw this exact situation happen with the `DAO-Hack <https://www.gemini.com/cryptopedia/the-dao-hack-makerdao>`_. In 2016 a massive hack occurred, that resulted in a `community vote on whether or not to reverse the transaction <https://futurism.com/the-dao-heist-undone-97-of-eth-holders-vote-for-the-hard-fork>`_, and split the chain. A large group of miners said that they didn't support the reversal, and as a result a chain known as *Ether-Classic* resulted, while the main chain had the hack reversed. Anyone who didn't agree with the decision could mine on Ether-Classic, while everyone who did stayed on the main-chain. It was up to the individual to decide what they wanted to do.


Vitalik and the Foundation
*****************************

*"Vitalik and the foundartion have too much power over the development of Ethereum"*


This might be the most ridiculous claim of all. Vitalik is not some snake-oil salesman who is out to con us all. He is simply a researcher, guiding the foundation and the community towards the development of the things that he and the foundation think needs to occur. He does not have any unilateral power to change anything. Vitalik researches improvements to Ethereum, and makes improvement proposals to make it better. His goal is simply to make Ethereum better. Go read what he's written, and watch his interviews and you'll see that he's a man worth trusting.

.. raw:: html

  <iframe width="560" height="315" src="https://www.youtube.com/embed/XW0QZmtbjvs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


The foundation as well doesn't do anything more than anyone else. The **non-profit Ethereum Foundation** has 3 functions:
  1. Maintain the `Go Ethereum Client (Geth) <https://github.com/ethereum/go-ethereum>`_. But it is open source and allows anyone to participate
  2. Coordinate development between community members and all-core devs to decide on new features
  3. Write specifications to ensure uniforming between clients and capabilities.

It is not some kind of cabal doing shadowy stuff with Ethereum. All their documents and `video calls are public and anyone can see and audit what they do <https://github.com/ethereum/pm>`_


EIP-1559
---------

*"EIP-1559 didn't lower gas fees, it's more expensive than ever to do anything"*

EIP-1559 was not supposed to lower gas fees. It was a change to how your transaction fees are paid. The goal was to make them more predictable, so that you do actually save money. In a world before 1559, your wallet (like Metamask) had to effectually "guess" how much gas to pay to be included in a coming-block. Very often, this resulted in users losing money. This would happen when your wallet guesses too much, and you pay more than you needed to, or you would not pay enough and your transaction would get stuck in the mempool, or outright fail, in which case your transaction does not get executed and your funds are wasted. In a post-1559 world, your wallet is much more accurate, so you can be confident that the price you are quoted, is the price you pay. You won't pay more than you need to, and be confident your transaction will go through.

Coinbase in particular even rose to its defense, `explaining that it has saved them millions of dollars in transaction fees <https://blog.coinbase.com/the-technical-benefits-of-eip-1559-c41bb85f5924>`_. There's also a large number of other benefits to EIP-1559.

I'm not going to go into all of them in detail but some of them include:
  **1. Next block inclusion and finality** - Ensuring that your transaction will go through immediately and more efficiently which is essential for rollups to function efficiently.

  **2. Deflation** - EIP-1559 reduces the supply of Ethereum over time by burning a large amount and reducing circulation. As an Ethereum holder, this makes your existing Ether more valuable and will cause the price to rise.

  **3. More efficient gas** - Making your transaction fees more efficient and accurate to prevent overpayment

  **4. Miner Extractable Value (MEV)** - Using 1559's new gas fee mechanism, that requires burning a portion of all transaction fees, it makes it significantly more expensive and difficult for miners to `manipulate transaction ordering at your expense <https://ethereum.org/en/developers/docs/mev/>`_. This is also a benefit of the switch to Proof-of-Stake.

Ethereum was Pre-Mined
-------------------------

Premining is the process of creating a supply of cryptocurrency and distributing it before mining even occurs. It is typically done by the developers as a way to raise money to fund the project. Prior to the first block people are already given a certain amount of coins. This is not an uncommon process. In order for a cryptocurrency to function, there needs to be a large enough supply to allow people to transact. If you don't pre-mine to some extent then you are forced to wait for each block as enough people acquire currency through mining and then transacting to create a decent ecosystem. Just because some people are given the coin, **does not mean it's bad**. The question is not "did the developers sell off coins before launch", but "who were they sold too, and how many".

The common conspiracy is that Ethereum was pre-mined, and an obscene amount was sold off to a very small amount of people who now control up to 70% of the network secretly. While there are elements of truth to that, it's incredibly exaggerated and not nearly as bad as the bitcoin maximalists claim it is.

In 2015 Ethereum had an ICO. You sent them Bitcoin, and in return you get Ether. Roughly ``~60M Ether`` was pre-mined during this process. The Ethereum Foundation and developers kept about ``~12M`` for themselves, with the intention of going into a public trust to fund the foundation and the development of various needed applications by the community. As of today the foundation only holds about ``~300k Ether``, <1% of supply.

The evidence suggests as well that Ethereum might even be `more fairly distributed than Bitcoin <https://medium.com/@adamscochran/the-10k-audit-42c100dd32bb>`_

.. image:: images/eth_fud_images/distribution.png

There was no secret venture-capital fund that managed to get the inside track. It was posted on a website, and anyone was able to get in. Obviously some people were able to buy more than others because they had more Bitcoin, but to say that that is an "eth-killer" level problem is absurd. Of that 72M, with new Ether created from Mining, the total supply has jumped to about ``~120M``, with the premine only comprising about *60%* of the supply now. That number will also continue to fall over time as supply continues to rise and be burnt due to EIP-1559. Before you complain about a pre-mine, its also important to ask, where are those tokens now? If you look at current distribution breakdowns, only about 50% of currently circulating Ethereum was from that pre-sale.

.. image:: images/eth_fud_images/eth_supply.png

There are other good arguments about pre-mine, such as it allows anyone to get in on the process of being an early supporter, instead of requiring people with large computing power or electricity to hold a monopoly on the process early. This leads to early miners having significantly more power. For example, Satoshi, as the first miner, was predicted to have as many as ``1M BTC``, or ``4.7% of all BTC``.

There is no evidence that this pre-mine has had any significant negative impact on the distribution or decentralization of Ethereum. It might not be the most decentralized way to distribute, but it's ignorant to talk about it as if it's some big "gotcha" moment about Ethereum that makes it some big rug pull.

Energy Waste
-------------

This is perhaps the most idiotic argument of all of them. Does Ethereum mining use a lot of energy? Yes. Of course it does, and that's obviously bad, until you realize that in less than 6 months (Q2 2022) the switch to Proof-of-Stake will `reduce that energy usage by ~99.95% <https://www.morningbrew.com/emerging-tech/stories/2021/05/19/proofofstake-make-ethereum-9995-energyefficient-work>`_, making this a non-issue.


Even if you don't care about proof of stake, it's still a red-herring to talk about. The problem is not that it uses a lot of energy, but that that energy comes from non-renewable sources. This would be a pointless discussion if that energy came from renewable sources. Not to mention that entire countries like El-Salvador as `exploring using energy from volcanoes to mine for crypto cleanly <https://apnews.com/article/cryptocurrency-technology-business-bitcoin-central-america-e0074a2343a3e3a9beb08723ff65ecf5>`_.

Even, ignoring all of that, ask yourself this, "How much energy does our current financial system use? What is the current banking systems' contribution to climate change?". It's all a series of misdirects meant to discredit Ethereum by people who don't understand it.

Memecoins and NFT's
--------------------

NFT's Actually
***************
I'll be honest with you here. Most NFT's are stupid. They are. Paying 100 Ether for an 8-bit pixel-punk is, at least in my mind, a waste of money. I right-click-saved this image because even I think it's ridiculous. But art was never the best-use for this technology. Ethereum was always meant to be a decentralized-computer, whose only limitation was what the community was able to come up with. Obviously not everything that gets made will be a world-changing idea, and to say that just because a lot of stupid things come out of it means its worthless is to miss the point. I wrote a longer explanation `of NFT's <https://thecryptoconundrum.net/introduction/picking_coins.html#nft-s>`_ about all the things you could do with NFT's besides stupid artwork.

To say that because the main use for Ethereum right now is stupid 8-bit artwork that can be right-cliked means that the whole platform is stupid is absurd. That's like saying "The adult-film industry is putting a lot of money into VR pornography, so VR is stupid and we shouldn't use it."

Shiba-Inu
*************

Shiba-Inu token is garbage nonsense. It's quite ridiculous how popular it got, but that's the downside of giving people power over finance. Clickbait news sources love to write headlines about Shiba-Inu price, market-cap, and which celebrities are shilling for it. What they don't tell you about is the dozens or hundreds of successful applications and startups that managed to raise money and expand the use cases for Ethereum, with that same tech. Case in point, DAO's. DAO's only work because they can issue tokens like Shiba, to anyone they want, to raise money. It's a new world of financial application like crowdfunding and governance.

The benefit of Ethereum is that it is permission-less. Anyone can create a token, market it, and sell it, with incredible ease. I can build my own shiba-inu token in `less than 5-minutes <https://vittominacori.github.io/erc20-generator/create-token/>`_. Sometimes that results in people creating nonsense, it's an unfortunate by-product of decentralization and an open financial-system.


It's Hard to Use
-------------------

There's a somewhat valid argument to be made here. You would be right in saying that on-boarding new users, using uniswap or DeFi, or a lot of other things is hard for the non-technical user. But that's because it's new. Think back to the mid 2000's. Most people were still going to banks for their needs. It wasn't until the banks started putting in lots of effort to online-applications that people started switching. My mother is in her 50's and she uses Venmo and online banking, because it has been made incredibly easy to do so.

Cryptocurrency has only been around for a little over a decade, and Ethereum for less than that. The focus of the community over that time has been primarily towards building a usable-network. But, now that popularity is skyrocketing, the focus on usability is increasing as well. Part of the issue right now is the difficulty in setting up a wallet, buying from an exchange, sending it off, etc.  As more businesses and services start to integrate however, it will be easy to onboard new people. I don't know exactly what that will look like 5-10 years from now, but it will certainly be easier.

I think the technology is getting better. Applications like `Brave Browser <https://brave.com/> and `Metamask <https://metamask.io/>`_ are on-boarding thousands everyday, and their services, at least in my opinion, are quite easy to use. I even did a `whole article <https://thecryptoconundrum.net/ethereum_explained/usability.html>`_ on how easy it is to use Metamask, with things like token-swaps built right in to the app.

*Rollups are hard to use. You can't expect people to make layer-2 wallets, onboard, move between rollups, etc. Using a layer-1 blockchain is key.*

Every criticism you can level at Rollups, or at Ethereum is true **only in the short term**. If your argument for Solana or Algorand is that it's simpler than rollups, you're already reaching. At the point where we're accepting the premise that layer-1 is easy to use, then it doesn't make sense to say rollups are tougher.

Let's look at what it would take your grandmother to do something takes to do something simple like provide liquidity on a decentralized-exchange, even on a layer-1 blockchain:
  1. They set up a wallet software, hardware or software. Meaning they first have to download and launch the app/extension.
  2. Create a new wallet, and write down the seed-phrase as a backup.
  3. They go to an exchange and buy the native-L1 currency (Sol, ADA, XTZ, AVAX, etc.) or token.
  4. They put in their address and send it off the exchange.
  5. They go to the website, select the token, find the right page, select the right inputs, and input the correct values.
  6. They confirm the transaction in their wallet and view it on a block explorer when confirmed.

People who argue it is necessary to use a Layer-1 blockchain, because of the complicated nature of this process, are arguing in bad faith. It relies on the assumption that everyone is able to use *every other aspect of Cryptocurrency perfectly*, but that the one extra step of using a rollup is too much. It assumes the premise that people are 100% capable of doing **ALL THAT**, but not checking a box on their exchange that says "send to Arbitrum network" instead of sending Ethereum. If we're going to believe that people are capable of understanding how to withdraw to Solana, or any other network, then it's reasonable to assume they will also be able to withdraw to a Rollup-network too.

I'm not saying that currently this is the optimal system for onboarding people either, but that's not the point. The way forward for Cryptocurrency relies on making every part of the onboarding process easier. It will get easier to use layer-2 solutions as well, so that people don't even know they're on it. The UX/UI design will get better, and easier over time. Cryptocurrency has been around a little over a decade, with Ethereum even less. To expect a fully formed, completely future-proof architecture, that's also the optimal UI-design is to know nothing about the history of technology.

At one point banks decided to switch over to online banking. With the help of marketing, of financial payment companies, and the community, they succeeded. Now almost all banking is done online. It didn't happen overnight. It was an end-result the sustained effort of thousands of people all over the world

*But Layer-2 Solutions are too fragmented, I can't use an app if it's on a different rollup system?*

True. But you also have 5 different payment-apps when you use Venmo, CashApp, Apple Pay, PayPal, and Zell. People don't seem to think that those are too hard to use and complain about the fragmented financial system. They find ways to make it work, typically by sending money back and forth between their bank.

This criticism also seems to forget that you can, and will continue to be able to send funds between rollups. In fact, as the tech gets better, this will become an invisible process. As developers work together to built interoperable systems, you will be able to use apps seamlessly. Let's say you wanted to use an app on ZKSync but you're on Loopring. In the future you'll be able to send one transaction. This transaction will move the funds around for you automatically, and automatically take action on the destination rollup without intervention. Perhaps there will be other work-arounds that haven't even been invented yet.

It would be one thing if the Ethereum community was being willfully ignorant of the issues facing the network right now, but that's just clearly not the case. In the beginning of 2021, there were little to no major rollup platforms. Now there are several, with billions in liquidity, and fees a fraction of the main chain.

It's Overvalued
----------------

If you think Ethereum is overvalued, then you're either not paying attention, or don't understand how market-caps work.
At it's price of ``$61k/BTC``, it's market cap was roughly ``~$1.2T``. For a cryptocurrency with no major upgrades and no purpose other than transferring from one person to another, this is a lot of money.

Ethereum, on the other hand, has absurd growth potential. At ``$4300/ETH`` it's market cap is only ``$500B``. This does not even account for the total value in Stablecoins, DeFi, Tokenized-assets, etc. It is only Ethereum. If the price were to more than double, to ``$10k/Eth``, it's market cap would be roughly *equal* to Bitcoin's. When you think about the potential Ethereum has when factoring in all of it's smart-contracts, games, DeFi, etc, a market-cap of that caliber might be an undervaluation. It's not unrealistic to think that within 5-10 years, with a more mature ecosystem, obscenely low-fees, and a more secure layer-1 chain, it's market cap could reach ``$2T`` or ``$3T``, bringing Ether's value to heights like ``$20k`` or ``$30k``. The sky is the limit.

Some researchers have even gone so far as to claim Ethereum is capable of hitting `$100,000/Eth within a few years <https://squish.substack.com/p/ethereum-the-triple-halving>`_

Conclusion
--------------

2021 has been a banner year for Ethereum, but it's also attracted a lot of scrutiny. Some of this is legitimate, but a lot is unfounded. It faces a series of fast growing competitors, but whether or not any of them succeed in their mission is anyone's best guess. When reading about Ethereum online, it can be tempting to fall for the fear, and be tempted to jump-ship. But before you do, ask yourself if that fear is unfounded. How much of it is people trying to shill for their own coins, hyped up by venture-capital firms, or just straight lies. Do your own objective research.

I know it's difficult, but patience is key. The bull run over the last year (2021) has led many people to expect things to happen immediately, for ridiculous price spikes, etc., but that's just not the reality of how things work. When you're dealing with an economy worth `a half a trillion dollars <https://coinmarketcap.com/currencies/ethereum/>`_ development needs to be focused on ensuring security and robustness, or it puts everything on the chain at risk. I look back at where things are now, vs. where they were in 2019, and while fees are higher, the ecosystem is undoubtedly in a better place than it was back then. Even in the last year, there's been `dozens of proposals and improvements <https://github.com/ethereum/EIPs/tree/master/EIPS>`_ to Ethereum that have flown under the radar, but continue to contribute to the long-term success of the network. Ethereum has been around for an incredibly short time when you look at the history of technology. Yet, it has the best long-term road-map for improvement, the most dedicated community, and a continued dedication to the principles that it was founded on. At the end of the day, that's what really matters. Follow the tech, and you will find the way.
