# Rewards

## Overview

To ensure players hold the vast majority of SIGMA2 tokens, 90% of the initial supply of SIGMA2 will be given away to players in the form of awards. These tokens are locked in rewards contracts, from which players can claim rewards they are entitled to. The per block emission rate is set such that all rewards will be given out over the course of one year from the launch.  The amount of rewards a player receives depends on their largest loss within a given rewards round. The details of this are explained below in the next section.

There are three different rewards contracts, one for each token players can place bets in. 50% of the rewards will be allocated for players betting in SIGMA2, 25% for players betting in MATIC, and 25% for players betting in USDC. This is to slightly encourage the use of SIGMA2 for betting over other tokens.  The 9,000,000 SIGMA2 allocated for rewards is split between these three rewards contracts as such.

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
| Polygon mainnet address:          | [0xaab34069ef41BcD10645FE0eeDbbD1416bDF8c91](https://polygonscan.com/address/0xaab34069ef41BcD10645FE0eeDbbD1416bDF8c91) |
| Emission rate:                    | 0.285352 SIGMA2 per block |
| Min round length:                 | 43200 blocks (~ 1 day) |
| Polygon testnet (Mumbai) address: | [0x51985A6b404Fae2B520fE4C455d65670ac0Ed035](https://mumbai.polygonscan.com/address/0x51985A6b404Fae2B520fE4C455d65670ac0Ed035) |

**MATIC Games Rewards Contract:** TODO

|                                   |   |
| --------------------------------- | - |
| Polygon mainnet address:          | [0x0D5B50B1557eE651eA5a0e342b06866F87b02388](https://polygonscan.com/address/0x0D5B50B1557eE651eA5a0e342b06866F87b02388) |
| Emission rate:                    | 0.142676 SIGMA2 per block |
| Min round length:                 | 43200 blocks (~ 1 day) |
| Polygon testnet (Mumbai) address: | [0x2A06486D2591Cb0eB370d5bC2E1Fa73A1D07dA3f](https://mumbai.polygonscan.com/address/0x2A06486D2591Cb0eB370d5bC2E1Fa73A1D07dA3f) |

**USDC Games Rewards Contract:** TODO

|                                   |   |
| --------------------------------- | - |
| Polygon mainnet address:          | [0x460b7916e5921Eb527570FbA22B4797BB677240F](https://polygonscan.com/address/0x460b7916e5921Eb527570FbA22B4797BB677240F) |
| Emission rate:                    | 0.142676 SIGMA2 per block |
| Min round length:                 | 43200 blocks (~ 1 day) |
| Polygon testnet (Mumbai) address: | [0xDD3f82f7a5Fc90dcC575E46275E8380589DaAfE5](https://mumbai.polygonscan.com/address/0xDD3f82f7a5Fc90dcC575E46275E8380589DaAfE5) |
