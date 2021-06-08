Transaction Fees
=================

Everytime you do something on Ethereum, you must pay a transaction fee in Ether. The amount of this fee varies based no the complexity of your operation and the speed you want to to happen at. How complex your operation is, is measured in a unit known as `gas <https://ethereum.org/en/developers/docs/gas/>`_. It is the fuel that allows it to operate, in the same way that a car needs gasoline to run.


How is it measured
--------------------

Gas is a unit that measures how much computation must be done to perform your transaction. The more things you do, the more gas you have to pay. 

It is a measurement totally separate from Ether. This means that whether the price of Ether goes up or down, the amount of gas used will be **the same**. Some example transactions and their gas cost

+---------------------------+----------+
| Transaction               | Gas Cost |
+===========================+==========+
| Ether Transfer            | 21,000   |
+---------------------------+----------+
| Token Transfer            | 46,109   |
+---------------------------+----------+
| Uniswap Transaction       | 158,403  |
+---------------------------+----------+
| Multi-Sig Wallet Creation | 393,047  |
+---------------------------+----------+


When you make a transaction, you pay a certain amount of ether per unit of gas used. This is typically measured in *Gwei* ``(GigaWei = 1 Billion Wei = 1x10⁻⁹ Ether)``. This is called the *gas price*

Therefore, you can calcualate your total transaction cost as: ``Transaction Fee = Gas Price * Gas Used``. The final number being expressed in Gwei, which is converted to Ether, as the numbers get larger.

Let's take an example transaction. I want to send 1 Ether to my friend. The gas cost of a simple 1 person direct Ether transfer is always ``21,000 gas``. Based on recent recent transactions the average cost of a transaction is ``25 Gwei``

I can calculate then that ``25 Gwei * 21,000 Gas = 0.000525 Eth ($1.37235)``.

If I wanted to speed up the transaction to be completed faster, I would simply increase the *gas price*. You cannot increase the amount of gas spent, only the price per. This is also why smart contract efficiency is so important. Being as efficient and minimalist as possible can substantially lower the gas usage for a user.

These values are automatically calculated by your wallet. They will pick varying amounts of Gwei for you, based on amounts used by recent transactions to give you an estimate of how much to spend.

.. image:: images/gas_tracker.png

This also means that at times when network usage is high, the gas price can go up as well. This is because everyone is constantly bidding higher than one-another to have their transaction included in a block, with limited space.


Gas Limits
------------

For some operations, like simple transactions, we know the gas cost (21,000). However, for many contracts, we have to make an estimate. If we don't provide enough gas to complete the transaction, then it will fail and the cost will **NOT** be returned to us. To prevent this from occuring, we have to include a special parameter called the *gas limit*. 

Gas Limit: 
	The **maximum** amount of gas that you are willing to pay for a transaction. Not all of the supplied gas will be used by the transaction, but this is the most you are willing to pay.

Let's assume we have a contract transaction that we estimate will consume ``100,000 gas``. This is an estimate, and given that its cost is high, we don't want the transaction to fail by not supplying enough gas. Therefore, we should supply ``125,000 gas``. The total transaction fee is calculated based on the *gas limit*. However, any gas that is not consumed, is refunded to you. So if you only use ``100,000/125,000`` you are refunded the extra ``25,000 gas * gas price``.

Don’t try and save gas by lowering your limit. It won’t change the amount of resources needed to process your transaction. Your transaction will just run out of gas and you’ll have to resubmit it, costing you more in gas fees.

This is all calculated by your wallet automatically when forming a transaction, but it can be sent manually. However, it is not suggested you modify this amount unless you know exactly what you are doing.


Why do we need gas
--------------------

Gas serves three very important functions:
	#. It decouples the amount of computation from the price of ether. The amount of computation stays exactly the same whether ether is worth ``$200`` or ``$20,000``. The value that changes is the *gas price*. This makes transaction fees a function of supply and demand. If people simply agreed to only make transactions with low gas prices, then transaction fees would stay low.
	#. It prevents network blocking. By using gas limit, a transaction will stop when the amount of gas runs out. This prevents a transaction from getting stuck and theoretically running forever, bringing the network to a standstill. Since there is a pre-determined amount of computation, the program must come to an end, at some point. This is what's known in computer science as `the halting problem <https://en.wikipedia.org/wiki/Halting_problem>`_. 
	#. It prevents network spamming. If there were no fees associated with sending a transaction, people could spam the network by flooding it with transactions to prevent legitimate users from getting through. Think of it like a DDoS. This is a problem that coins like `Nano <https://nano.org/>`_ are attempting to solve.


Block size
------------

Unlike Bitcoin, whose block size is measured in Bytes, the block size of an Ethereum block is measured in Gas. Each block has its own gas limit to how many transactions can be included, determined by amount of gas consumed. 

The block gas limit at block 0 was set at ``5,000``; any miner who mines a new block can alter the gas limit by up to about ``0.1%`` in either direction from the parent block gas limit. The gas limit as of April 2021 currently hovers around ``15 Million``.


This means that the sum of the *gas limits*, used by all transactions in the block, can be no more than ``~15 Million``. 

If a miner were theoretically to fill a block with only simple Eth transfers, then they could theoretically include 714 transactions in a block. 
	``15 Million / 21,000 = ~714``

In actuality, this is not the case, as miners will include many transactions involving contracts, as they consume much more gas and therefore have higher transaction costs. 

**"If contracts consume way more gas than transfers, then why don't miners just only include those transactions and ignore regular transfers?"**

	A good questions. Some blocks do. All blocks work on the auction model, where you're essentially bidding to get your transaction included. One of the answers is that more complex transactions will opt to pay a lower *gas price*. I.E while a simple transfer using ``21,000`` gas might use an average of ``25 Gwei/Gas``, a more complex contract using ``200,000 gas`` might opt to use only ``15 Gwei/Gas``, to keep costs from being extraordinarily high for the user, and keeping transactions competitive. It all depends on how long you're willing to wait for your transaction to be confirmed. You could theoretically pay ``0 Gwei/gas`` and have it be included if a miner chose to. They wouldn't, but the only thing stopping them from doing so is economics.

	With the coming `EIP-1559 <https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1559.md>`_, this block size limit will increase to ``~25 Million``. I will explain that more in depth later.

**"If gas limit per block is the only thing defining how many transactions we can include, why don't we just dramatically increase the size and eliminate scalability issues?"**

	We could. However, that creates centralization issues. When you either increase block size or the rate new blocks are created, the chain's data size will start to grow very quickly. This means that at a certain point, consumer grade hardware will not be able to support a chain so large. At that point only commercial entities and a few large players will be able to run full nodes to store the chain, increasing centralization. This is the fundamental tradeoff between scalability and decentralization. 

	This is how the alternative network `Binance Smart Chain <https://www.binance.org/en/smartChain>`_ operates. They sacrificed decentralization by increasing the block size, and only allowing a small number of people with professional-grade hardware to create blocks. This has undoubtedly increased their network speed, but at the cost of decentralization.


Tracking Gas
---------------

You can see which smart contracts consume the most gas `here <https://etherscan.io/gastracker>`_. 

It's also a useful tool for helping to determine the current price of gas for various services such as token-transfers and Uniswap swaps. Don't be afraid to 

`Eth Gas Station <https://ethgasstation.info/index.php>`_ is also a very useful site for you to estimate the cost of your own transactions, view the highest gas burners, and historical and current trends in gas usage.

