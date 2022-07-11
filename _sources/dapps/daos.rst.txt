Decentralized Governance and DAO's
====================================

The Problem
-------------

Let's imagine you have a great idea, and want to start a business. You appoint yourself CEO and slowly grow your business. As the head, the buck stops with you. You reap some rewards if successful, but shoulder the blame if otherwise. You singlehandedly have the power to do things that could adversely affect the success of the business. You could dodge taxes, skirt regulations on product manufacturing, embezzle funds, etc. This is a risk, and one that we see time and time again. The rise of Ethereum and other blockchain platforms has also allowed the creation of a large field of Dapps, with billions of dollars of crypto under their control. These applications rival multi-billion dollar financial institutions in their scale and complexity. The problem is that with privacy and decentralization, comes scams and malicious actors.

When a business breaks the law and defrauds customers, they answer to the legal system. The executives are held to blame, and new changes occur from the top down. The central-authority (the legal system) holds other centralized authorities to account and sometimes offers restitution. When a dapp's funds are held by a single actor, they hold the power to steal them, and skip town to never be heard from again with your money. This `happens <https://en.wikipedia.org/wiki/Mt._Gox>`_ `more than it should <https://www.cylynx.io/blog/the-rise-of-cryptocurrency-exit-scams-and-defi-rug-pulls/>`_. A truly decentralized world requires a different way of thinking. The solution is to democratize the decision-making process.

Instead of vesting power in the executives, a central authority, decision-making power is vested in the consumers themselves. They make the decisions, and no single person is able to individually cause havoc. It takes a village to raise a child, and also a Dapp. Just as public-companies will allow shareholders to vote on certain business proposals, decentralized governance takes it one step further. Any decision, no matter how small must be authorized by consent of the community. It is a system of transparency, decentralization, and zero-trust. Every action is transparent in exactly what it does, how it works, and how proposed it. Votes on these changes are handled by the code, with complete trust and transparency. Protocol changes, fund transfers, even membership is decided by the community.

.. image:: images/daos/structure.jpg

As of June 25th there was over **~$4.5 Billion** in locked liquidity in `Uniswap V2 <https://v2.info.uniswap.org/#/>`_. It is essential to the Ethereum ecosystem, so handing control of it over to a single entity presents a huge risk. While it has a team of core-devs, actively working on proposals and improvements, all major changes come from the community. This delegation of power ensures its stability and minimizes risk of rug-pulls.

In April 2021, Wyoming became the first state to `legally recognize DAO's as legal businesses (LLC's) <https://www.coindesk.com/wyoming-dao-llc-law-passed>`_, so clearly it's got a lot of potential, and is here to stay.


*Image Source: Blockchain Education Platform*

A governance system has three parts:
  #. The underlying protocol
  #. The governance contract.
  #. The governance token

.. image:: images/daos/dao-components.png

*Image Source: codecentric Blog*

The Protocol
-------------------------
  This is simply whatever the application you are using is. It could be `Uniswap <https://v2.info.uniswap.org/#/>`_, `Compound <https://compound.finance>`_, `1Inch <https://1inch.io/>`_, `Tornado-Cash <http://tornado.cash/>`_, etc. Anything at all. In fact, any contract can be configured to work with a governance system. Any function that changes something about the contract can be configured to work this way. It works by using a *function modifier*. This basically means that contract itself is configured so that it's functions can only be invoked by a pre-determined address. Many applications use this to determine ownership, where only a person with a specific address can invoke the function. However, in this case the owner is a different contract, the governance contract.

Governance Contracts
-------------------------

  This is a smart contract, or a series of contracts, with specific rights to invoke functions on the protocol contracts. However, because it is a contract itself, it first has to meet certain criteria and function calls in order to do so. Every contract has three parts:

The Proposal
*************

  This is a function that anyone can call. You submit a request to call certain functions within the relevant contract. This proposal contains all the detailed information necessary for the contract to invoke another. You have to input which contracts you want to call, which functions, the required inputs for those functions, a description of your proposal, and important voting information.

The Voting
************
  Before a proposal can be executed, the proposal has to be voted on by all relevant stakeholders. Who is considered a relevant stakeholder is determined based on the specifics of the contract. You could technically allow anyone to vote with no prior commitment, but this is a bad idea as it allows anyone to hijack the process by creating tons of new accounts for the sole purpose of voting. The best way to do this is to force people to hold some kind of asset before voting. While some DAO's manage membership with NFT's, the more common choice is to use `ERC-20 Tokens <https://thecryptoconundrum.net/ethereum_explained/tokens.html#erc-20-fungible>`_. Some contracts require that you "lock up" these tokens first however. Before voting, everyone must deposit ``>= 1 Ether`` into the contract. Once you deposit it into the contract, you can vote on any proposals. You can unlock your deposited funds at any time but it means you lose your right to vote until you lock them up again. Some voting systems tie your holdings to your voting weight. ``1 Ether = 1 Vote, 2 Ether = 2 Votes, etc.``. Some contracts say *1 person 1 vote*. It's up to the developers and contract creators to decide that.

  The only downside to this system, is that it can create a decentralization bottleneck if done improperly. If the initial supply is not dispersed well, it can allow a few actors to accumulate significant voting weight over proposals. This is why some airdrops choose to distribute equally to all users. When Uniswap did `their airdrop <https://www.coindesk.com/uniswap-dharma-retroactive-uni-airdrop-defi-governance>`_, all users, whether they had exchange ``$5`` or ``$5 Million`` got the same amount of tokens. Tornado Cash did `theirs proportionally <https://cointelegraph.com/news/torn-soars-200-as-tornado-cash-s-governance-token-becomes-tradable>`_, but it's not apparent that this had any significant impact on its governance system.

  However, with some prior-planning you could deploy another governance contract that had the authority to change the rules of the initial voting system. You could create it with several different consensus types and requirements, specified by the proposal creator. When you want to vote, you simply call a *vote function* within the governance contract signaling your support or opposition to the proposal specified. This function will often take a proposal number, so that there can be multiple on the table at once. If this system seems daunting, keep in mind well-designed applications will include a web-ui where you can view the proposals and vote on it with a few clicks. Because all of these are contract calls, you will have to pay transaction fees to create proposals and vote. Some governance protocols also give you the option to delegate your voting power to someone else, by specifying an address. There are `many different types of voting systems <https://medium.com/daostack/voting-options-in-daos-b86e5c69a3e3>`_, which you'll need to decide for yourself which to use.

The Execution
******************
    This is when the contract calls described in your proposal get executed, if the vote passed. It takes each part of the proposal and executes them exactly how you specified it. Imagine it like this. You have a built a protocol called MyAwesomeDapp that lends out Ethereum to people at a fixed interest rate. This interest rate is a variable set in the contract, but can be changed by calling the function ``change_interest_rate(int new_interest_rate)``. This takes an input parameter of whatever you want the new interest rate to be. You also have a governance contract that is at address ``0x5a``. When you create your protocol contract, you say that the owner is the address ``0x5a``, I.E the governance contract, and that its functions can only be invoked by it. Someone submits a proposal to increase the interest rate to ``5%`` from ``4%``. That proposal includes the parameters *call change_interest_rate() with value 5% on the specified protocol contract*. If the proposal passes, then those function calls will be executed. It also does things like logging and archiving of all proposals and executions.

Governance Tokens
---------------------

  Instead of locking up Ether, protocols will often issue *governance tokens*. This is an *erc-20* token, which you must deposit first in order to vote, which is done by send it to a governance contract. When this is used, applications typically do an *airdrop* before opening up the system for proposals. This is where they mint an arbitrary amount and distribute them to members of the community so that there is enough circulation to get voting going. Platforms have typically distributed those to *"early-adopters"*, people who used the platform before the token release. For example, prior to Uniswap's token release, if you had ever used the protocol at any point, you were given **400 Uni tokens** for free. Other protocols, like Tornado-Cash, allocated tokens based on how much you had used, with heavier users of the app receiving a larger stake.

  These tokens are `fully-tradeable <https://coinmarketcap.com/currencies/uniswap/>`_ on the open market and their price is derived from the importance of being able to vote on the underlying protocols. Just like everything else it's the intersection of supply and demand. For example, `Maker <https://coinmarketcap.com/currencies/maker/>`_, the governance token for the `Dai stablecoin <https://coinmarketcap.com/currencies/multi-collateral-dai/>`_, is very expensive. It costs more than Ether does. This is because the supply is much lower, and it's a very important `DAO <https://makerdao.com/en>`_ that people want to be a part of.

This flow chart describes the process at a very high-level. It skips a few steps for simplicity purposes.

.. image:: images/daos/dao_flowchart.png

Why you should use it
----------------------

Why should you use a DAO:
  #. Trust - Giving up your authority to the community is a good way to gain the trust of the cryptocurrency community. With transparency and delegation, people will be more likely to use your app because they know that it can be trusted, and that you have faith in it. It is also a great way to show that you are optimistic about the long term viability of the project and its ability to stand on its own
  #. Funding - Selling off tokens for governance can be a good way to raise capital in an ICO. Many projects do this instead of airdrops.
  #. New perspectives and ideas - Sometimes the power of the group can be greater than the individual. Give people the power to find and change things on their own and they may surprise you. It also helps to eliminate overhead and costs. Banks have huge departments of people who's only job is to figure out things like interest rates and costs. By offloading this responsibility to the community, people will do this job for you to make the optimal amount of money and productivity. Security is always a risk, but that risk never goes away. When people have skin in the game, they are more incentivized to do the right thing and help it rather than attack it. Dai is incredibly stable because of arbitragers and the devoted members of the MakerDAO.

Use Cases
----------

There are hundreds, even thousands of possible use cases for DAO governance. Here's some of my favorite examples

Grants
  The Gitcoin DAO is an organization responsible for funding new and upcoming projects that are important to the ethereum ecosystem. People submit proposals for funding to build their application and DAO voting is used to determine to whom the funds should go to.

Venture Capital:
  Same logic as grants but for venture capital investment funds. Let people pool money and vote on how it should be invested.

Charity:
  The same logic as grants, but with charity. Anyone can donate and make a proposal to how the funds should be spent. Full transparency and democratization.

Investment Trading:
  Create a decentralized hedge fund that constantly trades coins on-chain based on member votes. Or you could vote to appoint someone as the trader on behalf of the group, and kick them out if they don't perform.

DeFi and other Dapps:
  DAO's like Maker, Compound, Aave, etc. use their DAO to dictate changes to the protocol like collateralization rates, interest rates, new lending pairs, etc.

Businesses and Freelancers:
  Allow people to pool their funds together to pay for goods and services without having to trust someone as a custodian.

Voting and Authorization:
  The distributed voting system allows for the democratization of really anything: Elections, board-approval, polling, etc. Obviously this technology is new and it will be a long time before it's used for any serious real-world systems, but it holds a lot of potential in what it can be used for.
