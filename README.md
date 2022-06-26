# Whitepaper v1

## Introduction

Sigma Squared is an open-source, decentralized gambling protocol, built on top of the Polygon blockchain. It was created with the goal of providing a truly decentralized gambling solution, where the players are the house. Randomness and fairness in games is ensured using Chainlink’s verifiable random functions.

The game smart contracts and house treasury are owned by a DAO, which in turn is controlled using voting interests in the form of an ERC20 token called Sigma Squared (SIGMA2). Players can place bets denominated in SIGMA2 for 0% house edge, enabling actuarially fair gambling. This is not something players can obtain elsewhere at the time of writing, as far as the writers are aware. Users can also place bets denominated in MATIC and USDC for a small house edge, which is set by the community/DAO. In the future, the community can choose to deploy game contracts for other tokens. Any contract balances that arise as the result of this house edge are completely owned and controlled by the DAO. The community may vote to distribute game contract balances in the future in the form of dividends or a buyback, for example.

To ensure the DAO, and in turn the game contracts / house are actually controlled by players, 90% of the initial circulating supply of Sigma Squared tokens will be given away to players in the form of rewards. This will happen over the first year of Sigma Squared’s existence. A certain number of tokens are distributed to players per block, prorated based on each player’s largest loss in a rewards round. This encourages use of the game contracts, and helps reduce variance, since the largest losers are rewarded more. A more detailed explanation can be found in the [Rewards](rewards.md) section of the documentation.

## Background

The advent of blockchains that support Smart Contract capabilities and verifiable random functions that ensure truly fair randomness, have made it possible to create a decentralized gambling protocol. Games can be completely decentralized and have their randomness ensured with VRFs.

This flips the normal power dynamics of gambling on their head. Instead of a centralized house maintaining the games and collecting all the profits, players can own and control the house themselves. A protocol can be designed where any overall house profit can stay within the player community. This empowers players by reducing the cost of gambling. In addition, if the protocol controls its own token, bets with zero expected value can be offered if denominated in this token.

## Previous Work

There have been a few attempts at creating a decentralized gambling protocol similar to one outlined in previous sections of this paper. In this section, two of the largest will be examined.

Polyroll was one of the first projects that attempted to provide a decentralized gambling solution. The creators claimed the project was open source and decentralized. In reality that was far from the truth. Game contracts were deployed and owned by a single Polygon wallet, giving it access to all the funds in all game contracts. The project claimed that ROLL (the project’s token) holders were entitled to profits from the games’ house edge, however nothing actually guaranteed this because, as mentioned, a single wallet address owned all the game contracts. There was some distribution of house profit to ROLL token holders, however each time this happened, the developers took a large amount first. The project eventually ended with developers announcing they were completely abandoning the project and draining the game contracts of all funds.

Polyflip is another project aiming to provide a decentralized gambling solution. It consists of a set of game contracts and a set of NFTs. The games have some positive house edge, and the NFT holders are supposedly entitled to all proceeds from the games. However, upon inspecting the deployed smart contracts, it can be seen that there is a single wallet address that owns all the game contracts, giving the single wallet the power to withdraw funds at any point. Distribution to NFT holders will only happen if the developers manually choose to do so.

Both of these ‘decentralized’ gambling solutions have a single centralized house in reality (a single wallet address). There is no governance for either. Also, each game had some positive house edge, and there are no actuarially fair bets.

Sigma Squared was created to address these shortcomings. The goal is to provide a truly decentralized gambling solution, where game contracts are owned and controlled by a DAO, which is controlled by the community.

## Overview

The Sigma Squared ecosystem consists of four main components.

### Sigma Squared Token / DAO

The Sigma Squared token is at the center of the entire ecosystem. It is an ERC20 token and is used to govern a Decentralized Autonomous Organization (DAO). Holders can submit and/or vote on proposals. The DAO has its own treasury, which it can use to promote and grow the Sigma Squared community.

### Game Contracts

The game Smart Contracts are what users actually interact with to place bets. Initially, there will be two types of game contracts, described below. However, in the future developers can add other types, and release them by submitting proposals to the DAO.

One set of game contracts allows players to bet on a Bernoulli random variable. A bet can be placed by specifying an amount and a multiplier. The outcome will either be a win or a loss. As an example, consider a player that places a bet with an amount of 1 USDC, a multiplier of 3x, and the house edge is 0%. There is a 33.33% chance the player wins 3 USDC (+2 USDC), and a 66.66% they do not get back their original bet (-1 USDC). If there is a positive house edge it will change the probabilities accordingly.

The other set of game contracts allow players to enter a lottery. Any amount can be deposited into the lottery, and a single user wins the entire amount at the end. The probability of winning is weighted based on the amount deposited. There can be a house edge associated with the lottery; when a user deposits into the lottery, a percentage of that deposit is taken out of the lottery pool and held in the contract as profit.

All the games contracts are completely owned and controlled by the DAO. Parameters, such as house edge and risk parameters, are governed by the DAO. All profit derived from any games with positive house edge is completely owned by the DAO.

Any games denominated in SIGMA2 have 0% house edge. This allows users to gamble in an actuarially fair way, with zero expected value. Games denominated in other tokens will likely always have some positive house edge, although this is decided by the DAO.

### Rewards Contracts

In order to ensure the initial distribution is done in a fair way, a set of rewards contracts are deployed that give away 90% of the initial SIGMA2 supply to players. This way, players are involved in the community, are entitled to any profits, and can help shape the future of the ecosystem.

Rewards will be given out over the course of a year, at which point the rewards system will be decommissioned. Rewards are given out in rounds which last 43200 blocks (\~ 1 day with Polygon block times). A set amount of tokens are distributed every block. The rewards are prorated and allocated to players based on each player’s largest loss in a given round.

See the [Rewards](rewards.md) section in the documentation for more details.

### Front-end Interfaces

The previous three components all exist on the Polygon blockchain. Interacting directly with the Smart Contracts programmatically is something that requires technical knowledge and is likely not what users imagine when they envision gambling. A front-end web app enables interaction in a more user-friendly way.

The on-chain game contracts are basic building blocks for gambling games that only specify the payout distribution. Front-end web interfaces can build on top of these to provide a more engaging gaming experience. Betting on a Bernoulli random variable by specifying an amount and a multiplier alone may not be very exciting, however many more interesting games have this type of payout structure. For example flipping a coin, roulette games, poker hands flipping, and ‘crash’ style games all have a Bernoulli payout structure.

Initially, a single open-source front-end interface will exist for Sigma Squared with a few basic games. However one of the goals of community development is to expand on the game selection and experience available to users. Anyone with web development knowledge can build a gambling application using Sigma Squared as the back-end. To encourage this sort of development, 5% of the initial circulating supply of SIGMA2 was given to the DAO treasury, with the intention of distributing it, in the future, to developers who expand on the user experience by creating new games or improving on existing ones. For example, the DAO could hold competitions or commission new game creation using these tokens as payment / reward.

## Initial Token Distribution

A decentralized project can only really be as decentralized as its token distribution. Having only a few relatively large holders of Sigma Squared tokens would be completely against the philosophy of the project. To prevent this from happening, the distribution of tokens has to be as fair and diverse as possible.

There is no initial offering, or any centralized offering of tokens. Instead the initial circulating supply of Sigma Squared will be given out as described below.

#### **Total Circulating: 10,000,000 SIGMA2**

**Player Rewards: 9,000,000 (90%)**

* To ensure the vast majority of tokens are in the hands of players.

**DAO Treasury: 500,000 (5%)**

* To be used for future development, marketing, and community growth.

**Early developers, test users, and investors: 500,000 SIGMA2 (5%)**

* This is a reward for early developers, users, and investors. This ensures the people behind the vision hold a significant controlling stake in the DAO initially, to prevent any sort of hostile takeover or other action.

In addition to this circulating supply, 2,500,000 SIGMA2 was added to the Bernoulli game contract denominated in SIGMA2, to payout future bet winners.

#### **Total: 12,500,000 SIGMA2**

## Long-Term Token Supply

Because games are offered with 0% house edge when bets are denominated in SIGMA2, the SIGMA2 balance of these game contracts will drift over time in a random walk or martingale. The future expected contract balance will always be the same as its current value, however it is possible for the balance to drift significantly in one direction or the other over time.

To deal with this, the DAO has the power to mint and burn SIGMA2 tokens. If the SIGMA2 game contact balances become extremely low, the DAO will mint more SIGMA2 tokens to add to the game balances. If the game contract balances are outrageously high, the DAO will withdraw SIGMA2 tokens and burn them.

This means the circulating supply of SIGMA2 tokens will also be a random walk over time. The expected value of the circulating supply in the future is whatever the current circulating supply is, but it could still drift in one direction or the other. In other words, SIGMA2 is neither inflationary or deflationary in expectation, but could experience short-term inflation or deflation from random drift.

The profits from games denominated in other tokens, that have some positive house edge, could be used to buy back and burn SIGMA2 tokens, effectively making it deflationary in the long-run. However, the exact mechanism used to distribute house profit is left to the DAO to decide.

## SIGMA2 Intrinsic Value

The underlying utility of Sigma Squared tokens is derived from a few different sources described below. In a steady-state long-run equilibrium, the total market capitalization of SIGMA2 is a function of these.

### Number of players placing bets with positive house edge

SIGMA2 holders are entitled to all profit from game contracts with positive house edge. The more players that place bets with positive house edge (non-SIGMA2 games), the more valuable SIGMA2 becomes.

### Number of players placing bets with SIGMA2

Players may wish to place bets denominated in SIGMA2 so as not to give up any expected value (0% house edge). In order to bet with SIGMA2, players need to have some SIGMA2 wallet balance. The more players that need SIGMA2 the higher the demand for it is in the market, hence the higher the price.

### Desire to govern Sigma Squared ecosystem

SIGMA2 token holders control the DAO, which in turn controls the entire Sigma Squared ecosystem. The DAO sets the parameters for all game contracts, has the power to spend its treasury, and has the power to deploy new game contracts among other things. The desire to govern the ecosystem drives up the demand for SIGMA2, hence driving the market price higher.

## Network Effects

As Sigma Squared gains more users and the SIGMA2 market cap increases, there are network effects in play.

* As more bets are placed, the contract balances increase (for games with positive house edge). This will increase the maximum allowable bet.
* As the demand for SIGMA2 and its market capitalization increases, the price of SIGMA2 will become more stable, increasing players’ willingness to hold and gamble using SIGMA2. Also, the higher the SIGMA2 market cap, the larger the maximum allowable SIGMA2 bet.
* As the price of SIGMA2 increases, the DAO’s treasury becomes more valuable. The purpose of the treasury is to encourage development and marketing for Sigma Squared. This incentivizes more development, which improves the user experience. It also incentivizes marketing, which brings more players into the ecosystem.

## Evolution of the Ecosystem

The current state of Sigma Squared is intended to be only a starting point. Thus, ensuring the ecosystem has the ability to evolve over time is of utmost importance.

Old game contracts can be replaced, or new game contracts deployed using DAO proposals. If a game contract needs to be replaced, a proposal can be made which programmatically drains the old game contract, deploys a new one, and transfers all funds to the new contract. If a new game contract needs to be deployed, this can also be done using a similar process.

The initial front-end interface that players use to place bets is completely open source and hosted on IPFS. Development for this can follow existing processes used across the open source community. In addition to this, anyone can create their own front-end for Sigma Squared. The more front-end interfaces developed, the more variety in gambling experience players have and the more decentralized Sigma Squared become.
