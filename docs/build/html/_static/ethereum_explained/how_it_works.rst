How Ethereum Works
====================

The Ethereum platform, at its core, is simply a way for people to move cryptocurrency from one person to another, as payment for the use of computing power.

Ethereum is the name of the platform, while the cryptocurrency you exchange is known as *Ether*. It is the core of the platform and spending it is required to do anything.

When you use Ethereum, you are paying miners/stakers to do difficult computations for you, while they maintain the integrity of the network. Everything you do on Ethereum requires you pay these people a fee, in Ether (the native coin). This is the transaction fee, known also as gas (i'll explain more later). If you are doing something more computationally difficult, this fee is higher because there's more computation that must be done.

Simple transactions such as sending to your friends, will have a lower cost because they are less computationally strenuous. Initiating a smart contract with thousands of lines of code, will cost a lot more. This amount will vary based on transaction size and how fast you want it completed.

The Ethereum blockchain operates on a distributed consensus-model, just like Bitcoin. Coin transactions are grouped together into blocks, created at pre-determined intervals known as the *block-time*. They are then dispersed to the rest of the network where transactions are verified and if a consensus is reached on its validity, added to the chain.

In Bitcoin this is roughly every ``~10 Minutes``. In Ethereum its ``~13.17 Seconds``.


The US dollar can be split into 1/100th of itself (1x10^⁻²), that measurement being a penny. Ether works similarly, except its smallest denomination is 1x10⁻¹⁸. This is known as a *wei*. There are various measurements of Ether, listed below

+---------------------+-------------+---------------------------+
| Unit                | Ether Value | Wei Value                 |
+=====================+=============+===========================+
| Wei                 | 1x10⁻¹⁸     | 1                         |
+---------------------+-------------+---------------------------+
| Kwei (babbage)      | 1x10⁻¹⁵     | 1,000                     |
+---------------------+-------------+---------------------------+
| Mwei (lovelace)     | 1x10⁻¹²     | 1,000,000                 |
+---------------------+-------------+---------------------------+
| Gwei (shannon)      | 1x10⁻⁹      | 1,000,000,000             |
+---------------------+-------------+---------------------------+
| microether (szabo)  | 1x10⁻⁶      | 1,000,000,000,000         |
+---------------------+-------------+---------------------------+
| milliether (finney) | 1x10⁻³      | 1,000,000,000,000,000     |
+---------------------+-------------+---------------------------+
| ether               | 1           | 1,000,000,000,000,000,000 |
+---------------------+-------------+---------------------------+

*Most of those are never used, except for Wei/Gwei, which is used for calculating transaction fees. Even then you don't really need to know this chart, it's here for educational value*.

This explanation leaves out a lot of things, but is a very simple explanation of things.

Your Wallet
------------

The next article should cover a much more detailed explanation on the basics of wallets. For now i'll be keeping it simple. Like I explained in the `Blockchain Introduction Article <https://thecryptoconundrum.net/introduction/blockchain.html#storing-your-cryptocurrency>`_, a wallet is  as simple as downloading an application. It's an encryption key used to verify you are the owner of an address. The difference is that different these wallets are more versatile, as they let you interact with smart contracts, which I'll explain below. For example, some wallets operate as browser extensions, accessible with one click. This is so that when you go to a website, the site can automatically launch the wallet and set up a transaction to another person or contract as easily as possible. It also allows you to send tokens on the Ethereum blockchain as easily as you would send Ether.

You can check your balance of your address `here <https://etherscan.io>`_.

I'll be covering how to use this and set it up later.

Smart Contracts Explained
---------------------------

In Ethereum, transactions are more complicated than Bitcoin. In Bitcoin, the only thing you can do is send from one person to another. In Ethereum, interacting with a Smart Contract is a valid transaction, that can be included in a block. When you make one, it is processed same as a simple-transfer, and included in a block, alongside hundreds of others. To the network, it is not treated any different than a regular transaction, except that it contains more information to be processed. This is because a smart contract, is just an application written in a programming language, like all code.

I want you to imagine, if you will, a lottery. Everyone across the nation goes to a store and buys a ticket and that money goes into the pot run by the government. The government is the centralized actor, and lottery operation relies on trust at a lot of stages. Trust that your money changes hands into a pot and everyone is honest. Trust that the government actually pays out to the winner, and so on and so forth.

Smart Contracts are decentralized, autonomous, and transparent actors. Every part of the above system can be automated with code, eliminating the need to trust a central service. with a piece of code you can contribute to the pool directly, randomly select winners, and disperse rewards directly and anonymously. You only need to trust the code.

It is the decentralization and automation of that responsibility, and instead allows you to trust code. Nobody can tamper with it. Once it is deployed, its code cannot be changed. It can be destroyed, if programmed to, but not changed. Everyone can view and audit it, to ensure its validity. This is why honesty is such an important part. If you write your contract in a malicious way to benefit yourself, everyone will notice, and won't use your application.

Much like regular web applications, you can interact with them without knowing at all how they work. Although they are complex pieces of code, with proper design, you can create and send transactions to them without having to know about the underlying code at all. If you're interested in this, visit the Developer's Corner at the end of this series.

A smart contract operates autonomously, but must be called by a human. When you make a transaction, you call a specific contract, and a function within that contract. The contract operates in a pre-determined way. The way it operates is defined by the code, at the time it is deployed. Given the same inputs, it will always produce the same outputs. Contracts can call on other contracts to do things, on and on in an infinite chain. Keep in mind though, this process gets prohibitively expensive the more contracts you involve.

Anyone in the world can deploy a smart contract, provided you pay the fee associated with it. The more complex the code, the higher your transaction fee will be. Whoever deploys it sets the rules of who is allowed to use it. You could say anyone can use it. You could limit it to only allowing specified addresses. You could even say anyone could use it provided they first met a series of conditions. The rules of which are defined in the source-code.

It has a balance, just like any wallet, and can send any coin or token to any other existing address, including another contract. Think of it like going to Google.com. Until you make a request to Google's servers, they sit idle with the information you want, and then wait for your request information and process it, returning the expected results. This works the same way but decentralized. Although it has a balance, it is autonomous, and nobody controls it. The difference between this and a wallet is that a wallet is software, operated by you, that sends transactions from your address. You cannot send a transaction as a contract. This means that even though it has a balance, and an address, there is no seed phrase that would allow you to act on behalf of the contract. Instead, you would write the code so that it does something like sending Ether to another person. The contract's action to send Ether has to be initiated by your externally-owned-address (EOA), invoking the action on the contract. If you were to look at this afterwards, you would see only a single transaction. That transaction included your address as the initiator, the contract as the recipient, and all of the actions the contract took.

A good example of this is that you could write a contract that says "on the directive of this specific address, send a specified amount of money to this other address". You have to specify all factors like amount, who can invoke the contract, and everything you want the contract to do, when you write it, as it cannot be changed once deployed.

.. image:: images/sc_diagram.jpg

Image Source: `Enuke Software <https://www.enukesoftware.com/blockchain-application-development.html>`_

These contracts have their own unique programming language, which can be written like any other language would. It's very similar to Java or Python

You must pay a transaction fee anytime you wish you change the state of a contract. I.E anytime you want it to do something. If you want to change a value that costs Ether. However, to read a contract or get a current value, it is free. You can get the value of *10,000* different addresses, and not pay a cent. However, the moment you want to change a value or send someone something, you have to pay.

Block Explorers
*****************

When you make a transaction, it is public to the world. Anyone can view it from anywhere with an internet connection, or offline if you have a full download of the blockchain offline. This can be done from a `block explorer <https://etherscan.io>`_. A *block-explorer* is simply a website that allows you to view any piece of data on the blockchain. You can go back to the first block, and look at the history of the first coins as they change hands up until the present. Any contract, its source code, and every transaction ever made to it can be viewed as well. They also include other useful information that the site personally compiles, such as fee estimates, important metrics, and usage analytics. This system of transparency is one of the things that makes the blockchain unique. There's nowhere to hide.

Each blockchain has its own block-explorer. They are fantastic resources to learn about all things in the ecosystem, how they work, etc.

.. image:: images/etherscan.png

*Etherscan Block-Explorer Homepage*

.. image:: images/eoa_txs.png

*An Etherscan page for an individual non-contract address*.

.. image:: images/tether_txs.png

*The Etherscan page for the Tether Token. It shows a list of all transactions in its history*

.. image:: images/tether_functions.png

*Some of the functions that the contract can perform when invoked, organized by if they are read or write functions*

.. image:: images/tether_contract.png

*The source code for the Tether token pictured above*

As you can see, there is a lot of information to parse through. But, there's a ton of things you can learn and it can be fascinating to look through.

Two important things to keep in mind:
  #. This website is not a direct-node. The website operates a node, and has done its own indexing of the blockchain, and compiled this resource of information for you in real-time. It is updated with every new block. This allows them to give you more information than a normal node would.
  #. Etherscan has two pages for various tokens. One is the tracker, and the other is the contract. This is because a token is simply a complex-contract. This is discussed much more heavily in the `tokens explained <https://thecryptoconundrum.net/ethereum_explained/tokens.html>`_ page, so don't worry if that doesn't make sense yet. They will contain *almost all* of the same information, but by categorizing it this way, it provides a much better user-experience and is much cohesively organized. If you wanted to look at the source code, you will need to look at the *contract-page*. To see more broad-information about things like economics and availability, the token page is more apt.
  
