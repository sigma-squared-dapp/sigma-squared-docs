# Bernoulli Games

This set of game contracts allows users to bet on a Bernoulli random variable.  In simpler terms, it’s a bet with two possible outcomes: either a win or a loss.  A bet can be placed by specifying a bet amount and a multiplier.  The bet amount is sent to the game contract.  If the bet results in a win, the player is transferred (bet amount) * (multiplier).  If the bet results in a loss, the player receives nothing.  The probability of a win/loss is determined by the house edge.

There is a different contract deployed for each type of token accepted as bets.  Currently that includes USDC, MATIC, and SIGMA2.

### Notable params: TODO

| Name | Description |
| --- | --- |
| houseEdge | |
| maxWinAmount | |
| minBetAmount | |


Github Links: TODO

Contract Address: TODO

# Lottery Games

This set of game contracts consists of lottery style games.  Players can enter a lottery by depositing some amount of tokens.  At the end of the lottery period a single player is picked as a winner, and they receive the entire prize pool.  The probability of each player winning is weighted based on their deposit amount.  If there is some house edge specified, then that percentage is taken out of each deposit and held as profit instead of going to the lottery pool.

### Notable params: TODO

| Name | Description |
| --- | --- |
| houseEdge | |
| minBetAmount | |
| roundLengthBlocks | |

Github Links: TODO

Contract Address: TODO


# Fairness

The fairness of each game contract is extremely important.  Fairness is ensured by settling bets with verified randomness provided by Chainlink VRF.  All game contracts are open source, so the implementation of the games and use of the randomness can be audited as well.

# User Interface

A front end web application allows users to interact with the above smart contracts in a user-friendly way.  This front-end is hosted on IPFS to ensure decentralization.  Currently the following games are supported.

| Front-end Game Name | Underlying Smart Contract Game | Description |
| --- | --- | --- |
| Coin Flip | Bernoulli | Players bet on a fair coin flip.  The chance of winning is always 50%.  The payout depends on the house edge.  For example if the house edge is 0%, the payout is always 2x.  If the house edge is 5%, the payout is 1.9x. |
| Poker Hands | Bernoulli | A player bets on who has the best poker hand, against any number of ‘house’ hands (not real players).  A single bet is placed before cards are dealt, and the payout and probability depend on the number of opponents selected. |
| Lottery | Lottery | Players enter a lottery.  A single player wins; the probability of winning is weighted based on the amount deposited. |

In addition to these games, there is a section that shows a player’s overview.  It displays the player’s recent bets, along with the rewards that are available to claim.

# Future Work

Future development will focus on adding new front end games, and potentially new smart contract game types.  Some ideas are described below.

- **Crash game**: Players specify a multiplier, and they either win or lose.  A rocket or other animation shows the multiplier slowing increasing until it crashes.  It will use the Bernoulli game contracts.

- **Roulette**: Roulette style game where players can place bets on numbers.  It will use the Bernoulli game contracts.

- **Arbitrary discrete payout structure**: This is a new underlying contract game type.  Users can place a bet by specifying a list of payouts and probabilities.  The expected value has to add up to betAmount * (- house edge).  This will be less gas efficient than the Bernoulli game, however it will allow for any arbitrary discrete payout structure to be used.  Almost any gambling game can be reduced to some discrete payout structure, so this opens up the opportunity for developers to implement an endless number of front-end games.
