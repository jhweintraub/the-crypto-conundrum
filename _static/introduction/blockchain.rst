The Blockchain
===============

How does it work?
------------------

The core of the blockchain relies on two things: cryptographic-security and decentralization. You may have heard the phrase "distributed-ledger-technology". This means that the blockchain is a simple record of transactions. 

Imagine your bank. Your bank has a database somewhere, with every customer's information including their balance. This is a centralized service, it's all in one location. If you wanted to send money to someone else also at your bank, their software simply subtracts the amount from your info in the database, adds it to someone else's, and records the transaction info. That record of transactions is a ledger of-sorts. Cryptocurrency works the same way, except distributed. This means that every person in the network has a copy of this ledger of transactions, and everytime a new transaction occurs, every copy of the ledger gets updated with it. 

As thousands of transactions occur every second, these transactions get bundled together into what's known as a block. This block includes many transactions as well as identifying information such as time-stamps, security information, and info from the previous block. This block is then added to the ledger's history, creating what looks like a chain. The image below should help illustrate this. This model allows you to trace the history of every transaction and coin back to its origin point, and even back to the original bitcoin transaction. Once information is on the blockchain it can never be removed, only more added. 

.. image:: images/blockchain.png


When you say that you own "A bitcoin", what that really means is that there's a transaction line somewhere in the blockchain that says someone gave you 1 Bitcoin. There's no actual coin or value relating to any particular coin. It is simply a notation that says you own something in theory.

Image Source: `3Blue1Brown <https://www.youtube.com/watch?v=bBC-nXj3Ng4&t=1130s>`_.


Transaction Fees
-----------------

	Every transaction contains a transaction "fee". This is a small amount added to the transaction paid by the sender, and awarded to the person who adds the block to the chain. Think of it like a credit card transaction. The store you are exchanging with pays the credit card company for the ability to take cards. However, with this the customer pays a small fee to process the transaction, in exchange for the ability to use cryptocurrency. This fee is independent of the amount being sent. If you send $5 or $5 million, the fee should be the same. You can increase this fee to incentivize the transaction to be sent faster, or a lower one if you're willing to wait for confirmations.


I think this video explains it best:

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/bBC-nXj3Ng4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Security
---------

Why is Decentralization Superior?
**************************************

Every time a transaction occurs, it propagates throughout the network of people running it (nodes). These nodes come to a consensus on the current status of the network after every transaction. This is better for security. While a hacker would only have to infiltrate one bank server to steal your funds, hacking the blockchain requires infiltrating thousands of machines at once around the world. When no one person controls the system, no one person can cause chaos and destroy everything.

I think Vitalik Buterin (Inventor of Ethereum) said it Best:

	"I happily played World of Warcaft during 2007-2010, but one day Blizzard removed the damage component from my beloved warlock's Siphon Life spell. I cried myself to sleep, and on that day I realized what horrors centralized services can bring".

	--  Vitalik Buterin, actual quote.

.. image:: images/decentralization.jpg


Does this mean that Cryptocurrency is unhackable?
**************************************************

**NO** it doesn't. While the underlying technology that allows the network to function is mathematically solid, hacks occur all the time on people that own cryptocurrency. Much like credit card theft, someone who steals your crypto wallet information can steal your coins. However, with enough practical security measures and common sense, you should be more than protected. The weakest part of this system is human error.


Storing your Cryptocurrency
----------------------------

So can I just sign up with an email and a password like normal?
****************************************************************

Kind of. In order to buy Cryptocurrency you'll need to go through an exchange and set up a wallet.


What is a Cryptocurrency Wallet?
*************************************

The crypto wallet is how you interact with the blockchain and send transactions. Without going into too much detail, your wallet is an encryption key that you use to prove that you are the owner of certain coins. The wallet software will take the key, do a lot of math, and send and verify the transaction for you. It's similar to how Venmo deals with your money, you don't need to know how it works, just your info to log into your account.

When you create a wallet, it will generate the key for you in the form of a "mnemonic phrase". This is a 12 or 24 grouping of words, that the software uses to generate the keys. Write this down and keep it somewhere safe. With these words, you can use any wallet software and access the funds. However, if you lose it, it's gone **FOREVER**.

	``witch collapse practice feed shame open despair creek road again ice least``

The wallet also generates what's known as your address. It's the identifier associated with your wallet. Unlike venmo though, where it's a human readable word, it's a long string of numbers and letters. The exact format will vary based on the coin you're using, but it should look something like this.

	``0xaB5409b0E5a66AcC9D63f668414539A60a5917C1``

When someone wants to send you money, you just give them that string and they send it there. All wallets also give you the option to generate a QR-Code, for the person to scan. If you want to make a transaction, simply scan the code, select the amount, and you're off to the races.

.. image:: images/qrcode.png
	:width: 120pt

Since the blockchain is public and add-only, anyone can view your address' current balance and the history of all transactions. Just go to a website such as

`Ethereum Blockchain Explorer
<http://etherscan.io/>`_.

`Bitcoin Blockchain Explorer
<https://www.blockchain.com/explorer/>`_.

and type in your address to see the full history.
