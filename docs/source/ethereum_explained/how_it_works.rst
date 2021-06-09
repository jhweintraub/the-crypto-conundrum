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

In Ethereum, transactions are more complicated than Bitcoin. In Bitcoin, the only thing you can do is send from one person to another. In Ethereum, interacting with a Smart Contract, is a valid transaction that can be included in a block. This is because a smart contract, is just an application written in a programming language, like all other code. 

I want you to imagine, if you will, a lottery. Everyone across the nation goes to a store and buys a ticket and that money goes into the pot run by the government. The government is the centralized actor, and lottery operation relies on trust at a lot of stages. Trust that your money changes hands into a pot and everyone is honest. Trust that the government actually pays out to the winner, and so on and so forth. 

Smart Contracts are decentralized, autonomous, and transparent actors. Every part of the above system can be automated with code, eliminating the need to trust a central service. with a piece of code you can contribute to the pool directly, randomly select winners, and disperse rewards directly and anonymously. You only need to trust the code.

It is the decentralization and automation of that responsibility, and instead allows you to trust code. Nobody can tamper with it. Everyone can view and audit it, to ensure its validity. 

Much like regular web applications, you can interact with them without knowing at all how they work. Although they are complex pieces of code, with proper design, you can create and send transactions to them without having to know about the underlying code at all. If you're interested in this, visit the Developer's Corner at the end of this series.

A smart contract operates autonomously, but must be called by a human. When you make a transaction, you call a specific contract, and a function within that contract. The contract operates in a pre-determined way. It has a balance, just like any wallet, and can send any coin or token to any other existing address, including another contract. Think of it like going to Google.com. Until you make a request to Google's servers, they sit idle with the information you want, and then wait for your request information and process it, returning the expected results. This works the same way but decentralized.

.. image:: images/sc_diagram.jpg

Image Source: `Enuke Software <https://www.enukesoftware.com/blockchain-application-development.html>`_

These contracts have their own unique programming language, which can be written like any other language would. It's very similar to Java or Python

You must pay a transaction fee anytime you wish you change the state of a contract. I.E anytime you want it to do something. If you want to change a value that costs Ether. However, to read a contract or get a current value, it is free. This can be done from a `block explorer <https://etherscan.io>`_, because if you wanted a contract to read from another contract, that you would have to pay for.



