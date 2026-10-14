# TradeSphere Academy — Auction Mechanics

## Overview

TradeSphere Academy uses **Uniswap's Continuous Clearing Auction (CCA)** protocol for on-chain token distribution and price discovery.

Participants bid for tokens as supply is released over time. Clearing prices and allocations respond to demand under the protocol's rules.

Academy extends CCA with configurable distribution scenarios, automated participants, real-time visualization, and replay.

**Uniswap provides the auction protocol. Academy provides the tools to configure, operate, and understand it.**

---

## Academy Auctions & Staged Campaigns

### Why Multiple Auctions?

A single auction can establish an initial market price, but it may not generate sufficient capital or liquidity to support a developing project.

Builders need a way to introduce supply progressively, attract participants, and finance continued development without committing their entire token allocation at launch.

Academy's staged campaign model addresses these requirements through controlled distribution and successive funding opportunities.

### Campaign → CCA → Steps

An **Academy Auction** represents a campaign composed of multiple independently executed Uniswap CCAs.

| Level | Responsibility |
|---|---|
| **Academy Auction** | Campaign allocation, stages, graduation, scheduling, and cumulative results |
| **CCA Stage** | Independent auction execution, clearing, settlement, exits, and claims |
| **Steps / Rounds** | Token distribution schedule within an individual CCA |

The structure applies distribution at two levels: a campaign allocates supply across CCA stages, and each CCA distributes its supply across steps.

Participants experience one Academy Auction while the underlying CCAs operate independently.

### Graduation & Progression

Each stage must meet its published minimum funding requirement to graduate.

- **Graduated:** The campaign may advance to the next stage.
- **Not Graduated:** The current campaign ends. The project may launch another Academy Auction later.

Completed stage results can inform the timing and configuration of future stages.

Typical CCA durations are expected to be approximately **3–4 days**. Strong participation may justify shorter intervals between stages; slower development may warrant additional preparation and outreach.

The terms of an active CCA remain unchanged. Adjustments apply to future stages.

### Liquidity Development

Following successful Confidence graduation, the project intends to establish its initial Uniswap liquidity pool.

This creates two complementary markets:

| Market | Purpose |
|---|---|
| **Uniswap Liquidity Pool** | Ongoing secondary-market trading |
| **Academy CCA Stages** | Controlled primary distribution and capital formation |

Later CCA stages can operate alongside the liquidity pool, introducing additional supply and funding opportunities as the project develops.

Pool creation depends on the availability of designated assets and the completion of the required liquidity operations.

### The Reckoning Campaign

*Gridiron: The Reckoning* illustrates the staged approach.

| Stage | Network | Purpose | Liquidity |
|---|---|---|---|
| **01 — Discovery** | Sepolia | Participation and qualification | — |
| **02 — Confidence** | Mainnet | Initial funding and price discovery | Launch initial pool |
| **03 — Momentum** | Mainnet | Continue controlled distribution | Add liquidity |
| **04 — Expansion** | Mainnet | Broaden participation and capital formation | Add liquidity |
| **05 — Peak** | Mainnet | Complete the planned campaign allocation | Add liquidity |

Each stage advances only if the preceding CCA graduates. Subsequent stages can contribute additional assets to the existing liquidity pool and project treasury.

**Implementation status:** Individual CCA execution is operational. Unified campaign orchestration, adaptive scheduling, and campaign-level graduation are part of Academy's evolving implementation.

---

## Continuous Clearing Mechanics

A CCA releases a configured token supply over a defined period.

Participants submit bids specifying how much they are willing to spend and the maximum price they will accept.

As supply becomes available, the protocol determines allocations from the active bids.

The clearing price is nondecreasing: it may remain unchanged or increase, but cannot move backward.

| Concept | Description |
|---|---|
| **Base Token** | Token being distributed |
| **Quote Token** | Asset used to purchase the base token |
| **Supply** | Total base tokens allocated to the CCA |
| **Floor Price** | Minimum clearing price |
| **Spending Cap** | Maximum quote-token commitment |
| **Price Ceiling** | Highest price accepted by a bidder |
| **Clearing Price** | Price determined by qualifying demand and available supply |
| **Flow Rate** | Rate at which auction tokens become available |
| **Fill** | Tokens allocated to a bid |
| **Checkpoint** | Recorded cumulative auction execution state |

The smart contracts remain authoritative for clearing and settlement. Academy maintains corresponding calculations for monitoring, simulation, and verification.

---

## Rounds, Steps & Token Flow

Academy organizes each CCA's distribution schedule into **rounds (steps)**.

A round has a defined duration and allocation of the auction's supply. Its flow rate depends on the relationship between those values.

### Distribution Example

| Round | Duration Share | Supply Share |
|---|---:|---:|
| 1 | 20% | 15% |
| 2 | 20% | 20% |
| 3 | 20% | 25% |
| 4 | 20% | 25% |
| 5 | 20% | 15% |

*Illustrative configuration. Equal round durations produce flow rates proportional to the allocated supply.*

### Flow Visualization

![TradeSphere Academy — Auction Execution](../assets/academy-auction.png)

*Academy Test auction showing rounds, token flow, clearing, bids, and participant controls.*

The flow indicator displays the active round, its relative release rate, allocated supply, and remaining tokens.

Rounds describe changes in distribution conditions, not independent auctions.

### Realized & Unrealized Allocations

Allocations have distinct states during execution.

**Unrealized**

Current-round fills remain subject to changing bid competition and clearing conditions.

**Realized**

At a completed round boundary, that round's fills are established. A bid may be partially or fully filled.

**Continued Allocation**

Eligible bids can receive additional fills in subsequent rounds.

A participant's cumulative allocation can therefore include both realized fills from completed rounds and unrealized fills from the current round.

This distinction describes the auction calculations. Separate realized and unrealized position fields and UI presentation are planned enhancements.

---

## Bidding & Price Discovery

Participants connect their wallets and place bids using the auction's quote token.

Each bid specifies two principal constraints:

- **Spending Cap:** The maximum quote-token amount committed.
- **Price Ceiling:** The maximum price the participant accepts for the base token.

### Bid Submission

1. Connect a supported wallet and select the appropriate network.
2. Review the auction's current clearing price and bid conditions.
3. Configure the spending cap and price ceiling.
4. Authorize any required ERC-20 allowances, including Permit2 where applicable.
5. Submit the transaction through the connected wallet.

Academy uses Reown for participant-authorized transactions and Nethereum for system-managed transactions, including automated bidding.

Both paths interact with the same CCA contracts.

### Bid Competition

As bids enter the auction, the available supply is allocated according to the protocol's clearing rules.

When demand exceeds supply at the current clearing price, the clearing price can advance.

Bids below the clearing price stop qualifying for additional allocation. Bids with higher price ceilings can remain eligible.

Within an active round, additional bids can displace unrealized allocations before that round's fills are established.

### Bid Status

Academy presents the following active bid conditions:

| Status | Meaning |
|---|---|
| **Clearing** | Currently qualifying for allocation |
| **Partial** | Receiving less than the requested allocation |
| **Outbid** | Not currently qualifying for allocation |

After the auction closes, final outcomes are represented as **Cleared**, **Partial**, or **Outbid**.

Bid status and allocation are related but distinct: a bid may already have realized fills from completed rounds even if its remaining demand becomes outbid.

---

## Checkpoints & Monitoring

Uniswap CCA checkpoints represent cumulative execution state.

Academy reads contract state and checkpoints to monitor auction progress and reconstruct clearing calculations.

Relevant information includes:

- Blockchain position and execution progress
- Cumulative token distribution
- Clearing price
- Funds raised
- Allocation calculations

### Blockchain Synchronization

Academy centralizes blockchain monitoring through shared application services.

This reduces redundant RPC traffic from connected browsers and provides a consistent application model.

The interface can update its clock and presentation between blockchain observations, while authoritative contract state follows confirmed on-chain execution.

### Numeric Calculations

Academy's .NET services use Nethereum and calculation utilities for contract data, token decimals, and fixed-point prices, including Q96 representations.

These calculations support monitoring and replay without replacing the smart contracts as the authoritative source.

For execution environments and automated validation, see [Bots & Scenarios](bots.md).

---

## Auction Lifecycle & Settlement

An individual CCA progresses through the following application states.

| State | Description |
|---|---|
| **Pending** | Awaiting the configured start |
| **Active** | Auction execution and eligible bidding are underway |
| **Ended** | The auction period has completed |
| **Claimable** | Applicable claim operations are available |
| **Settled** | Auction-level settlement has completed |

These states describe the auction itself. Participant positions have separate settlement responsibilities.

### Auction Settlement

Auction settlement completes the auction's required accounting and transfers of funds and tokens according to the contract rules.

Final clearing results establish the economic outcomes.

### Position Settlement

Individual participants may still have outstanding exits, refunds, or token claims after the auction has settled.

**A settled auction does not imply that every participant has claimed their balances.**

Academy supports both connected-wallet and system-managed exit and claim transactions, subject to the relevant contract conditions.

### Exits & Claims

Participants can exit eligible bids or reclaim balances when the contract permits.

Claims transfer the resulting token allocations or refundable quote-token balances according to the auction's settlement rules.

These operations are independent for each CCA stage. Participants do not need to wait for the entire Academy Auction campaign to conclude.

---

## Positions & Allocations

Academy consolidates participant bids into position summaries.

Position information includes:

- Committed funds
- Average purchase price
- Bid count and status
- Token allocations
- Quote-token and base-token settlement balances

### Allocation Accounting

At any point during an active auction:

`Total Filled Amount = Realized Amount + Unrealized Amount`

Realized amounts originate from completed rounds. Unrealized amounts represent current-round allocations that may still change.

At the end of the auction, the cumulative allocation is finalized under the contract's clearing rules.

The distinction between realized allocations, auction settlement, and individual claims is important:

- **Realized:** Allocation established through completed rounds.
- **Settled:** Final auction accounting completed.
- **Claimed:** The participant has executed the applicable claim operation.

A participant may have realized allocations that are not yet claimable, or claimable balances that remain unclaimed.

The planned position-model update will expose realized and unrealized values separately.

---

## Related Documentation

- [Architecture](architecture.md) — Application architecture and creation
- [Technology Stack](technology.md) — .NET, Nethereum, Reown, and supporting technologies
- [Bots & Scenarios](bots.md) — Test, Sim, Live, automation, and replay
- [Rewards & Qualification](rewards.md) — Discovery qualification, Confidence matching, and bonuses
- [Uniswap CCA Documentation](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)