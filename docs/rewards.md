# TradeSphere Academy — Rewards & Qualification

## Overview

**Gridiron: The Reckoning** is TradeSphere Academy's inaugural auction campaign, using the IRN token to demonstrate market-driven funding, token distribution, price discovery, and community participation.

The campaign progresses from testnet discovery to mainnet auctions, rewarding early participants who help establish the project's initial economy.

The first two auctions are particularly important:

- **01 — Discovery:** Participate on Ethereum Sepolia using test assets and establish eligibility for Confidence rewards.
- **02 — Confidence:** Participate in the first mainnet auction using real assets, with additional IRN incentives for eligible Discovery participants.

**Discovery establishes eligibility. Confidence requires commitment.**

Rewards depend on qualifying participation and settled purchases, not simply connecting a wallet or registering interest.

---

## The Reckoning Campaign

The Reckoning consists of five auction stages.

| Stage | Auction | Campaign Allocation | IRN |
|---|---|---:|---:|
| 01 | Discovery | 10% | 5 billion |
| 02 | Confidence | 15% | 7.5 billion |
| 03 | Momentum | 20% | 10 billion |
| 04 | Expansion | 25% | 12.5 billion |
| 05 | Peak | 30% | 15 billion |
| **Total** | | **100%** | **50 billion** |

The total IRN supply is **1 trillion tokens**, with **5% (50 billion IRN)** allocated to The Reckoning campaign.

### Discovery Allocation

Discovery operates on Sepolia using test assets.

Its 5 billion IRN campaign allocation is reserved for incentives associated with the subsequent Confidence auction rather than being sold for real funds during Discovery.

This reserve funds both the Confidence lottery bonus and participation rewards.

### Confidence Allocation

Confidence has a regular auction allocation of **7.5 billion IRN**.

An additional **5 billion IRN** is reserved for Discovery-related incentives distributed through Confidence.

| Allocation | IRN |
|---|---:|
| Confidence auction supply | 7.5 billion |
| Discovery incentive reserve | 5 billion |
| **Combined potential distribution** | **12.5 billion** |

The 5 billion IRN reserve is divided between the lottery bonus and participation rewards.

**Both incentives are funded from the same reserve. No additional IRN allocation is required.**

---

## 01 — Discovery

Discovery is the qualifying stage of The Reckoning.

It operates on **Ethereum Sepolia**, using test assets and actual blockchain transactions.

Discovery is more than a demonstration. It allows participants to experience the auction mechanism while establishing eligibility for potential rewards in Confidence.

### How to Participate

1. Connect a supported wallet to TradeSphere Academy.
2. Select the Sepolia network.
3. Obtain the test assets provided for Discovery participation.
4. Submit a qualifying auction bid.
5. Participate under the auction's published rules.

Academy's Discovery experience provides test quote tokens for participation without requiring users to purchase them with real funds.

Sepolia gas may still be required to authorize transactions.

### Qualification

**Connecting a wallet alone does not establish eligibility.**

Participants must submit a qualifying bid during Discovery.

The participating wallet address provides the connection between Discovery and Confidence.

Participants should retain access to the same wallet for the subsequent mainnet auction.

### Why Discovery Matters

Discovery serves several purposes:

- Introduces participants to Uniswap Continuous Clearing Auctions.
- Demonstrates actual on-chain bidding and price discovery.
- Exercises Academy's wallet, transaction, monitoring, and position interfaces.
- Validates auction execution under real testnet conditions.
- Establishes eligible participants for Confidence incentives.
- Helps determine whether sufficient interest exists to proceed to mainnet.

Progression to Confidence is conditional on sufficient demand and successful launch validation.

---

## 02 — Confidence

Confidence is the first mainnet auction of The Reckoning.

Unlike Discovery, participation requires real economic commitments.

Confidence introduces additional IRN incentives for participants who qualified through Discovery and return to make qualifying purchases.

### Eligibility Requirements

To receive Discovery participation rewards during Confidence, a participant must:

1. Have qualified through actual participation in Discovery.
2. Use the same wallet address in Confidence.
3. Submit a qualifying Confidence bid.
4. Complete a qualifying settled purchase.
5. Satisfy the campaign's purchase limits and eligibility requirements.

**No qualifying purchase, no rewards.**

Participating in Discovery alone does not entitle a wallet to an unconditional mainnet token distribution.

### Purchase Limits

The intended eligible settled-purchase range is:

| Parameter | Amount |
|---|---:|
| Minimum qualifying purchase | 100 USDC |
| Maximum eligible purchase | 5,000 USDC |

These limits define the intended purchase range for Confidence reward eligibility.

The applicable enforcement mechanism must ensure that participants cannot bypass campaign restrictions through direct smart contract interaction.

### Discovery Incentive Reserve

Confidence includes a **5 billion IRN reserve** established from Discovery's campaign allocation.

The reserve is distributed through two incentive mechanisms:

1. **Lottery Bonus:** Calculated first and deducted from the reserve.
2. **Participation Rewards:** Funded from the remaining reserve.

Both amounts can be projected dynamically during the auction and finalized using settlement results.

---

## Confidence Lottery Bonus

The Confidence lottery provides an additional IRN incentive associated with auction participation.

The bonus is funded directly from the 5 billion IRN Discovery reserve.

### Bonus Calculation

The bonus is calculated using an amount equivalent to **3% of Confidence's settled USDC proceeds**, converted into IRN at the auction's final clearing price.

**Formula:**

`Lottery Bonus (IRN) = (Settled USDC Proceeds × 0.03) / Final Clearing Price`

For example, if Confidence settles 100,000 USDC at a clearing price of 0.00005 USDC per IRN:

`Lottery Bonus = (100,000 × 0.03) / 0.00005`

**Lottery Bonus = 60,000,000 IRN**

The calculation establishes an IRN-denominated prize.

**No USDC is withheld or deducted from auction proceeds.** The 3% figure is used solely to determine the equivalent IRN amount.

### Reserve Accounting

The lottery bonus is allocated first, directly from the Discovery incentive reserve.

The remaining IRN becomes available for participation rewards.

**Formula:**

`Participation Reward Pool (IRN) = 5,000,000,000 - Lottery Bonus (IRN)`

Using the calculated lottery bonus above:

`Participation Reward Pool = 5,000,000,000 - 60,000,000`

**Participation Reward Pool = 4,940,000,000 IRN**

The combined lottery bonus and participation rewards cannot exceed the 5 billion IRN reserve.

### Live Bonus Estimates

Because clearing prices and proceeds evolve throughout the auction, Academy can calculate a projected lottery bonus using current auction values.

As the auction progresses:

- Estimated settlement proceeds change.
- The clearing price may change.
- The projected IRN lottery bonus changes.
- The remaining participation reward pool is recalculated.

These values are provisional until final settlement.

The lottery bonus must remain within the available reserve. Any applicable cap or exhaustion behavior will be specified in the final campaign rules.

### Winner Selection

The lottery's final participation requirements, winner-selection procedure, and distribution mechanics will be published before activation.

The winner-selection mechanism is separate from the calculation and funding of the prize.

---

## Discovery Participation Rewards

After reserving the projected lottery bonus, the remaining IRN is available to reward eligible Discovery participants who complete qualifying purchases in Confidence.

### Reward Pool

The participation reward pool is calculated as follows:

`Reward Pool (IRN) = 5,000,000,000 - Lottery Bonus (IRN)`

The pool changes as the projected lottery bonus changes throughout the auction.

### Reward Eligibility

Participation rewards require:

- A qualifying Discovery wallet.
- The same wallet participating in Confidence.
- A qualifying settled Confidence purchase.
- Compliance with the published purchase limits.

Rewards are associated with actual settled allocations, not simply submitted bids.

### Dynamic Reward Calculation

Academy is designed to calculate reward availability as the Confidence auction progresses.

Current clearing prices and provisional bid fills provide the basis for estimating qualifying purchases and associated IRN rewards.

As auction conditions change, projected individual rewards and the remaining available reward pool can be updated.

These projections remain subject to final clearing and settlement.

### Competitive Allocation

The participation reward reserve is finite.

The intended allocation approach is competitive rather than an unconditional proportional distribution across all Discovery participants.

Reward availability depends on qualifying purchases and the remaining reserve.

Detailed allocation priority, individual reward limits, and reserve-exhaustion rules will be published before Confidence.

**Qualification establishes the opportunity to earn rewards. It does not guarantee an allocation independent of actual participation and available supply.**

---

## Real-Time Incentive Accounting

The lottery bonus and participation rewards share one reserve and can be calculated together.

Academy can present the evolving incentive allocation as the Confidence auction progresses.

| Metric | Description |
|---|---|
| Discovery Reserve | Fixed 5 billion IRN incentive allocation |
| Projected Lottery Bonus | IRN equivalent of 3% of projected settled USDC proceeds |
| Available Reward Pool | Reserve remaining after the projected lottery bonus |
| Projected Participation Rewards | IRN associated with currently qualifying settled-purchase estimates |
| Remaining Unallocated Reserve | IRN not yet projected for either incentive |

### Calculation Sequence

1. Observe current clearing and settlement-related values.
2. Calculate the projected lottery bonus in IRN.
3. Deduct the projected bonus from the 5 billion IRN reserve.
4. Calculate projected participation rewards from qualifying purchases.
5. Update remaining reward availability.
6. Recalculate as auction conditions change.
7. Finalize the amounts using the completed auction's settlement results.

**Lottery bonus first. Participation rewards second. One reserve.**

This structure keeps the entire incentive program within its original campaign allocation.

---

## Auction Purchases vs. Incentives

The Reckoning distinguishes three economic components.

| Component | Description |
|---|---|
| **Auction Purchase** | IRN acquired through ordinary Confidence auction clearing |
| **Participation Reward** | Additional IRN earned by eligible Discovery participants through qualifying Confidence purchases |
| **Lottery Bonus** | Additional IRN prize calculated from Confidence settlement proceeds |

Ordinary auction purchases are governed by Uniswap CCA's on-chain clearing and settlement rules.

Additional rewards and bonuses are funded from the separate 5 billion IRN Discovery incentive reserve.

The total Confidence-related token distribution therefore remains within the combined 12.5 billion IRN allocation.

---

## Wallets, Transactions & Verification

Discovery and Confidence use different blockchain networks, but qualification is associated with the participant's wallet address.

| Stage | Network | Assets |
|---|---|---|
| Discovery | Ethereum Sepolia | Test assets |
| Confidence | Ethereum Mainnet | Real assets |

Using the same wallet address allows the campaign to associate qualifying Discovery activity with subsequent Confidence purchases.

### On-Chain Evidence

Auction participation produces observable blockchain transactions.

Qualification and reward calculations can be evaluated against actual bidding, clearing, and settlement information.

### Contract Enforcement

Economic eligibility conditions should be enforced through the appropriate on-chain mechanisms where necessary.

User interface validation alone is not sufficient to guarantee purchase limits or prevent direct contract interactions that bypass campaign-specific rules.

### Settlement-Based Accounting

Rewards are based on qualifying settled purchases.

A bid that is submitted but produces no qualifying settled allocation does not satisfy the Confidence participation reward requirement.

Current fills and clearing values support live projections, while final settlement establishes the authoritative results.

---

## Beyond Confidence

The Reckoning continues through three subsequent auctions:

- **03 — Momentum:** 10 billion IRN
- **04 — Expansion:** 12.5 billion IRN
- **05 — Peak:** 15 billion IRN

These stages continue the campaign's market-driven distribution of IRN.

Discovery qualification incentives are associated specifically with Confidence. They are not recurring reward allocations for every subsequent auction.

The broader objective is to establish an initial token economy, develop market participation, and support the Gridiron ecosystem.

## Current Status

The Reckoning's initial stages establish a progression from testnet qualification to mainnet participation.

Discovery provides the qualifying environment.

Confidence is the planned first mainnet auction, contingent on sufficient participation and successful validation.

The **5 billion IRN Discovery reserve** funds both the Confidence lottery bonus and participation rewards, with the lottery calculated first and the remaining reserve used for qualifying participant rewards.

The detailed winner-selection, reward-priority, distribution, and enforcement mechanisms will be finalized and published before Confidence activation.

Projected incentive amounts are not final until the auction's applicable settlement conditions have been satisfied.

---

## Related Documentation

- [Architecture](architecture.md)
- [Auction Mechanics](auction.md)
- [Technology Stack](technology.md)
- [Bots & Scenarios](bots.md)
- [Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)
