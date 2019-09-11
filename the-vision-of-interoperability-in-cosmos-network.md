---
title: "The vision of interoperability in Cosmos network"
description: "This post is a brief intro to Cosmos vision"
date: 2019-09-11
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: ''
layout: Post
category:
  - cosmos
authors:
  - AlexBond
company:
 - p2p
---

That's not a secret that blockchains have troubles with intercommunication and ability to understand each other. Various blockchains serve various purposes and may not be suitable for some uses and different projects may not be subjected to the same vision of a single ecosystem. Such isolation is locking their potential to utilize features of each other and achieve synergetic effect that may bring a new wave of development in crypto space. Interoperability barriers exists not only in the blockchain space.

# Real world analogy

Imagine a world where people living across continents can talk to each other without linguistic limitations. Humans would be able to communicate with maximum efficiency. Multinational teams would be able to interoperate and efficiently achieve common goals. There are two possible scenarios that make it theoretically possible.

The first one presumes the existence of a single global language adopted by everyone. In this case there are huge difficulties. National cultures across the continents are very different, generations have created their own traditions and beliefs over the centuries. Local languages influence the thinking of each individual. The existence of a single language means blurring the borders between nations and currently seems unrealistic.

Another way of thinking about it is to have a technology or device that automatically translates and transforms speech and allows people speaking different languages to understand each other without the need to learn another tongue. With this idea, for example,  anyone could speak English in China and be understood. The first steps in this area have been taken by Google and their[ Translatotron](https://ai.googleblog.com/2019/05/introducing-translatotron-end-to-end.html) can serve as a starting point for a model that can translate speech from one language directly into another.

# **The vision of interoperable ecosystem for blockchains**

Functioning in a single ecosystem may cause significant limitations in sovereignty, development and many other aspects eliminating their individuality (or individualities or specialty or specialties). In the blockchain space already exists a technology that will allow different blockchains to interoperate and avoid these difficulties.  

Cosmos ecosystem is a "place" where all networks are connected to each other through a set of inter-chain standards (ICS). Communication is carried via inter-blockchain communication protocol (IBC) that requires specific modules that run on independent machines. Special blockchains called hubs play a role of translators in the Cosmos ecosystem and make it possible for application-specific blockchains called Zones to communicate indirectly by connecting to the hubs and perform state transfer including tokens, ID metadata or even validator's set via IBC.

Construction of such application-specific blockchains from scratch is possible in a plug-and-play manner. Cosmos SDK provides a framework for simplification of the development process and makes it much more flexible. It is possible to choose from default modules that together define the actual state machine and customize sovereignty level. Each blockchain may have its own set of rules, validators and governance procedure to experiment with various incentive models without the need to conflict with a single set of governance rules. 

To bridge blockchains that built without use of Cosmos SDK and don't have instant finality (if block with your transaction is committed it will not be canceled and transaction may be considered valid) specific blockchains called Peg Zones come in place (game). Peg Zone is a Proof-Of-Stake blockchain that have instant finality. It is compatible with IBC and constructed specifically (for purpose) to track and mirror the state of a bridging blockchain. 

To sum up, Cosmos ecosystem is formed by three types of blockchains:

* Zones - blockchains already built with interoperability in mind using Cosmos SDK
* Hubs - blockchains that indirectly connect zones via IBC
* Peg Zones - blockchains that mirror blockchains outside of the Cosmos ecosystem and not compatible with IBC 

Freedom is a key to innovation. Innovation is a key to a breakthrough. Cosmos ecosystem may evolve in a natural magnitude as every project within the network is not tied up with a single set of governance rules and performance limitations. It creates a healthy environment for developers and entrepreneurs who are seeking new ways of making value transactions to end-users and offers better means of cooperation by utilizing features of the whole set of projects in the ecosystem.

------

*In the next chapters we will discuss the first hub in the Cosmos ecosystem - Cosmos Hub. We will cover governance, staking benefits, existing risks associated with staking and other important topics.*

------

**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake ATOM with us:** https://p2p.org/cosmos

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)