# TradeSphere Academy — Auction Mechanics

## Overview

TradeSphere Academy uses **Uniswap's Continuous Clearing Auction (CCA)** protocol for on-chain token distribution and price discovery.

Unlike a conventional fixed-price token sale, a continuous clearing auction allows participants to compete for allocations while tokens are released over time.

Bids, available supply, and clearing prices interact throughout the auction, creating a dynamic market for the initial distribution of tokens.

Academy builds on Uniswap CCA with additional capabilities for auction configuration, scenario testing, simulation, automated participation, monitoring, visualization, and replay.

**Uniswap provides the auction protocol. Academy provides the environment for designing, operating, and understanding the auction.**

## How Continuous Clearing Works

A CCA auction distributes a configured token supply over a defined period.

Participants submit bids expressing how much they are willing to spend and the maximum price they are willing to pay.

As tokens become available, the auction determines allocations according to the active bids and the protocol's clearing rules.

The clearing price can rise as competition increases but does not decrease during the auction.

Participants bidding below the current clearing price may lose their ability to receive additional allocations.

### Key Concepts

| Concept | Description |
|---|---|
| Base Token | Token being distributed |
| Quote Token | Asset used to purchase the base token |
| Supply | Total base tokens allocated to the auction |
| Floor Price | Minimum clearing price |
| Bid Amount | Quote-token spending commitment |
| Maximum Price | Highest price a participant accepts |
| Clearing Price | Price determined by competing bids and available supply |
| Flow Rate | Rate at which auction tokens become available |
| Fill | Tokens allocated to a bid through clearing |
| Settlement | Final accounting of funds and token allocations |

The auction contract is authoritative for clearing, allocations, and settlement.

Academy's calculations and visualizations explain and reconstruct that execution.

---

## Auction Configuration

Before deployment, an auction is configured through Academy's registration and scenario models.

### Contract Configuration

Auction configuration includes:

- Base and quote token addresses
- Total auction supply
- Floor price
- Pricing tick spacing
- Minimum funding requirements, where configured
- Auction start and end times
- Claim timing
- Token and funds recipients

These parameters determine the assets, economic constraints, and on-chain operating conditions of the auction.

### Distribution Scenario

The associated scenario defines how tokens are released during the auction.

This includes the allocation, duration, rounds or steps, and token flow rates.

Academy allows different scenarios to be evaluated through its Test and Sim environments before moving into Live execution.

For the full execution architecture, see [Architecture](architecture.md).

---

## Rounds, Steps & Flow

Uniswap CCA supports token distribution over time.

Academy organizes that distribution into **rounds (steps)** to make the changing release schedule easier to understand.

A scenario may distribute different percentages of its supply over different portions of the auction's duration.

Each round can therefore have its own flow characteristics.

![TradeSphere Academy — Auction Execution](../assets/academy-auction.png)

*Test auction showing the current round, token flow, clearing information, competing bids, and bid controls.*

### Distribution Example

Consider an auction configured with five rounds.

| Round | Duration Share | Supply Share |
|---|---:|---:|
| 1 | 20% | 15% |
| 2 | 20% | 20% |
| 3 | 20% | 25% |
| 4 | 20% | 25% |
| 5 | 20% | 15% |

*Illustrative configuration, not a prescribed distribution.*

Each round releases tokens at a rate determined by its allocated supply and duration.

A round allocating more tokens over the same duration has a higher flow rate.

### Flow Visualization

Academy's flow indicator helps participants understand:

- The current round or step
- The relative distribution rate
- The amount of supply allocated to each round
- How much of the current round's supply remains

This makes the auction's distribution schedule visible without requiring participants to interpret contract checkpoints.

**Rounds represent changes in distribution conditions, not separate auctions.**

---

## Bidding

Participants connect their wallets and submit bids using the auction's quote token.

Each bid expresses two principal constraints:

**Spending Cap**

The maximum amount of quote tokens committed to the bid.

**Price Ceiling**

The maximum price the participant is willing to pay for the base token.

These constraints define the participant's willingness to compete for allocation.

### Bid Submission

A participant:

1. Connects a supported wallet.
2. Selects the auction.
3. Reviews the current clearing price and available information.
4. Configures the bid amount and maximum price.
5. Authorizes any required token allowances.
6. Submits the bid as an on-chain transaction.

Once confirmed, the bid becomes part of the auction's competitive clearing process.

### Allowances & Authorization

ERC-20 bidding may require token allowance operations before a transaction can be submitted.

Academy guides participants through the necessary approval process, including Permit2 authorization where applicable.

Transactions initiated by connected participants require wallet authorization.

### System Bidding

Academy also supports system-managed transactions through Nethereum.

This allows automated participants to submit bids using managed accounts.

Automated bidding supports scenario evaluation, competitive testing, and configured system participation.

The same underlying auction contract rules apply to transactions submitted by human participants and system actors.

---

## Clearing Price & Bid Competition

Continuous clearing creates competition between bids for the supply becoming available.

When available supply is insufficient to satisfy all competing demand at current prices, the clearing price can advance.

Bids with higher maximum prices can remain competitive as lower-priced bids cease to qualify for additional allocation.

### Clearing Price Behavior

The clearing price is nondecreasing: it can remain unchanged or increase, but it does not move backward.

A participant's price ceiling therefore matters throughout the auction.

An aggressive bid may remain competitive across a wider range of clearing prices, while a conservative bid may stop qualifying as competition increases.

### Bids & Available Supply

The current state of a bid is not necessarily its final result.

As supply is released and competition changes, the auction recalculates which bids qualify for allocation.

Within an active round, available supply can be exhausted by competing demand before the round ends.

At that point, competition among qualifying bids becomes particularly significant.

A bid's current allocation can change as higher-priced bids compete for the available supply.

**A displayed fill is provisional until the applicable on-chain auction rules finalize it.**

### Competitive Outcomes

Academy presents bid and position information so participants can distinguish between bids that are competitive, partially allocated, or currently outbid.

Final outcomes depend on clearing, auction completion, and settlement.

---

## Checkpoints & Auction State

Uniswap CCA uses checkpoints to represent cumulative auction execution state.

Academy reads checkpoint information and uses it to reconstruct and display the auction's progress.

Checkpoint-related data includes:

- Blockchain position
- Cumulative token distribution
- Clearing price
- Funds raised
- Allocation-related calculations

### Blockchain Monitoring

Academy monitors blockchain state and maintains a shared application model for connected participants.

This reduces redundant blockchain RPC activity and supports consistent presentation of auction information.

The user interface can update its displayed timing and state between blockchain observations, but authoritative on-chain state advances with confirmed execution.

### Application Calculations

Academy uses Nethereum and its auction calculation services to interpret contract values, including fixed-point pricing and token-unit conversions.

These calculations support:

- Clearing price display
- Token allocation estimates
- Bid and position summaries
- Scenario evaluation
- Replay and result verification

The application model does not replace the auction contract as the authoritative source.

---

## Auction Lifecycle

Academy tracks the auction through its operational states.

| State | Description |
|---|---|
| Pending | Configured or deployed, awaiting its start |
| Active | Auction is running and accepting eligible participation |
| Ended | Auction period has completed |
| Claimable | Eligible settlement or claim operations are available |
| Settled | Final settlement has been completed |

Actual operations depend on the auction contract state and supported lifecycle transitions.

### Exiting & Reclaiming

Participants can exit or reclaim funds when the contract's conditions permit.

An exit can remove a bid from continued competition, subject to the rules and timing of the auction.

### Claiming

Once the auction reaches the appropriate state, participants can claim their resulting token allocations and any refundable quote-token balances according to the contract's settlement rules.

Academy supports both participant-authorized and system-managed exit and claim transactions.

---

## Positions

Academy provides participants with a consolidated view of their auction positions.

### Position Summary

Position information includes:

- Total committed funds
- Average price information
- Number of bids
- Current allocations
- Settlement balances

### Bid Status

During an active auction, bids may be presented as:

| Status | Meaning |
|---|---|
| Clearing | Currently qualifying for allocation |
| Partial | Receiving less than the requested allocation |
| Outbid | Not currently qualifying for allocation |

After the auction closes, final bid outcomes can be presented as Cleared, Partial, or Outbid.

The interface distinguishes current competitive conditions from finalized outcomes.

### Settlement Balances

Settlement information separates the quote-token and base-token sides of the position.

This allows participants to understand the funds committed, tokens allocated, and balances available for reclaim or claim.

---

## Scenario Testing & Validation

Academy's auction mechanics can be evaluated in three execution environments.

### Test — Mock

Test executes the auction model off-chain.

It supports configurable execution speed, automated bidders, and replay without requiring blockchain transactions.

Developers can experiment with distribution schedules, flow rates, pricing, duration, and participant behavior.

### Sim — Testnet

Sim operates against real smart contracts on a testnet such as Ethereum Sepolia.

It exercises blockchain transactions, automated bidders, clearing, settlement, and claims using test assets.

Scenarios can be cloned from Test into Sim.

### Live — Mainnet

Live operates against mainnet smart contracts with real assets and economic commitments.

Scenarios can be cloned from Sim into Live, with the appropriate network and deployment configuration.

Replay is supported across all three environments.

---

## Replay & Verification

Academy supports reconstructing auction activity and replaying its execution.

Replay is designed for more than historical visualization.

The application rebuilds auction calculations and compares reconstructed results with recorded execution outcomes.

This helps developers evaluate:

- Clearing price progression
- Bid competition and allocation
- Supply distribution
- Checkpoint calculations
- Final settlement results

Replay provides a useful mechanism for diagnosing discrepancies between modeled and observed auction behavior.

It is especially valuable when evaluating complicated scenarios involving numerous bids, automated participants, and changing distribution rates.

---

## What Academy Adds

Uniswap CCA provides the on-chain auction protocol.

Academy extends the operating environment around that protocol.

| Capability | Contribution |
|---|---|
| Auction Registration | Project identity, configuration, and scenario management |
| Token Support | Creation of new tokens and integration of existing tokens |
| Scenario Design | Configurable distribution, flow, rounds, and duration |
| Test | Off-chain mock execution and evaluation |
| Sim | Testnet validation using real smart contracts |
| Live | Mainnet auction execution |
| Automated Participants | Configurable system bidding and scenario evaluation |
| Market Visualization | Live clearing, flow, bid, and position information |
| Replay | Reconstruction, recalculation, and verification |
| Project Discovery | Future community-driven token and project registry |

Auction participation and monitoring are publicly accessible. Creation, scenario administration, automated testing, and replay currently remain restricted.

Broader access is planned after successful validation through the first two IRN campaign auctions.

**Our objective is not to replace Uniswap's protocols, but to make them easier to configure, evaluate, operate, and participate in.**

---

## Related Documentation

- [Architecture](architecture.md)
- [Technology Stack](technology.md)
- [Bots & Scenarios](bots.md)
- [Rewards & Qualification](rewards.md)
- [Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)
