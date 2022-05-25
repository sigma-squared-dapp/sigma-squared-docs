# Rewards

## Overview

To ensure players hold the vast majority of SIGMA2 tokens, 85% of the initial supply of SIGMA2 will be given away to players in the form of awards. These tokens are locked in reward contracts, from which players can claim rewards they are entitled to. The amount of rewards a player receives depends on their largest loss within a given rewards round. The details of this are explained below in the next section.

There are three different rewards contracts, one for each token players can place bets in. 50% of the rewards will be allocated for players betting in SIGMA2, 25% for players betting in MATIC, and 25% for players betting in USDC. This is to slightly encourage the use of SIGMA2 for betting over other tokens.

![Rewards Allocation](<assets/Rewards Allocation.png>)

Rewards are given out in discrete rounds. A round has a minimum number of blocks, and after that time has passed, can be ended at any time. At the end of each round a set amount of tokens, based on the per block emission rate, are given out to all users who placed a bet in that round and lost. The rewards are weighted based on each player’s largest loss in the round. The larger a player’s loss, the more of the rewards they will receive for that round.

Below is an example for clarity.

For a given round each player’s losses are as follows.

| Player   | Largest Loss |
| -------- | ------------ |
| Player 1 | 100 SIGMA2   |
| Player 2 | 10 SIGMA2    |
| Player 3 | 20 SIGMA2    |

In this round, Player 1 will receive 100 / 130 = 76.923% of the rewards, Player 2 will receive 10 / 130 = 7.682% of the rewards, and Player 3 will receive 20 / 130 = 15.384% of the rewards. The number of bets, volume, or any wins do not matter. Only the largest loss in a given round matters.

This mechanism is intended to reward users who place large bets more. Rewards are prorated based on largest loss, rather than largest bet, to reduce variance for players who have lost a large amount.

There is a separate rewards contract for each token players can place bets with. And the rewards mechanism is completely separate for each.

## Contracts

**SIGMA2 Games Rewards Contract:** TODO

|                                   |   |
| --------------------------------- | - |
| Polygon mainnet address:          |   |
| Emission rate:                    |   |
| Min round length:                 |   |
| Polygon testnet (Mumbai) address: |   |

**MATIC Games Rewards Contract:** TODO

|                                   |   |
| --------------------------------- | - |
| Polygon mainnet address:          |   |
| Emission rate:                    |   |
| Min round length:                 |   |
| Polygon testnet (Mumbai) address: |   |

**USDC Games Rewards Contract:** TODO

|                                   |   |
| --------------------------------- | - |
| Polygon mainnet address:          |   |
| Emission rate:                    |   |
| Min round length:                 |   |
| Polygon testnet (Mumbai) address: |   |
