---
title: "How to calculate available staking capacity for a Tezos baker"
description: "Analytical resources show different values. Find out yourself!"
date: 2019-09-12
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/MQA20ru.jpg'
layout: Post
category:
  - tezos
authors:
  - AlexBond
company:
 - p2p
---

Tezos ecosystem combined a variety of solid tools to monitor network performance and staking rewards. Block explorers represent a major part of the ecosystem health. Delegators and bakers often rely on such tools if looking for a data or before making a decision like, which baker to stake with. Diversity of these services provide users with unique design and allows to choose one that corresponds to a particular need. Some parameters are not unique and various analytical explorers display identical network variables. 

In some cases it may lead to a confusion when the same variable displayed with different values on multiple resources(explorers, services). It can be because of different frequencies of the network data updates (API/RPC calls) or different timeframes taken for calculation. Currently, such an important parameter as available staking capacity. It represent an amount of XTZ that can be staked with a particular baker without making him over-delegated. Delegated tokens above the limit will not contribute to the power of the baker. Currently this parameter implies significant differences on various analytical sources.

# Security deposit

In order to create blocks baker should maintain a specific amount of self-bond that is used for security deposit required by the Tezos protocol and subject to slashing as a measure against misbehavior. Security deposit per created block is equal `512 XTZ` and per endorsement is equal `64 XTZ`. When validator bakes block or endorses these funds become frozen for a number of preserved cycles defined by the protocol and unfreeze after. 

If we assume that 100% of total supply participate in staking we can calculate the minimum bond requirement for a baker: `((block_security_depo + endorsement_security_depo * endorsers_per_block) * blocks_per_cycle * (preserved_cycles+1)) / total_supply`

Let's split this formula into parts:

Part 1: `block_security_depo + endorsement_security_depo * endorsers_per_block`

In this part we calculate the total amount of security deposit per block.

Part 2: `blocks_per_cycle * (preserved_cycles+1)`

By multiplying the total security deposit per block on(with) the number of blocks in the cycle and frozen period plus one we get the total amount of XTZ that are frozen for preserved cycles.

Part 3: `Part 1 * Part 2 / total_supply`

Here we finally calculate the security deposit share of the total supply.

Let's crunch some numbers:

`block_security_depo = 512 XTZ
endorsement_security_depo = 64 XTZ
endorsers_per_block = 32
blocks_per_cycle = 4096
preserved_cycles = 5`

All these parameters derived from a Tezos protocol and represent constant values until community decides to propose changes via governance procedure. The only dynamic parameter is `total_supply` that at the day of writing is equal *~ 814,31 million XTZ*. The actual self-bond requirement is floating as baking frequency and endorsement rights are changing but for this case we will not take possible baking deviations into consideration as they are relatively small.

The whole calculation of minimum self-bond requirement *if 100% tokens at stake* look like: `((512 + 64 * 32) * 4096 * (5+1)) / 814 310 000 = 7,73%`. 

With a decrease of total supply percentage at stake, minimum self-bond requirement will increase as overall share of frozen XTZ in a security deposit related to the participating tokens will be higher. 

To calculate the exact self-bond requirement we can simply put the exact number of tokens at stake instead of `total_supply` or divide the result of previous calculation made for 100% staked tokens by the actual percentage of staked XTZ. It will result in **~10,5%** of *actual self-bond requirement* for a baker. 

The only caveat here is that total supply is growing over time while security deposits remain the same. In the long run it will result in extremely low self-bond requirement as well as the network security.

# Available staking capacity

After finding the exact self-bond requirement we can answer two questions:

1) Does a particular baker maintain sufficient self-bond?

2) How many stake a particular baker can accept before it become over-delegated?

To answer the first question we should find a self-bond share in the total staking balance. 

`staking_balance = self_bond + delegated_balance`
`self_bond / staking_balance * 100 = X%`. 

If `X > actual_self_bond_req` then baker have enough self-bond and won't miss baking or endorsement slots. 

The answer to the second question is available staking capacity. To find this value we should substract staking balance from the maximum balance.

`max_balance = self_bond / actual_self_bond_req`
`available_staking_capacity = max_balance - staking_balance`

Now you have all the necessary information to check by yourself if the self-bond of a baker is sufficient enough to bake and what is available staking capacity of a validator.

------

*Providing a secure staking experience is one of our core priorities. *If you have any questions feel free to contact our team. We are always open for communication.*

------
**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake your XTZ with us:** [p2p.org/tezos](p2p.org/tezos)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)