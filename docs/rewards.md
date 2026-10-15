# TradeSphere Academy — Rewards & Qualification

## Overview

**Gridiron: The Reckoning** is a five-stage auction campaign designed to launch the IRN token economy through market-driven funding, price discovery, and community participation.

The first two stages introduce additional incentives:

- **01 — Discovery:** Participate on Ethereum Sepolia using test assets to qualify for IRN matching rewards.
- **02 — Confidence:** Purchase IRN on Arbitrum One, receive qualifying matching rewards, and participate in the USDC and IRN bonus lottery.

**Discovery establishes eligibility for matching rewards. Confidence determines the rewards.**

The bonus lottery does not require Discovery participation.

---

## The Reckoning Campaign

The campaign allocates 5% of IRN's total supply of 1 trillion tokens.

| Stage | Auction | Allocation | IRN |
|---|---|---:|---:|
| 01 | Discovery | 10% | 5 billion |
| 02 | Confidence | 15% | 7.5 billion |
| 03 | Momentum | 20% | 10 billion |
| 04 | Expansion | 25% | 12.5 billion |
| 05 | Peak | 30% | 15 billion |
| **Total** | | **100%** | **50 billion** |

Discovery's 5 billion IRN allocation is reserved for Confidence incentives rather than distributed as Arbitrum One tokens during Discovery.

Confidence therefore has:

| Allocation | IRN |
|---|---:|
| Auction supply | 7.5 billion |
| Bonus and matching reserve | 5 billion |
| **Maximum combined distribution** | **12.5 billion** |

Each stage must meet its published minimum funding requirement to graduate. Failure ends the current campaign. A project may launch another campaign later.

Following successful Confidence graduation, the project intends to establish its initial Uniswap liquidity pool. Subsequent stages can continue token distribution alongside the secondary market.

---

## 01 — Discovery

Discovery takes place on **Ethereum Sepolia**, using test assets and real blockchain transactions.

Participants can experience the auction without committing real purchase funds.

### Participation

1. Connect a supported wallet and select the Sepolia network.
2. Receive the test USDC provided for Discovery.
3. Place a bid in the Discovery auction.
4. Retain access to the participating wallet address.

Sepolia gas may still be required.

Connecting a wallet alone does not establish qualification. **Actual Discovery auction participation is required.**

### Qualification

The address used during Discovery establishes eligibility for matching rewards in Confidence.

Participants must use **the same wallet address** when purchasing IRN during Confidence.

Discovery's testnet auction supply is currently configured at **1 billion test IRN**. This does not limit the number of Arbitrum One IRN tokens eligible for matching in Confidence.

Discovery determines eligibility, not the size of an individual's matching reward.

---

## 02 — Confidence

Confidence is the first Arbitrum One mainnet auction, using real USDC and IRN.

It introduces two separate incentives:

1. **IRN Matching Rewards** for qualified Discovery participants.
2. **USDC and IRN Bonus Lottery** for eligible Confidence participants.

### Participation Limits

| Requirement | Amount |
|---|---:|
| Minimum qualifying purchase | 100 USDC |
| Maximum qualifying purchase | 5,000 USDC |

The limits are intended to encourage broad participation rather than concentration among large bidders.

A submitted bid alone does not guarantee an allocation. Qualifying purchases must clear and settle under the auction rules.

Applicable participation restrictions must be enforced through appropriate contract mechanisms, not solely through the user interface.

---

## IRN Matching Rewards

Participants who qualify through Discovery can receive additional IRN based on their eligible Confidence allocations.

### Eligibility

A participant must:

- Have participated in Discovery.
- Use the same wallet address in Confidence.
- Make a qualifying settled Confidence purchase.
- Meet the applicable purchase limits.

**No qualifying Confidence purchase, no matching rewards.**

### Matching Reserve

The campaign allocates **5 billion IRN** for Confidence incentives.

The IRN lottery bonus is deducted from this reserve first. The remainder is available for matching rewards.

`Available Matching IRN = 5,000,000,000 - Lottery Bonus IRN`

### Proportional Matching

Matching rewards are calculated from qualifying Confidence IRN allocations—not Discovery allocations.

The initial objective is a **1:1 IRN match**.

If the available reserve can cover all qualifying allocations, participants receive a full match.

If matching demand exceeds the reserve, rewards are reduced proportionally for all qualifying participants.

**Formulas:**

`Matching Demand IRN = Sum of All Qualifying Confidence IRN Allocations`

`Matching Ratio = Min(1, Available Matching IRN / Matching Demand IRN)`

`Participant Matching Reward = Qualifying Confidence IRN Allocation × Matching Ratio`

The matching ratio is zero when there are no qualifying allocations.

### Example

Assume:

- Available matching reserve: 4 billion IRN
- Total qualifying Confidence allocations: 5 billion IRN

The matching ratio is:

`Matching Ratio = 4B / 5B = 80%`

A participant purchasing 10 million IRN would receive:

`Matching Reward = 10,000,000 × 80% = 8,000,000 IRN`

All qualifying participants receive the same proportional matching rate.

**There is no first-come-first-served advantage in matching reward allocation.**

---

## Confidence Bonus Lottery

The Confidence bonus lottery awards **both USDC and IRN**.

Discovery participation is not required. Eligibility is based on the published Confidence participation and settlement rules.

### Bonus Calculation

The USDC bonus is calculated as **3% of Confidence's settled USDC proceeds**.

An equivalent IRN amount is calculated using the final clearing price.

**Formulas:**

`Bonus USDC = Settled USDC Proceeds × 0.03`

`Bonus IRN = Bonus USDC / Final Clearing Price`

### Example

Assume:

- Settled proceeds: 100,000 USDC
- Final clearing price: 0.00005 USDC per IRN

Then:

`Bonus USDC = 100,000 × 0.03 = 3,000 USDC`

`Bonus IRN = 3,000 / 0.00005 = 60,000,000 IRN`

**Total bonus: 3,000 USDC + 60,000,000 IRN**

The USDC component is funded separately from the IRN reserve, using the designated portion of Confidence proceeds.

The IRN component comes from the 5 billion IRN incentive reserve.

### Bonus and Reserve Relationship

The IRN bonus is allocated first.

Using the example above:

`Available Matching IRN = 5,000,000,000 - 60,000,000`

`Available Matching IRN = 4,940,000,000 IRN`

The remaining reserve supports proportional matching rewards.

**The combined IRN lottery bonus and matching rewards cannot exceed 5 billion IRN.**

If the calculated IRN bonus would exceed its available reserve, the final campaign rules must define the applicable cap before activation.

### Lottery Selection

The final winner-selection method, eligibility details, verification procedure, and distribution process will be published before Confidence.

The lottery bonus calculation is independent of the winner-selection process.

---

## Real-Time Rewards & Bonuses

Academy can calculate the current bonus and matching allocations throughout Confidence.

These values are **unrealized**, not estimates based on hypothetical market assumptions. They are calculated from the auction's current state.

| Metric | Calculation |
|---|---|
| Unrealized USDC Bonus | 3% of current settlement-related proceeds |
| Unrealized IRN Bonus | USDC bonus divided by current clearing price |
| Available Matching Reserve | 5B IRN minus unrealized IRN bonus |
| Unrealized Matching Ratio | Available reserve divided by total qualifying IRN allocations, capped at 100% |
| Unrealized Individual Reward | Qualifying IRN allocation multiplied by the current matching ratio |

As bids, clearing prices, and allocations change, the values are recalculated.

### Realized and Unrealized Allocations

Auction allocations have distinct accounting states:

- **Unrealized:** Current-round fills that can change as bidding continues.
- **Realized:** Fills established at the close of completed rounds.
- **Settled:** Final auction balances established through settlement.

A position may contain both realized fills from previous rounds and unrealized fills from the current round.

Bonus and matching calculations use the applicable auction state, with final amounts determined from completed settlement.

### Auction vs. Position Settlement

Auction settlement and participant position settlement are separate.

An auction may be settled while individual participants still have outstanding exits, refunds, or token claims.

Final reward accounting follows authoritative auction settlement results. Individual reward delivery and position claims follow their applicable distribution procedures.

---

## Verification & Enforcement

Discovery and Confidence take place on separate networks.

| Stage | Network | Assets |
|---|---|---|
| Discovery | Ethereum Sepolia | Test assets |
| Confidence | Arbitrum One | Real assets |

Qualification is linked through the participant's wallet address.

On-chain bidding, clearing, and settlement provide verifiable evidence of participation.

Campaign-specific eligibility rules and purchase limits must be enforced appropriately, including against transactions submitted directly to the contracts.

Final reward and lottery allocations must be reconciled against actual settlement results.

---

## Beyond Confidence

The campaign continues through three additional stages, provided each preceding stage graduates.

| Stage | Allocation |
|---|---:|
| Momentum | 10 billion IRN |
| Expansion | 12.5 billion IRN |
| Peak | 15 billion IRN |

These stages continue controlled token distribution and capital formation as the project develops.

Future stage timing and scenario configuration can respond to previous auction results.

Discovery matching rewards and the Confidence bonus lottery are specific to Confidence; they do not automatically repeat in later stages.

---

## Current Status

Discovery provides the initial testnet qualification environment.

Confidence is the planned first Arbitrum One stage, conditional on Discovery meeting its graduation requirements.

The incentive structure is defined as:

- **3% USDC bonus** calculated from Confidence proceeds.
- **Equivalent IRN bonus** calculated using the clearing price.
- **5 billion IRN reserve** funding the IRN bonus first, with the remainder used for matching.
- **Proportional IRN matching** of qualifying Confidence allocations.
- **Real-time unrealized calculations**, finalized through settlement.

Contract enforcement, lottery selection, reward distribution, and any applicable reserve limits must be finalized before the incentives are activated.

---

## Related Documentation

- [Architecture](architecture.md)
- [Auction Mechanics](auction.md)
- [Technology Stack](technology.md)
- [Bots & Scenarios](bots.md)
- [Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)