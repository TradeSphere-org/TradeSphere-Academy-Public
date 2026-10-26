# TradeSphere Academy — Rewards & Qualification

## Overview

**Gridiron** is the first featured project on TradeSphere Academy, introducing the IRN token economy through **The Reckoning**, a five-phase campaign of market-driven funding, price discovery, and community participation.

The first two phases introduce distinct objectives and incentives:

- **01 — Discovery phase:** Establish community participation and qualification through the Discovery auction on Ethereum Sepolia, using test assets.
- **02 — Confidence phase:** Establish initial market demand and funding through the Confidence auction on Arbitrum One, using real USDC, with matching IRN rewards and a bonus lottery.

**The Discovery auction establishes eligibility. Qualifying purchases in the Confidence auction determine matching rewards.**

Participation in the Discovery auction is not required for the Confidence auction bonus lottery.

---

## Gridiron — The Reckoning Campaign

The Reckoning allocates **5% of IRN's total supply of 1 trillion tokens** to a progressive campaign designed to establish the IRN market, develop liquidity, and support Gridiron's growth.

| Phase | Purpose | Allocation | IRN |
|---|---|---:|---:|
| 01 — Discovery | Participation and qualification | 10% | 5 billion |
| 02 — Confidence | Initial funding and price discovery | 15% | 7.5 billion |
| 03 — Momentum | Continued market development | 20% | 10 billion |
| 04 — Expansion | Broader participation and capital formation | 25% | 12.5 billion |
| 05 — Peak | Complete planned campaign distribution | 30% | 15 billion |
| **Total** | | **100%** | **50 billion** |

### Discovery & Confidence Allocations

The Discovery phase's **5 billion IRN allocation** is reserved for incentives associated with the Confidence auction rather than distributed as mainnet IRN during the Discovery auction.

The Confidence phase therefore provides:

| Allocation | IRN |
|---|---:|
| Confidence auction supply | 7.5 billion |
| Bonus and matching reserve | 5 billion |
| **Maximum combined distribution** | **12.5 billion** |

### Campaign Progression

Each phase has objectives and graduation requirements that must be satisfied before the campaign advances.

The Discovery phase emphasizes broad participation and qualification. The Confidence phase introduces real capital commitments, competitive price discovery, and initial market funding.

A phase may involve multiple auction attempts. Results can inform subsequent attempts, including adjustments to configuration or the selection of different scenarios.

An unsuccessful auction attempt does not necessarily end its phase. Progression depends on the campaign's published requirements.

Following successful graduation of the Confidence phase, Gridiron intends to establish its initial Uniswap liquidity pool. Subsequent phases can continue token distribution and capital formation alongside the secondary market.

**The Reckoning is Gridiron's campaign strategy.** Other projects may use different structures, including a single auction.

---

## 01 — The Discovery Auction

The Discovery auction is Gridiron's public qualification auction, operating on **Ethereum Sepolia** using **test USDC and test IRN**.

An extended participation window gives the community time to participate. Defined minimum and maximum bidder requirements establish the qualification boundaries for advancing the campaign to the Confidence phase.

Participants can experience real blockchain transactions, live bidding, and continuous price discovery without committing real purchase funds.

### Participation

1. Connect a supported wallet on Ethereum Sepolia.
2. Explore the Discovery auction and configure a bid.
3. Receive test USDC automatically when placing the first bid.
4. Submit the bid and retain access to the participating wallet address.

Academy provides test USDC **once per wallet, immediately before its first bid** in the Discovery auction.

Connecting a wallet does not trigger funding. Additional test funding is not provided after bidding.

Sepolia network gas may still be required.

**Connecting a wallet alone does not establish qualification. An actual bid in the Discovery auction is required.**

### Participation Requirements

The Discovery auction uses an extended participation window with defined minimum and maximum bidder limits.

The minimum establishes the participation requirement for graduation. The maximum limits the number of participating bidders.

These requirements allow Gridiron to evaluate genuine community interest and participation before proceeding with its planned mainnet funding phase.

The specific duration and bidder limits are defined by the applicable auction configuration and campaign rules.

### Qualification

The wallet address used in the Discovery auction establishes eligibility for additional IRN matching rewards in the Confidence auction.

Participants must use **the same wallet address** when purchasing IRN in the Confidence auction.

Participation in the Discovery auction determines eligibility, not the size of an individual's matching reward.

The Discovery auction uses test IRN. Its testnet supply does not represent mainnet IRN distributed to participants and does not determine the available Confidence auction reward allocation.

**Qualification requires participation in the Discovery auction followed by a qualifying settled purchase in the Confidence auction.**

**[Explore the Gridiron Auction](https://academy.tradesphere.org/gridiron)**

---

## 02 — The Confidence Auction

The Confidence auction is the planned initial **Arbitrum One mainnet auction**, using real USDC to purchase IRN.

Its launch is conditional on satisfying the Discovery phase's graduation requirements.

The Confidence auction is designed to establish market demand, discover pricing, raise capital, and encourage broad participation.

It introduces two separate incentives:

1. **IRN Matching Rewards** for eligible Discovery auction participants who complete qualifying purchases in the Confidence auction.
2. **USDC and IRN Bonus Lottery** for eligible Confidence auction participants, regardless of prior Discovery auction participation.

### Participation Limits

| Requirement | Amount |
|---|---:|
| Minimum qualifying purchase | 100 USDC |
| Maximum qualifying purchase | 5,000 USDC |

These limits are intended to encourage broad participation rather than concentrating allocations among large bidders.

A submitted bid alone does not guarantee a purchase. Qualifying allocations must clear and settle under the auction rules.

Participation limits and applicable restrictions must be enforced through appropriate contract mechanisms, not solely through the Academy interface.

---

## IRN Matching Rewards

Participants who qualify through the Discovery auction can receive additional IRN based on their eligible purchases in the Confidence auction.

### Eligibility

A participant must:

- Have placed a bid in the Discovery auction.
- Use the same wallet address in the Confidence auction.
- Complete a qualifying settled purchase in the Confidence auction.
- Meet the applicable participation and purchase requirements.

**No qualifying Confidence auction purchase, no matching rewards.**

### Matching Reserve

The campaign allocates **5 billion IRN** for incentives associated with the Confidence auction.

The IRN lottery bonus is deducted from this reserve first. The remaining IRN is available for matching rewards.

`Available Matching IRN = 5,000,000,000 - Lottery Bonus IRN`

### Proportional Matching

Matching rewards are calculated from qualifying IRN allocations purchased in the Confidence auction—not from test-token allocations in the Discovery auction.

The initial objective is a **1:1 IRN match**.

If the available reserve covers all qualifying allocations, participants receive a full match.

If matching demand exceeds the available reserve, rewards are reduced proportionally across qualifying participants.

**Formulas:**

`Matching Demand IRN = Sum of All Qualifying Confidence Auction IRN Allocations`

`Matching Ratio = Min(1, Available Matching IRN / Matching Demand IRN)`

`Participant Matching Reward = Qualifying Confidence Auction IRN Allocation × Matching Ratio`

The matching ratio is zero when there are no qualifying allocations.

### Example

Assume:

- Available matching reserve: 4 billion IRN
- Total qualifying IRN allocations: 5 billion IRN

The matching ratio is:

`Matching Ratio = 4B / 5B = 80%`

A participant purchasing 10 million IRN would receive:

`Matching Reward = 10,000,000 × 80% = 8,000,000 IRN`

All qualifying participants receive the same proportional matching rate.

**There is no first-come-first-served advantage in matching reward allocation.**

---

## Confidence Auction Bonus Lottery

The Confidence auction bonus lottery awards **both USDC and IRN**.

Participation in the Discovery auction is not required. Eligibility depends on the published Confidence auction purchase and settlement requirements.

### Bonus Calculation

The USDC bonus is calculated as **3% of the Confidence auction's settled USDC proceeds**.

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

The USDC component is funded separately from the IRN reserve, using the designated portion of the Confidence auction proceeds.

The IRN component comes from the 5 billion IRN incentive reserve.

### Bonus & Reserve Relationship

The IRN bonus is allocated before matching rewards.

Using the example above:

`Available Matching IRN = 5,000,000,000 - 60,000,000`

`Available Matching IRN = 4,940,000,000 IRN`

The remaining reserve supports proportional matching rewards.

**The combined IRN lottery bonus and matching rewards cannot exceed 5 billion IRN.**

If the calculated IRN bonus would exceed the available reserve, the final campaign rules must define the applicable cap before activation.

### Lottery Selection

The final winner-selection method, eligibility details, verification procedure, and distribution process will be published before the Confidence auction.

The lottery bonus calculation is independent of the winner-selection process.

---

## Real-Time Rewards & Bonuses

Academy can calculate current bonus and matching allocations as the Confidence auction progresses.

These values are **unrealized calculations based on the current auction state**, not predictions based on hypothetical market assumptions.

| Metric | Calculation |
|---|---|
| Unrealized USDC Bonus | 3% of current settlement-related proceeds |
| Unrealized IRN Bonus | USDC bonus divided by current clearing price |
| Available Matching Reserve | 5B IRN minus unrealized IRN bonus |
| Unrealized Matching Ratio | Available reserve divided by qualifying IRN allocations, capped at 100% |
| Unrealized Individual Reward | Qualifying IRN allocation multiplied by the current matching ratio |

As bids, clearing prices, and allocations change, the values are recalculated.

### Realized & Unrealized Allocations

Auction allocations have distinct accounting states:

- **Unrealized:** Current-stage fills that can change as bidding continues.
- **Realized:** Fills established at the close of completed auction stages.
- **Settled:** Final auction balances established through settlement.

A position may contain both realized fills from previous stages and unrealized fills from the current stage.

Bonus and matching calculations use the applicable auction state, with final amounts determined from completed settlement.

### Auction vs. Position Settlement

Auction settlement and participant position settlement are separate.

An auction may be settled while individual participants still have outstanding exits, refunds, or token claims.

Final reward accounting follows authoritative auction settlement results. Individual reward delivery and position claims follow their applicable distribution procedures.

---

## Verification & Enforcement

The Discovery auction and Confidence auction operate on separate blockchain networks.

| Auction | Network | Assets |
|---|---|---|
| Discovery auction | Ethereum Sepolia | Test USDC and test IRN |
| Confidence auction | Arbitrum One | Real USDC and IRN |

Qualification is linked through the participant's wallet address.

On-chain bidding, clearing, and settlement provide verifiable evidence of participation.

Campaign-specific eligibility rules and purchase limits must be enforced appropriately, including against transactions submitted directly to the contracts.

Final reward and lottery allocations must be reconciled against actual settlement results.

---

## Beyond the Confidence Phase

The Reckoning continues through three additional phases, provided the campaign satisfies its progression requirements.

| Phase | Allocation |
|---|---:|
| Momentum | 10 billion IRN |
| Expansion | 12.5 billion IRN |
| Peak | 15 billion IRN |

These phases are intended to continue token distribution, participation, market development, and capital formation as the project evolves.

Subsequent phases may introduce new auction attempts, alternative strategies, and revised configurations based on previous results and market conditions.

The matching rewards established through Discovery auction qualification and the Confidence auction bonus lottery are specific to the Confidence auction. They do not automatically repeat in later phases.

---

## Current Status

**The Discovery auction is live on Ethereum Sepolia**, providing Academy's initial public testnet qualification environment.

The Discovery phase uses an extended participation period with minimum and maximum bidder requirements. Its objective is to establish sufficient community participation to qualify the campaign for progression.

**The Confidence auction is planned for Arbitrum One**, conditional on satisfying the Discovery phase's graduation requirements.

The planned Confidence auction incentive structure includes:

- **3% USDC bonus** calculated from settled Confidence auction proceeds.
- **Equivalent IRN bonus** calculated using the final clearing price.
- **5 billion IRN reserve** allocated first to the IRN bonus, with the remainder available for matching.
- **Proportional IRN matching** of qualifying Confidence auction allocations, up to 1:1.
- **Real-time unrealized calculations**, finalized through settlement.

Contract enforcement, lottery selection, reward distribution, and any applicable reserve limits must be finalized before the incentives are activated.

---

## Related Documentation

- [TradeSphere Academy](https://academy.tradesphere.org)
- [Explore the Gridiron Auction](https://academy.tradesphere.org/gridiron)
- [Architecture](architecture.md)
- [Auction Mechanics](auction.md)
- [Technology Stack](technology.md)
- [Bots & Scenarios](bots.md)
- [Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)
