Developers Corner
==================

If you're here you have a familiarity with code, data structured, computing theory, etc. I'll break down the intricate technical details of how this all works.

Cryptography
--------------

Like all cryptocurrencies, Ethereum relies on `Public-Key-Cryptography <https://en.wikipedia.org/wiki/Public-key_cryptography>`_, and `Digital Signatures <https://en.wikipedia.org/wiki/Digital_signature>`_. 

Ethereum relies on `Elliptic-Curve Cryptography <https://en.wikipedia.org/wiki/Elliptic-curve_cryptography>`_, specifically the `Secp256k1 Curve Library <https://en.bitcoin.it/wiki/Secp256k1>`_. It shares this characteristic with Bitcoin, allowing many of the same library functions to be used. 

You start by generating a private-key pair using your favorite encryption library, keeping your private key secret. Your address is the `Keccak-256 (SHA-3) Hash <https://en.wikipedia.org/wiki/SHA-3>`_ of your public key. 

An Ethereum private key can be generated using the `BIP39 Standard Mnemonic Library <https://silentcicero.gitbooks.io/pro-tips-for-ethereum-wallet-management/content/ethereum-wallet-basics/using-seed-phrases-to-create-ethereum-accounts.html>`_. 

All transactions requre the use of the `Elliptic Curve Digital Signature Algorithm (ECDSA) <https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm>`_ from the private key associated with the address.

When using your private key to sign a message, you must also include a special value: a `nonce <https://medium.com/swlh/ethereum-series-understanding-nonce-3858194b39bf>`_. This is a scalar value equal to the number of transactions sent from this address or, in the case of accounts with associated code, the number of contract-creations made by this account. Every time you send a transaction this value increases, and is necesarry to ensure signatures are unique for each transaction to prevent double-spending.


Smart Contract Code
---------------------

In Ethereum, a smart contract is writen in a custom programming language, known as **Solidity** (although there are others such as **Vyper**). By spending ethereum as a transaction fee, you can cause the contract to execute in a pre-determined way. `Solidity is turing-complete <https://hackernoon.com/turing-completeness-and-the-ethereum-blockchain-c5a93b865c1a#:~:text=Solidity%2C%20the%20Turing%20complete%20language,deployed%20once%20on%20the%20blockchain.&text=A%20hacker%20can%20run%20any,to%20create%20an%20unauthorized%20effect.>`_, statically typed, supports inheritance, libraries, and complex user-defined types among other features.

Take the following code snippet of an example smart contract:

.. code-block:: solidity
	
	/*version number*/
	pragma solidity ^0.8.0;

	/*contract name*/
	contract example_contract {

		/*function name with parameters and return values*/
		function add(uint256 a, uint256 b) returns (uint256) {
        	return a + b;

    		}
	}

This is a smart-contract written in *Solidity*. It's name is *example_contract* It contains a single function, called *add*. This is a function that takes an input of two-numbers and adds them together, returning their sum. When you deploy this contract, it is given its own address, much like your wallet. If you wanted execute this contract, you would initiate a transaction with the contract's address, and execution information. This information includes the name of the function you are calling, the input values, cryptographic signatures, etc.

Because the contract has a valid address, when deployed it can also do things such as hold balances like a normal wallet. This allows you to do things such as send Ether and various tokens to it to hold, and distribute. However, nobody owns the private key to this address. If you wanted to withdraw from the contract, you would have to write in various functions to allow you to do so. Take this example code. 

.. code-block:: solidity
	
	pragma solidity ^0.8.0;
	
	contract example_contract2 {

		uint256 balance = 0;

		function send_ether(address payable recipient) payable {
        		balance += msg.value; /*msg.value is the transaction value*/
    		}
	}

This code contains a method that allows you to store and send ether from one person to another. If you see the word *payable* means that if you call this method, you can send ether alongside the input value of a recipient, and the contract will do with it what you specify. If you don't specify to send it somewhere, then it will hold the amount in its account balance for the contract. This is useful because it allows you to specify what to do if someone sends ether to the contract address, alongside relevant nput data. For applications like DeFi, or that involve sending money around, it is a very powerful tool for trustless funds exchanges.

Imagine what you could do when you take this concept and make it more complex.


**Contracts are immutable.** *This means that once a contract is deployed, it CANNOT BE MODIFIED. Certain variables can have values be changed, but code logic cannot. If you deployed and then realized that the contract had a bug, your only choice is to deploy a new contract that fixes this.*

**These next 3 sections are going to be more tech-heavy so if you don't have a CS or tech background, feel free to skip to the next article, as you don't need to understand it to be able to use Ethereum. Otherwise, i'm still going to try and keep it simple.**

Logs
------

You also have the option to publish the metadata about a transaction, that you define. These logs are known as *events*. Take the following code.

.. code-block:: solidity
	
	pragma solidity ^0.8.0;

	//Declare an Event
	event transfer(address indexed _from, address indexed _to, uint _value);

	
	contract example_contract2 {

		function send_ether(address payable recipient) payable {
        		emit transfer(msg.sender, recipient, msg.value);
    		}
	}

We first declare an event and its parameters. In this case it's *transfer* and it requires a sender, a recipient, and a value. When the function *send* is executed, it will publish this metadata to the chain alongside the rest of the transaction, as JSON data. This is done with the keyword *emit*. We can view this on a `block explorer <https://etherscan.io/tx/0x265d64a8d0e7f86cae84d29bc9b86dc796b0eaae9e84a99d0b1e82b17609b622#eventlog>`_ beautified to look like this

.. image:: images/events.png

*Image Source: Etherscan.io*

We can see the value of all the inputs. This is a high-level topic but because we used the keyword *indexed* on the two addresses, the EVM has classified them as topics. This is so that the EVM can more easily classify and reference them later. If we were to not use the *indexed* keyword, they would be below in the *data* category, alongside *value*

The address listed is address of the contract that emitted the log. This is necesarry because a contract may invoke a function on another contract, known as an *internal transaction*. This is still considered part of the main initial transaction for block purposes and is useful to keep track of transaction history.

More detailed information can be found `here <https://medium.com/mycrypto/understanding-event-logs-on-the-ethereum-blockchain-f4ae7ba50378>`_./

Accounts
----------

Unlike Bitcoin, Ethereum supports the idea of an account, with a balance. 

**"Wait, if Bitcoin doesn't actually have a balance, how come I can go to a website and it tell me how much Bitcoin I have?"**

This is a good question. The answer is that Bitcoin doesn't actually have the concept of an account balance. When you go to a website, that site specifically has indexed the blockchain on their own and created a local copy that they then serve to you. It looks through your transaction history and calculates how much Bitcoin you have, instead of looking at the chain directly for every query. This would be very slow. Your balance is the sum of all of your previously income transaction values. Each transaction has a BTC value. Imagine you wanted to send 5 BTC. Your wallet takes several transactions from your history, and bundles them together until the sum of their values is `>=5 BTC`. It then takes that amount, and sends it, and returns the extra unsused Bitcoin to you. 

Look at this example transaction

.. image:: images/btc_tx.png

*Image Source: Blockchain.com*

You can see that the input is multiple transactions until the amount is high enough to send it out to other places. This also means that amount you pay in transaction depends on how many inputs and outputs you need. If you look below you'll see that transaction fee is measured in sat/Byte. The Bytes is the size of the transactions together, and the sat is the amount of BTC you are willing to pay for each of those bytes (sat = satoshi = 1e-18 BTC).

Obviously this is a bad way of doing things because if you transact in smaller amounts, when you want to make a larger transaction those fees can add up. It's also just incredibly redundant, and prohibits layer-2 scaling solutions such as rollups and sidechains. This is why the only substantial Bitcoin proposed-scaling-solution is the Lightning Network, a side-channel implementation with its own set of problems.


On Ethereum, in order for contracts to be able to support the ability to transfer values, it must re-imagine this. I.E you must be able to query the amount of Ether in any address in existence and have a native balance value for each address in existence. This means that when you make a transaction, it is much simpler for the network to send coins around, and simplifies many API's and operations.

How is this done? Through a State Machine, which you may remember from sophomore year CS Class.

Blockchain as a State Machine
------------------------------

State Machines, if you've ever read this book, you're probably breaking out into a cold-sweat right now

.. image:: images/sipser.png
	:width: 180pt

*Image Source: Michael Siper, Introduction to the theory of computation, 3rd edition*

Don't worry, I'm going to keep it simple. The entire Ethereum network, at any given moment, can be represented as a state. Every time a transaction occurs, the state changes. Therefore we can represent the network as a state machine. The following examples are in the `Ethereum Whitepaper <https://ethereum.org/en/whitepaper/>`_. 

Think of it like this

``APPLY(S,TX) -> S' or ERROR`` where S = The current State and TX = The transaction value. 

In a real-world sense, iamgine the following: ``APPLY({ Alice: $50, Bob: $50 },"send $20 from Alice to Bob") = { Alice: $30, Bob: $70 }``. It took the current state of all balances, processed a transaction, and returned the new state.

In actuality, how the current state is determined is mathematically very tedious and involves `Merkle-Patricia Trees <https://eth.wiki/en/fundamentals/patricia-tree>`_. Since this is not a CS Lecture, (and I barely understand it myself) i'm not going to walk through how those work, but I can try if there seems to be demand for it.

This is important because we then can understand how smart contracts fit into this model. The use of a state machine allow the network to store the current state or values of a contract at any given time. Given as these contracts can have lots of variables to track, this is essential. It also allows us to create many layer-2 scaling operations off-chain. This I will explain later.

Ethereum Virtual Machine
--------------------------

To calculate the state, we first need to implement a valid transaction. We can do this through `The Ethereum Virtual Machine <https://ethereum.org/en/developers/docs/evm/>`_. Think of it like Java. When you write a program to do something, the Java code compiles down to bytecode, which is run through the Java virtual machine. This virtual machine runs on top of your normal Kernel, to make it OS-Agnostic and converts it further to machine code executable by your kernel. The Ethereum Virtual Machine works the same way. 

Every time you execute a transaction, the inputs and steps are converted into EVM-Bytecode. The machine takes the current state and performs the transaction and generates a new network-state. When you initially create a new contract, the contract gets converted to bytecode, and stored on the chain with its address. When you make a transaction the proper bytecode is queried and excuted. This also explains why contracts are immutable. 

The contract address is based on the creator's address and nonce at the moment of compilation, then hashed. Imagine the following function that gets called everytime a contract is created:

.. code-block:: python

	def mk_contract_address(sender, nonce):
    		return sha3(rlp.encode([normalize_address(sender), nonce]))[12:]


You cannot modify a contract, once deploy, because that would require recompiling the contract-bytecode, which is a special transaction. Given that the nonce for an address is incremented with every transaction, you would not be able to recompile the contract-bytecode and deploy it to the same address because the transaction would have a different nonce, and therefore a different address.

The following information is provided by `Ethereum Website <https://ethereum.org/en/developers/docs/evm/>`_:

	"The EVM executes as a stack machine with a depth of 1024 items. Each item is a 256-bit word, which was chosen for the ease of use with 256-bit cryptography (such as Keccak-256 hashes or secp256k1 signatures)."

	"During execution, the EVM maintains a transient memory (as a word-addressed byte array), which does not persist between transactions."

	"Contracts, however, do contain a Merkle Patricia storage trie (as a word-addressable word array), associated with the account in question and part of the global state."

	"Compiled smart contract bytecode executes as a number of EVM opcodes, which perform standard stack operations like XOR, AND, ADD, SUB, etc. The EVM also implements a number of blockchain-specific stack operations, such as ADDRESS, BALANCE, KECCAK256, BLOCKHASH, etc."

	"All Ethereum clients include an EVM implementation"

.. image:: images/evm.png

*Image Source: Ethereum Foundation, ethereum.org*

Bytecode, Sourcecode, and ABI
-------------------------------

EVM bytecode represented as a string of hex codes. Each byte represents one opcode (ADD, MUL, XOR, ETC.) and each opcode has a gas cost. Each ``ADD`` opcode is 3 gas, ``MOD`` is 5, ``KECCAK256`` is 30, and so on. This is how gas cost is calculated, and why efficiency and optimization is so important.  `Full opcode gas cost heres <https://github.com/crytic/evm-opcodes#table>`_.

It is important to remember, that when a contract is published, it is only publishing the EVM-Compatible-Bytecode, not the source code to the chain. The source code can be published on an explorer such as `Etherscan <https://etherscan.io>`_ where it can then be checked against the bytecode for accuracy. If you are deploying a contract, this is important so that people know what they are interacting with and how to do so properly. 

When you compile a contract, the compiler will generate an *Contract ABI (Application Binary Interface)* This is the standard way for you to properly create transactions by defining the functions and inputs required. If looks similar to JSON. If you publish a contract, you should also publish the ABI alongside it, on a block explorer or somewhere people can find it. Wallet applications will use this information to guide you through the process, compile, and properly encrypt and sign the transaction. Without it, people will have to decompile your bytecode and attempt to figure out how it works. This runs the risk of them sending faulty transactions. Transparency is your friend. Nobody can or will use a contract with faulty source code and no ABI.

An example, compressed for space. It includes all of the decompiled function information your wallet needs to create an EVM-Compatible Transaction: 

.. code-block:: json

	[{"constant":true,"inputs":[],"name":"name","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"view","type":"function"}

More info on ABI's can be found `in the documentation <https://docs.soliditylang.org/en/v0.5.3/abi-spec.html#:~:text=The%20Contract%20Application%20Binary%20Interface,as%20described%20in%20this%20specification.>`_


Transaction lifecycle
----------------------

What happens when you want to send a transaction. There are several steps:
	#. Constructing the raw transaction. This is in the form of a signed raw transaction hex. Your wallet constructs the raw transaction data, and signs it with your private key. This contains several fields:
		#. The Nonce, in hex. The unsigned integer that represents your transaction count, to prevent double-spends. It is incremented every time you make a transaction, to prevent replay transactions.
		#. Gas Price, in hex.
		#. Gas Limit, in hex.
		#. the recipient, the "to" field.
		#. the transaction value, in ether, also in hex.
		#. Extra transaction data. Only necesarry for a smart contract interaction. Calculated automatically by your wallet. If you want to do it yourself though, it's very easy:
			#. Take the sha3 of the function signature from the contract ABI, without the parameter names. 
				- If the function signature is ``mint(address to)``, then you should only use ``mint(address)``. This is because the EVM doesn't care about the parameters, it just needs to be able to identify the function.
				- ``web3.utils.sha3("mint(address)")``
				- ``0x7f9c8b4781db704d0917ecead0efa9e769fadacf34db8e74afcc18c0c8f35497``
			#. Take the first *4* bytes of the hash -> ``0x7f9c8b47``
			#. Take the input parameters, and convert to bytes32, a 32-byte hex string. If the value of the string is less than 32-bytes, pad it on the left. If it is an address, or already in hex form, just do the padding, no extra conversion required.
				- ``0xaB5409b0E5a66AcC9D63f668414539A60a5917C1``
				- ``000000000000000000000000aB5409b0E5a66AcC9D63f668414539A60a5917C``
			#. Repeat for each input parameter, and append to the function signature. 
	#. Sign the transaction with your private key.
	#. Submit your transaction request by sending it to a local node. This means that the transaction construction and signing can be done offline. This is often to protect the secrecy of the security key and prevent transaction tampering. You can do this using `Etherscan's nodes <https://etherscan.io/pushTx>`_ by submitting the raw transaction data.
	#. The node will propagate the unconfirmed transaction to its peers, if they choose they will add it to their mempool. Some may reject it if they feel the gas is too low or if the transaction is invalid. This is because the mempool has a finite size.
	#. The transaction sits in the mempool until a miner chooses to include it in a block. They include it in the block and execute the transactions and mine it until completion.
	#. Nodes propagate the new block and state information through its peers. If the block is accepted, they will add it to their chain. If not, they ignore it.
	#. Propagation continues until the entire network has the updated blocks. 
	#. Process repeats indefinitely.



