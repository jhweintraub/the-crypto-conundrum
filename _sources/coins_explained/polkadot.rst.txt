Polkadot (DOT)
===============

Background
------------

If you've been on any major cryptocurrency exchange, you may have noticed there's a LOT of coins. There's thousands of them, and they're all different. Some of them are faster, some are more private, some are more versatile, or energy efficient, etc. Some are exactly the same with different names. Regardless, each of them has a role to play in the future of crypto. Every time a new coin pops up it tries to occupy a new niche corner of the market, used for a different reason. Because of this, a popular phrase has arisen: *the future is multi-chain*.


In 1950, the Diner's Club International program was created. It was the first credit card of its time. Now, over 70 years later there are hundreds of cards. Each one has a different set of interest rates, rewards, terms and conditions, etc. They each all vie for market-share, but for most people, owning a credit card is not a zero-sum game. You can have more than one, and which one you use for any purchase depends on context and circumstance. When making a business purchase, use the business card. Buying gas? use the card that gives cash back.

In the future cryptocurrency will operate the same way. First there was Bitcoin, and it was what most people used for several years, without competition. Now, there are hundreds of different coins, and advanced wallet software gives you the power to use dozens of them from one application. However, while there are lots of different coins to choose from, it can be a pain to keep track of what you own, convert between them, and transfer funds over networks.

In its current form, the only way for most people to convert between Ethereum and Bitcoin is to either:
  1. Make a peer-to-peer transaction with someone in real life. Finding and trusting people to engage in these transactions is easier said than done.
  2. Send your coins to an exchange, sell Ethereum, and buy Bitcoin. This comes with its own cost. Selling your coins only to buy another has the potential to trigger a taxable-event in your country, that comes from a capital gain. You also have to pay the exchange fees every time you buy or sell. These fees can add up. This also presents a centralization bottleneck, which is to be avoided whenever possible.
  3. Use a wrapped token. However, this is good for gaining exposure to an investment asset, but not as a currency. Wrapped Monero  (WXMR) can be a useful investment tool, but doesn't preserve its privacy-features, and operates on the Ethereum blockchain.

A *multi-chain future* necessitates an easier way to move funds and data between blockchains. It needs a decentralized option. Let's look at the reasons why you may want something like this:
  1. Transacting in different coins. You may conduct most of your business in Ethereum. However, you decide that for one purchase you want to use Cardano. You could go to an exchange and buy Cardano and use that. But for the reasons I listed above, that's not a great choice. You need to able to fluidly convert your existing Ether to Cardano quickly.
  2. Investing. Perhaps you want to move some of your crypto to a different coin as an investment strategy, because you think the price will go up. You don't want to go through the problems of an exchange, and you don't want to leave it on an exchange either. Maybe you think the price of Bitcoin is going to drop soon, and you want to convert it to a stable-coin. You could convert it to USDC on Ethereum at a stable price, and convert it back when you were ready.
  3. Cross-Chain applications. Let's say you had an application on the Cardano blockchain, that monitored and used data from the Ethereum blockchain as input values to the contracts. You need a way for the two chains to send data back and forth.

The problem is that, in their current form, blockchains are isolated. They are self-contained islands, unable to reach to each-other. A blockchain node/app cannot reach out to another blockchain and see what's going on. Much like an island in the endless expanse of the ocean. With polkadot, blockchains become more like islands in an archipelago: separate, but close enough to interact and exchange. Polkadot is the ferry between them.

.. image:: images/polkadot/logo.png

History
*********

Polkadot was founded by `Dr. Gavin Wood <https://en.wikipedia.org/wiki/Gavin_Wood>`_, a co-founder and CTO of Ethereum alongside `Vitalik Buterin <https://en.wikipedia.org/wiki/Vitalik_Buterin>`_. He invented `Solidity <https://en.wikipedia.org/wiki/Solidity>`_, the language for writing Ethereum's smart contracts and helped write its original specifications. He left Ethereum in 2016 to found `Parity <https://www.parity.io/>`_, and work on Polkadot. As of 2021, they are preparing to roll out the main-net launch later this year. Although its main-net launch is still in progress, it has had several things until now. It has had a fully useable coin, DOT, for several years now. It also has an individually priced test-net-coin, Kusama, which is trade-able as well. Much like Ethereum and Ether, Polkadot is the name of the platform with DOT as the main currency.

The core features of Polkadot have been in development for several years now but the future is optimistic and expected very soon. Keep reading and i'll explain how it all works.

How it works
--------------

You should think of Polkadot not as a blockchain, but as a network of blockchains operating simultaneously. Polkadot is simply way to manage them and track their activities. This is done through two-mechanisms: para-chains, and the relay chain.

If you've read my post on `Ethereum 2.0 <https://thecryptoconundrum.net/ethereum_explained/eth2.html>`_, this system actually works *similar* to `sharding <https://thecryptoconundrum.net/ethereum_explained/eth2.html#id1>`_.

Para-Chains
************

A para-chain is any blockchain. It could be Bitcoin, Ethereum, Dogecoin, Monero, VeChain, etc. Literally any chain. They all operate independently, with their own consensus mechanisms, histories, protocols, etc. At full effectiveness, the Polkadot network has room to accommodate *up to 100 different para-chains.*

Polkadot has also created something known as the *substrate framework*. This is a toolset for developers to build very application-specific blockchains to fit as one of these para-chains. Using this toolset to build your blockchain makes deploying and building on polkadot simpler than doing it from-scratch. It also allows things like *forkless-upgrades*. However, it is not necessary to use in order to deploy on polkadot

The idea, is to have these para-chains be able to communicate with each other, whenever. Because they are operated independently, they can be updated by their respective communities without interrupting the Polkadot network.

.. image:: images/polkadot/parachains.png

*Image Source: Polkadot Website*

Relay Chain
*************

The relay chain is where the magic happens. It is the blockchain that sits above the para-chains. It keeps track of their status, the interactions between them, and decides what gets to be a para-chain. It is planned to someday be capable of tracking *100* para-chains. Each one of these fits into what is known as a *slot*. It can move a chain in or out of a slot, to keep the current para-chains changing. If a chain is included in one of the para-chain slots, its information is included in the relay-block.

This is where the Dot token information resides. Like all other blockchains, it has a consensus mechanism and creates blocks. These blocks contain the information about the state of the network, collected from all of the para-chains at the moment of block creation.

Since there are more chains than there are para-chain slots, Polkadot uses an *auction model* to decide what gets to fill it. People bid, in DOT, for the right to decide what chain should go in the slot. This is where it gets slightly confusing. Follow me here.

Each slot has a time-lock. When an auction occurs, the winner is the owner of that slot for *2-years*. Within that two years, it is subdivided into 8 quarters (3-months each). Chains can only be swapped in or out of the slot at the end of the quarter. For the duration of that 2-year period, the winning auction amount is *bonded* (locked-up). If you or your chain attacks the network or acts maliciously then your bond is burned and you forfeit it. Since the 2-year lease is split into quarters, that also gives the owner the ability to "sub-lease" the slot to whomever they want, for whatever reason. This has the potential to create a secondary market for the purchase of slot space. The slot can ONLY be updated or replaced at the end of the quarter.

.. image:: images/polkadot/relay_chain.jpeg

*Image Source: news.bitcoin.com*

Bridges
**********

A bridge is the interaction system between blockchains. There are several proposed solution for how this works, and it depends based on the scope and workings of the blockchain. In smart-contract enabled chains, this is expected to involve a "break-out contract". You would send funds to the contract, alongside identifying information, and someone would monitor it to facilitate the transfer of information to the intended destination chain.

In a non-smart-contract-chain this same system works with a "break-out-address", where you send funds to a specified address that will facilitate the transaction on the other destination chain. This may present a *"centralization bottleneck"*, but very smart people are working on ways to eliminate this as we speak.

All users involved in bridges are heavily bonded to ensure compliance and deter misbehavior and specifics of the bridge will depend on the currencies involved.

.. image:: images/polkadot/diagram.png

*Image Source: Polkadot White Paper*

DOT Token
**********

The DOT token exists on the relay chain. I like to think of it's use as part-way between Bitcoin and Ethereum. It is trade-able like Bitcoin, BUT it does not allow you to use smart contracts.

The relay chain does **NOT** support native smart contracts. The relay chain is meant to be AS MINIMAL AS POSSIBLE. This is not to say that polkadot does not support smart contracts. It only means that if you want to deploy one, you need to do it on a para-chain, NOT the relay chain. Since these are deployed on para-chains, you must pay for transactions and contracts with *that para-chain's* native token.

The DOT Token has three critical uses. Don't worry if this doesn't make complete sense yet, it will:
  #. Governance - Use your DOT token to vote on changes and upgrades to the network.
  #. Staking - Locking up your tokens to help secure the network - used by Nominators, and works similar to Ethereum but with slight differences.
  #. Bonding - Similar to staking, but the locked tokens are much greater, and gives you the right to actually create and attest to new blocks - Used by Validators.

Now you'll notice that I didn't include payments or transfers in that list. That's on purpose. The creators of Polkadot never intentioned for DOT to become a medium of exchange like Bitcoin or Ethereum. Rather, DOT's purpose is to secure the network and incentivize people to take part in it. DOT can be traded with a normal wallet, but given as there's no smart contracts to use it with, it's not an ideal currency for everyday purchases.

Users
************

This is part of the core of Polkadot. There are 4 types of users on Polkadot whom each have their own role in running the network. The role you fill defines things like your bond/stake requirements

  User Types:
      #. **Validators** - These are the top level users in the hierarchy of Polkadot. They are the most important people. They are essentially the *miners* of the Polkadot platform. They manage and run the relay chain. When new blocks are created on the relay chain, it is done by a validator. They are *heavily* bonded, with their very large token amount locked, because their work is so important.
      #. **Nominators** - These are the people slightly below Nominators that keep them honest. Unlike Etheruem's Proof of Stake, Polkadot uses *Nominated Proof of Stake*. In Ethereum, anyone can become a staker if they have enough Ether to stake. Every one of these stakers must attest to every valid block produced. In NPoS, you don't have to do that. Instead, anyone can delegate their DOT tokens to another person, to stake on their behalf. The people you *nominate* in your place are the *validators*, and your stake is part of their bond. You are rewarded for providing part of their bond dependent on how much you provide. The onus is on you to pick someone honest and to monitor them to ensure they don't lose your stake. The **only job** of the nominator is to delegate your DOT to a bond-holding validator, and ensure they act honestly. If they act dishonestly or get penalized, so do you.
      #. **Collators** - Collators are kind of like the *helper-elves* of validators. Each validator is responsible for monitoring and verifying the authenticity of a specific para-chain. However, they must also simultaneously keep track of the relay-chain. This creates a significant amount of storage and bandwidth overhead for the validator to store 2 complete chains and monitor both in real time. The solution is to once again delegate authority to a lower entity. The Collator watches over the designated para-chain for the validator. They monitor it, identify its status, and report on its condition to the validator they work with. This information is included by the validator in their block on the relay-chain. They are not required to stake/bond anything. However, because they work very closely with the validator, the relationship between the two is defined between them. A likely scenario involves the validator requiring their collator to contribute to the bond as well to ensure that they have a stake in the outcome. The collator's maintain a full-node on the respective para-chain, enabling them to create and monitor new blocks on the chain. For example, if your collator watches over the Bitcoin para-chain, think of them as being a miner and also a Collator simultaneously.
      #. **Fishermen** - Think of Fishermen as auditors. They are not related to the block producing process, but rather watchers. They monitor the para-chains and relay-chain, looking for misbehavior and misconduct. If they spot people acting maliciously, they can turn them in and receive a reward. When they spot something fishy, they do have to put up a small bond however. If the network rejects their suspicious activity report, the bond is taken away. If it is approved they are rewarded, with the amount depending on the size and severity of the violation. They act independently and the process can be automated. In order to be a Fisherman, you must first run a full-node and be constantly vigilant.

.. image:: images/polkadot/roles.png

*Image Source: Polkadot White Paper*

Kusama
-------

Polkadot also has a weird *cousin-platform* called `Kusama <https://kusama.network/>`_. Think of it like a staging ground for new and pending builds. New features and builds are deployed to the Kusama network first, and then the polkadot network when they're stable and ready for production. Kusama is the native coin of the network, and has a dollar-value. It is slightly coupled to the price of polkadot. I do not recommend buying Kusama because it is inherently a more unstable network with more bugs and updates than the polkadot network.

.. image:: images/polkadot/kusama.png

*Image Source: Polkadot Medium Page*


Is DOT an "eth killer"
------------------------

**ABSOLUTELY NOT**. In no sense is Polkadot even a competitor to Ethereum. This is true for a couple of reasons:
  #. Polkadot is not intended to be used as a primary currency. You won't be paying for things with DOT like you would with Ether. That alone would take it out of competition. It uses a wallet and operates like all other cryptocurrencies, but the community has less interest in promoting direct-DOT-transfers over network upgrades.
  #. Polkadot does not support smart contracts. There is no DeFi, Uniswap, DAO's, etc. on Polkadot. There are smart contracts and applications, but they are on a polkadot para-chain, NOT the relay chain. This means you'll be using that para-chain's coin to use those applications instead of DOT. Without native applications there is no way that DOT could or would compete with Ethererum.
  #. It doesn't need to. Ethereum is meant to be the world's decentralized computer. Polkadot servers a different niche purpose. It's goal isn't to be a decentralized computer, but simply to facilitate communication between blockchains. Ethereum's growth doesn't impinge upon Polkadot's and vice versa. The two of them can grow together. In fact, if polkadot is successful in making onboarding to Ethereum easier, than its possible that Ether's value will rise as well, because of its growth in popularity.

If you don't believe me here's some quotes from the `Polkadot White paper <https://polkadot.network/PolkaDotPaper.pdf>`_ that makes this point as well

  "Minimal: Polkadot should have as little functionality as possible...no additional complexity should be present in the base protocol than can reasonably be offloaded into middleware, placed through a parachain or introduced in a later optimisation".

  "Contracts cannot be deployed through transactions; following from the desire to avoid application functionality on the relay-chain, it will not support public deployment of contracts".

  "In the event that the relay-chain has a VM and it be based around the EVM, it would have a number of modifications to ensure maximal simplicity. It would likely have a number of built-in contracts (similar to those at addresses 1-4 in Ethereum) to allow for platform-specific duties to be managed including a consensus contract, a validator contract and a parachain contract".

Future predictions
-------------------
**I am not a Financial Advisor. Nothing said here is financial advice. I am not liable for any losses you may incur while investing. Investing in Cryptocurrency is a financial risk, and you should do your own research prior to any purchases.**

I think that before I talk anything about the price, its important to know where Polkadot is right now.

As of July 2021, there are no Para-chains on the main polkadot network. There is only the relay-chain. However, Kusama is in the roll-out phase of deploying the first para-chains. Assuming it all works as planned, it is expected that within the next-year these updates are going to be deployed to the main-net. You should watch their website and their news releases for any updates.

It is expected that Polkadot will be able to support up to *100 para-chains* at its peak. Polkadot has been in development since 2016, and is moving on-schedule. When the network decides to upgrade the main-net, they will begin slot-auctions to decide which para-chains may be included.

I'm not gonna make a price prediction, because I just honestly don't know. The only thing I will say is that it's all time high (ATH) is at *$49*, from February 2021. In July, it's *$11.5*. It's current market cap at that price is *$11.6 Billion*. You can do the math on the ATH market cap, but it's not unreasonable to say it's going to surpass its all time high. Once it successfully deploys parachains and bridges, it can easily surpass *$50*.

The roadmap can be found `here <https://polkadot.network/launch-roadmap/>`_.

In place of a definitive price prediction i'm rather just going to say that this coins is a **BUY**.

.. raw:: html

    <div class="nomics-ticker-widget" data-name="Polkadot" data-base="DOT" data-quote="USD"></div><script src="https://widget.nomics.com/embed.js"></script>
