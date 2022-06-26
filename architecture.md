# Architecture

## High-Level Diagram

![component diagram](<assets/Sigma Squared Architecture.jpg>)

## Components

### Sigma Squared Token

This is a standard ERC20 token contract. The owner of the token is the DAO. This means the DAO has the power to mint and burn tokens, along with pausing all transactions in case of emergency. The contract is based on the OpenZeppelin ERC20 contract.

Contract list: [SigmaSquared](https://github.com/sigma-squared-dapp/sigma-squared-core/blob/master/contracts/SigmaSquared.sol)

### DAO

The DAO has the ability to execute arbitrary transactions that are proposed and voted on. Sigma Squared holders can propose and vote. Voting shares are represented using Sigma Squared ERC20 tokens. This contract is based on the OpenZeppelin Governor contract.

The DAO owns the Sigma Squared token contract, and all of the game contracts. It has the power to call any functions on these contracts that are marked ‘onlyOwner’. The functions can adjust game parameters, withdraw funds from games, etc..

Contract list: [SigmaSquaredGovernor](https://github.com/sigma-squared-dapp/sigma-squared-core/blob/master/contracts/SigmaSquaredGovernor.sol), [SigmaSquaredTimelockController](https://github.com/sigma-squared-dapp/sigma-squared-core/blob/master/contracts/SigmaSquaredTimelockController.sol)

### Rewards Contracts

This is the set of contracts that distribute rewards to players. For more information on how the rewards are distributed, see the [Rewards](rewards.md) section of the documentation. The game contracts report wins and losses to these contracts, because rewards are distributed based on betting activity.

After the distribution of all rewards from the initial token allocation, these contracts will be decommissioned.

Contract list: [SigmaSquaredLargestLossRewards](https://github.com/sigma-squared-dapp/sigma-squared-core/blob/master/contracts/SigmaSquaredLargestLossRewards.sol), [NativeLargestLossRewards](https://github.com/sigma-squared-dapp/sigma-squared-core/blob/master/contracts/NativeLargestLossRewards.sol), [USDCLargestLossRewards](https://github.com/sigma-squared-dapp/sigma-squared-core/blob/master/contracts/USDCLargestLossRewards.sol)

### Game Contracts

This is the set of contracts that players interact with to place bets.  These are described in the [Games section](games.md) of the documentation.