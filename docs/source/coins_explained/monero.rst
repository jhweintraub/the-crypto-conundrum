Monero (XMR)
==============

Ever since the `Colonial-Pipeline Hacking <https://en.wikipedia.org/wiki/Colonial_Pipeline_cyber_attack>`_, the media has seemed to fixate not on `Colonial Pipeline's obscene disregard for security <https://www.ajc.com/news/nation-world/lawsuit-alleges-colonial-pipeline-was-negligent-in-recent-cyberattack/TTMEMLRXKZFGLBBZZIT4T4XNC4/>`_, but rather on how `Bitcoin enabled the attackers <https://markets.businessinsider.com/currencies/news/bitcoin-anonymous-untraceable-myths-stupid-dirty-money-laundering-crypto-chief-2021-6-1030517840>`_, how it's `"not truly anonymous" <https://marker.medium.com/colonial-pipelines-ransomware-recovery-reveals-bitcoin-is-not-truly-anonymous-6dfca3b320c9>`_, and a lot of other rubbish. Well, those people are about to get a lot more scared, because to an extent, they are correct. Bitcoin is not truly anonymous; It is pseudo-anonymous. This creates a lot of problems for your privacy, arguably the single-most important feature of using crypto.

But luckily, there is a solution.

.. image:: images/monero/xmrbg.jpg

Privacy vs. Anonymity
----------------------

Bitcoin is not anonymous, but it is private. It's like cash, where the only people who know the transaction is occurring is you and the recipient. It's not totally anonymous, as your transactions are public, but the contents and people involved is private. When you go to a website with encryption (https), your interactions are private. Observers can sometimes see that you're interacting with someone, but they can't see what you're saying.

.. image:: images/monero/nsa_meme.jpg

\*NSA Headquarters^

The blockchain is very transparent. This both its greatest asset, and one of its greatest flaws. Its addresses are public. When you make a `transaction <https://www.blockchain.com/btc/tx/9b7170c7517625a39d76df3de60029fabecc803a5778d39d40691a309a8991d8>`_, all of the information regarding it is stored forever, for anyone to see. This can be very useful, in things like supply-chain management, auditing, proof-or-purchase, etc. However, this also creates the issue of identification.

If you've ever spent time on reddit, you may notice that people tend to get called out for lying in multiple posts. This is because Reddit has post-histories. Everything you said gets logged to your account. Sometimes people get doxxed, because people on the internet with too much time on their hands will piece-together their history with a real-world identity. The same concept applies to most cryptocurrencies. When you send money from Coinbase to your wallet, Coinbase keeps that transaction record. They keep a list of who you send to. Using information like timestamps, known-addresses, amounts, and associates, a wallet address can be linked back to you.

There are `companies whose entire business model <https://www.coindesk.com/digital-mercenaries-blockchain-analytics-privacy-advocates>`_ is working with governments to tie-you to your wallets: `Chainalysis <https://www.chainalysis.com/>`_, `ciphertrace <https://www.google.com/search?q=ciphertrace&oq=ciphertrace&aqs=chrome..69i57.1227j0j1&sourceid=chrome&ie=UTF-8>`_, `Elliptic <https://www.elliptic.co/>`_, etc.

The US government spends `millions of dollars <https://www.coindesk.com/inside-chainalysis-multimillion-dollar-relationship-with-the-us-government>`_ specifically on this problem. It's not endemic to Bitcoin. Nearly ALL cryptocurrencies have this same issue, that comes from the desire for transparency. Whether you're using Bitcoin, Ethereum, or even Dogecoin, you are at risk.

Cryptocurrency was created with the aim of being digital cash. If it doesn't have anonymity, it's no better than a credit card in some respects. Luckily, there is a better way: Monero.

Monero is THE privacy-coin. When you use Monero, everything important is obscured from the outside. Money is changing hands, but outsiders don't know what or who is involved. In a Monero transaction the sender (your address), the amount, and the recipient, and the  address are all obscured. An outside viewer would have no idea who was really interacting. Complete anonymity.

.. image:: images/monero/privacy_meme.jpg
  :width: 350px
.. image:: images/monero/privacy_meme.jpeg
  :width: 300px


**Why do I need to care about privacy?**

That's up to you. If you don't care about preserving your right to privacy then you're entitled to your opinion. I would attempt to convince you otherwise, but it's not worth it. For now let's just assume you do care.

**Aren't criminals the only ones who care about Cryptocurrency to be able to commit crime?**

They could. Nothing stopping them. But that fear is significantly overblown. Don't believe me? Here's an except from a `report from researchers RAND foundation to the Department of Defense <https://www.rand.org/content/dam/rand/pubs/research_reports/RR3000/RR3026/RAND_RR3026.pdf>`_ saying the opposite:

  **Current concerns about cryptocurrency as a significant enabler of terrorist groups are almost certainly overblown**, but coming improvements in cryptocurrency technologies will likely have a significant long-term effect on CTF [counter-terror financing]. The speed at which these technologies are adopted, and the details of which technologies are used and how they are deployed, are critical uncertainties that have important operational impacts. These operational challenges are partly extending current methods of CTF and partly adapting methods from computer security. Impending change from traditional financial methods to more sophisticated “fintech” (i.e., financial technology) will pose challenges, starting with the addition of new sources to monitor and investigate. **This does not necessarily require intentional use by terrorist organizations but simply can be a byproduct of banks changing their practices.** For example, the U.S. Treasury “has access to unique financial data about flows of funds within the international financial and commercial system,” which is invaluable for tracking illicit flows of money.... On the other hand, it is a field where sophistication matters; money laundering may be made harder to detect when conducted by sophisticated actors, but **many terrorist groups’ technical abilities are not currently suited to this type of activity.**

In fact, dollars bills are still the `main source for money laundering operations <https://www.newsbtc.com/analysis/it-is-the-us-dollar-not-bitcoin-that-is-mostly-used-in-money-laundering/>`_.

.. image:: images/monero/xmr_meme.jpg

Privacy functions
------------------

Monero relies primarily on obfuscation techniques to preserver your privacy. This means to prevent the data from being readable and understood by changing it or throwing in misc. data to jumble it up. All addresses are obfuscated.

It does this through three pieces of technology: Ring signatures, RingCT, and Stealth addresses. Bear with me here, this is conceptually difficult, even for me.

Ring signatures
****************

First, to hide the sender, it uses Ring Signatures. When you send a transaction, the cryptographic-signature, that says you sent funds, is combined with the signatures of other random past-transactions. They are used as dummies. When all of the data is put together, it is *impossible* to know which person was the real sender and which others were fake. The more data you include, the harder it becomes.

.. image:: images/monero/ring_signature.png

Image Source: `2019 IEEE International Conference on Advanced Trends in Information Theory (ATIT) <https://www.semanticscholar.org/paper/Using-Ring-Signatures-For-An-Anonymous-E-Voting-Kurbatov-Kravchenko/a2c5c700f3f06cfe6bc633b1fe73f7916bab3435>`_

RingCT
********
RingCT (Ring-Confidential-Transactions), which obscure the amount sent. This is done by creating a shared secret between the sender and the receiver. They use this to change the output value to something else publicly, but can be deduced and proven by the original transaction participants. Think of it like this. When you have a transaction, the input must be the same as the output. So the sender puts in ``10 XMR``, and the output is also ``10 XMR``.  ``1+2+3+4 = 3+5+2``. But, if you multiply the values by some constant like ``5``, you would get a different number. ``5*(1+2+3+4) = 5(3+5+2)``. If you looked at the transaction all you would see is ``50 = 50``, but we don't know what the original input was or the constant, and there's a lot of ways to factor ``50``. This problems gets very difficult for computers when the numbers get bigger.

.. image:: images/monero/ringCT.png

Image source: `Exantech <https://blog.goodaudience.com/monero-confidential-transactions-or-send-i-know-not-what-to-someone-i-know-not-whither-337f20f0d64e?gi=b79aa72ebbba>`_

Stealth Adresses
******************
When you have a Bitcoin transaction, you have **one** address. This address is derived from a singular encryption key. You give this address to anyone, and anyone can send you funds there. It never changes. When you use Monero, the address is obfuscated, so it **looks** like it's going to a different address every time. For Monero, you still have one address, but when you have a transaction, you're really using it to generate a *1-time-only* obscured address. The person sending knows it's you, but to observers it looks like a different address every time. This address is procedurally generated on every transaction to be different, but can always be linked back to your original address, but **only** if you have the original encryption keys. You could send 5 transactions to the same person, but if you tried to look at the blockchain it would look like you're transacting with 5-different people.

When you use Monero, you are actually creating two-keys, one for spending (spend-key) and for receiving (view-key). You need the view key to identify your incoming transactions, and the spend-key to send them back out. These are handled by the same wallet. But, you still have only one address. The address is derived from both of them together.

When you want to form a transaction, a sender uses your public spend-key, public view-key (taken from your address), and some other info to create a *one-time address*. You need the secret view-key to be able to recognize incoming transaction. Basically, the sender takes the one-time address and sends it out to the network. The receiver listens to all of the new transactions, checking every one against their secret view-key, until they find one that's theirs. You have created a secret between the sender and receiver of you that is verifiable to everyone, but still obscured. When you want to send the transaction, you then take the secret view-key and secret spend-keys to prove your ownership and form a new transaction. If someone stole your private view-key, all they would be able to do is view your funds. They would need the private spend-key to be able to spend it. If they had just the private spend-key, they could spend, but they wouldn't know how much or where from.

I could write my address on the side of a bus, but if you tried to look at it on a blockchain explorer, you wouldn't see anything.

.. image:: images/monero/stealth_address.png

Source: `Delfr.com <https://delfr.com/bitcoin/stealth-address-moneros-part-10/>`_

Ring Signatures hides the sender, RingCT protects the amount, and Stealth addresses hide the recipient.

**This all sounds very complicated. If I have two keys, do I need to remember two seed phrases? and do I need to run a node to listen to all the transactions?**

It is complicated, but you can rest assured it is safe and works. People smarter than you and I are working on this day and night to keep making it better. As for how to actually use it, it's exactly the same as any other cryptocurrency. One mnemonic seed phrase can generate all the keys. When you want to send a transaction, just give the sender your public address, and the wallet does the rest.

And no, you don't need to run a full node. Your phone can get all the info it needs from the blocks on the chain at the point that you need it. Our technology has gotten very good at doing this kind of download and decryption/verification very quickly.

Consensus, scaling, and tokenomics
------------------------------------

Monero is based on proof of work, just like Bitcoin. However, it does have at least some solutions towards scalability. The size of Monero blocks is flexible, and can accommodate as many transactions as demand changes. Formulas determine how the reward miners receive interacts with the number of transactions they choose to include in blocks.

While it still works on the auction-model to determine block inclusion, dynamic sizing and `new encryption upgrades <https://www.coindesk.com/monero-to-become-first-billion-dollar-crypto-to-implement-bulletproofs-tech>`_ have kept transaction fees `obscenely low <https://www.coindesk.com/monero-fees-fall-to-almost-zero-after-bulletproofs-upgrade>`_.

Centralization is always an issue with PoW systems, but the community has taken this issue very seriously. A few years ago they went through an upgrade of their encryption algorithm known as `RandomX <https://academy.bit2me.com/en/which-mining-algorithm-randomx-monero/>`_, meant to make mining more resistant to specialized ASIC chips. The community is also very vigilant of `centralization in pools <https://bitcoinist.com/does-monero-have-a-serious-centralized-mining-problem/>`_, to try and discourage people from causing too many issues.

Monero does **NOT** allow smart contracts, but it may not need them.

It has a current circulating supply of ``17.9 Million``, and a max supply of ``18.4 Million``

The Future of Monero
-----------------------

This is the section where I might normally say something like "Based on these factors I think the price will go to X". I will do some of that but before I do, I think it's more important to discuss what the future for Monero may actually be.

Monero is not an Eth-Killer. It does not have smart contracts, but it doesn't need to. It doesn't compete with any of those platforms (Ether, Cardano, Solana, etc.). Monero focuses on doing its one thing really well, privacy. Aside from ZCash, which is nowhere near being a major competitor, Monero occupies a much more niche market, with a devoted fanbase and substantial growth potential. As i've said before, the crypto-world of the future is one of multi-chains: multiple chains working in parallel with users utilizing multiple ones. When you want DeFi, you use ethereum, but when you want privacy people will use Monero. It's privacy features are only going to become more relevant and important in our increasingly digitized world.

**Is the government going to ban it?**

I'd bet any amount of money the answer is no. They can't, even if they tried. How would they do it? Go around and arrest people for owning crypto? Impossible, especially on Monero where there's no way to know who owns what. Politicians, regulators, and news outlets like to posture and sensationalize Monero and its anonymity, but when push comes to shove they aren't going to do anything about it?

**Is it anonymous? I read an article that says Chainalysis and Ciphertrace have cracked it?**

It's possible. We really don't know.

Ciphertrace has `claimed to be able to track it <https://ciphertrace.com/ciphertrace-files-two-monero-cryptocurrency-tracing-patents/>`_, and there has been research indicating it `has problems <https://www.wired.com/story/monero-privacy/>`_, so I won't say its perfect. However, it is better than nothing and encryption tech gets better all the time.

Encryption and privacy is a cat and mouse game. As long as there's been encryption, there's been people trying to skirt it and peek inside. Luckily, the Monero community is constantly working to upgrade and improve its features. They've gone through updates in the past and new research is coming out everyday on ways to make it better.

There's also a lot of things you can do as well to make it even more private: sending transactions with multiple wallets, using VPN's or onion routing like TOR, being private with who you tell about your transactions, etc.

**It uses Proof-of-work, isn't that bad cause Bitcoin uses it?**

Yea kinda. It definitely uses a lot of energy, BUT the community is working on things like making is more resistant to centralized mining. It's energy usage is nowhere comparable to that of Bitcoin, and the rise of renewable energy makes it something I don't think is to be worried about. If you're worried about how that affects scalability, then see above where I talked about dynamic block sizing. It's not an ideal solution that maximizes decentralization, but it's better than nothing and with privacy features of Monero, I think it's a trade-off worth making.

Price Predictions
*******************

**Jeez ok, we get it. Can you tell us now what you think the price is gonna go to?**

Fine. But before I say anything, I have to repeat the official motto of this website: **I am not a Financial Advisor. Nothing said here is financial advice. I am not liable for any losses you may incur while investing. Investing in Cryptocurrency is a financial risk, and you should do your own research prior to any purchases.**

I think the price of Monero will go to *AT LEAST* **>$2,500** *within the next 5-years*.

At it's current price of **$268.52** it's market cap is *ONLY* **$4.81 Billion**. Keep in mind this is with a circulating supply of *17.9 Million*, ``~97.8%`` of hard-cap max supply. This eliminates any fears of inflation.

A price of ``$2,500`` each would mean a market cap of *~48 Billion*, *~10x* what it is currently. Now, 10x growth is a tall order, but I do think it is reasonable given the timeframe. Look at the following chart of Monero over its existence.

.. image:: images/monero/chart.png

Notice how the date I pointed out was almost exactly 5-years ago from the date this article is posted (6/21/2021). It was *$1.5578*. That is a **17,001.9% growth in price** over the last 5-years. Now I want you to think about how popular Monero actually is currently. Walk up to anyone on the street and ``>95%`` of the time nobody will have heard of it. The only current exposure people have is sensationalized news headlines exacerbated by recent ransomware attacks. But as cryptocurrency grows in popularity, so will it. Once someone starts with Dogecoin, or Ethereum, or Bitcoin they tend to move towards other coins and grow their holdings and usages. The price grows alongside it. Look at this other chart of transactions-per-day over the same period.

.. image:: images/monero/tx_day.png

*Image Source: BitinfoCharts*

From *412 transactions/day* to *14,300 transactions/day*, a **3370.87% increase**. Now imagine where it could be 5-10 years from now, as public awareness grows, as apps get easier to use, as more people start to care about online privacy. It's a very realistic growth potential.

Still think that *$48 Billion* is too high? Well keep in mind, that at its all-time-high of ``$0.73``, dogecoin had a market cap of **~$88.6 Billion**, almost double what i'm predicting. If a damn meme can get there then its not unreasonable to think the top privacy-coin in the market can too.

.. raw:: html

  <div class="nomics-ticker-widget" data-name="Monero" data-base="XMR" data-quote="USD"></div><script src="https://widget.nomics.com/embed.js"></script>
