---
title: "Transparency in blockchains for ordinary(non-advanced) users??"
description: "Introductory post about Oasis protocol"
date: 2020-02-17
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/EkipJ5c.jpg'
layout: Post
category:
  - staking, cosmos, kava, regen, terra, economy, iris
authors:
  - AlexBond
company:
 - p2p
---

With blockchains all operations within particular network are recording in immutable ledger without ability to corrupt the state of finalized transactions by a single party. As every transaction is recorded it can be easily retrieved for analytical or other purposes. With such transparency everyone can get trusted record of any event since the start of the network.

### Transparency for users (подумать над заголовком раздела)

But is it really an easy task for someone without deep knowledge in code and various API endpoints to get all the data they need? You may argue that there are multiple explorers built for these purpose but each of them focus on various use cases (purposes) and don't give a complete picture of all events happening in particular network. For an ordinary user like me explorers act as a window in this magic world of blockchains and **transparency (our understanding) of this world is limited by the events various tools decide to display**. 

Blockchains are still new and complex for understanding. It is aggravating by increasing number of projects with different logic and various triggers. Transparency especially matters for financial transfers and events that can be potentially taxed (used for accounting purposes), for example in Proof-Of-Stake blockchains it can be a withdrawal of accumulated rewards.

Wide range (diversity) of high-quality explorers is significant for building user commitment to the network and facilitating trust. More tools do not always result in better visibility. Some explorers focus more on usability, which is also very important but still does not conductive(contribute?) to increasing transparency for (clarity/knowledge of) users of the network.

### Unobvious transactions in Tendermint based blockchains

Let's take a look at the process of reward withdrawal process. Surplus accumulates in a validator pool and can be withdrawn to the corresponding staking address manually. Basically, delegator withdraw rewards at any point of time to receive them on address. Explorers show this operation with name `GetReward` or `Withdraw Reward`. In fact that's not the only action that triggers reward withdrawal.

#### Example

Let's take a random account and check the information about his balance on [Mintscan](https://www.mintscan.io/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8) block explorer.

![account](https://imgur.com/2S17BBl.jpg)

If we calculate total balances using this transaction data we should get:

- Received: *144,17 ATOM*
- Delegated: *134 ATOM*
- Available: *10,16 ATOM*

And here are values from [Mintscan](https://www.mintscan.io/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8):

![40muatom](https://imgur.com/1bJpW95.jpg)

We see additional 40 muATOM, but where did they come from if there was no withdraw transaction made by this address? Of course you may say it's just 40 muATOM who cares? But systems based on a code should not allow any mistake. So, is displayed balance correct or there is some mistake? Let's get into.

In fact there are hidden messages(transactions) that trigger reward withdrawal but not displayed on most explorers simply because they serve another purpose and these slight(minimal) changes do not correspond much to the observation of what is happening in general.

There are five core types of actions delegators usually perform:

- Delegate to a validator
- Redelegate to another validator
- Undelegate from a validator
- Withdraw accumulated rewards
- Send available tokens to another address

First four of them initiate reward withdrawal, and first three of them usually are not displayed by most explorers. 

In some cases to apply updates of the network validators stop producing blocks and upgrade node software. This process requires transition to a new chain with new genesis file that consist of(stores) the actual state on the moment of chain halt. When the new chain becomes active what happens with accumulated rewards?

These rewards also become available, transition to the new chain triggers withdrawal but this transactions are also hidden and not obvious for delegators. 

### Final thoughts

Every public network needs a variety of analytical tools to allow people without advanced technical skills to get information of what is going from different angles. In Proof-Of-Stake blockchains clear reward history and accessibility of historical data are especially important. 

More explorers doesn't guarantee high diversity of data but still contribute to increasing of user confidence and show different aspects of a particular network. Higher number of explorers can increase transparency. Every message or event can be important if it clarifies some valuable logics of the system.

Thinking of that, we decided to conduct technical research to make all rewards along with corresponding messages accessible and transparent across all versions of Cosmos Hub as a starting point.

------

*Want to stake with us? Alexey will be happy to help. Contact* *am@p2p.org* *to get personal assistance.*

------

**P2P Validator** provides secure non-custodial staking. Subscribe to our channels and stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)