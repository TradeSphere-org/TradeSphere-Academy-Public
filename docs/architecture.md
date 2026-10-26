# TradeSphere Academy — Architecture

## Overview

TradeSphere Academy is a .NET-based application for creating, configuring, testing, and operating on-chain token auctions using **Uniswap's Continuous Clearing Auction (CCA)** protocol.

Academy combines token and auction creation, project registration, scenario-driven execution, blockchain integration, market visualization, live monitoring, and replay.

Academy can also connect to existing Uniswap CCA auctions by contract address, including auctions deployed independently of Academy.

Its purpose is to help projects establish their initial token economies through market-driven funding, distribution, price discovery, and community participation.

Academy operates independently of TradeSphere's broader organizational model. Projects retain ownership and control of their tokens, organizations, participants, and economic relationships.

**TradeSphere provides the infrastructure. Projects build their own economies.**

![TradeSphere Application Stack](../assets/academy-architecture.png)

*TradeSphere application stack — applications, core services, and supporting infrastructure.*

---

## Current Availability

Academy is operational as a standalone application, with public access focused on participating in existing auctions.

Its creation, scenario execution, external auction loading, and administrative capabilities are implemented but currently restricted.

| Capability | Availability |
|---|---|
| Auction discovery and participation | Public |
| Wallet connection and on-chain bidding | Public |
| Auction monitoring, token flow, and positions | Public |
| Auction settlement and claims | Supported through the auction lifecycle |
| Auction registration and creation | Implemented — restricted |
| New token creation and existing token integration | Implemented — restricted |
| Loading existing CCA contracts by address | Implemented — restricted |
| External auction live monitoring | Implemented — restricted |
| External auction reconstruction and replay | Implemented — restricted |
| Scenario configuration | Implemented — restricted |
| Test, Sim, and Live environments | Implemented — restricted administration |
| Automated test bots | Implemented — restricted |
| Replay and result verification | Implemented — restricted |
| Auction administration | Implemented — restricted |
| General project access to creation tools | Planned |
| Unified Academy Auction campaign orchestration | Planned |
| TradeSphere Activity integration | Future |

### Initial Launch Validation

Academy is being validated through TradeSphere's own projects before expanding access.

The first featured project, **Gridiron**, introduces the IRN token economy through **The Reckoning**, a five-phase campaign.

The first two phases establish the initial milestones:

- **01 — Discovery:** The qualification phase begins with the Discovery auction
  on Ethereum Sepolia, using test USDC and test IRN. An extended participation
  window allows time to attract bidders, with minimum and maximum participation
  requirements defining the qualification criteria for advancing to the
  Confidence phase.
- **02 — Confidence:** The initial funding phase introduces the Confidence
  auction on Arbitrum One, using real USDC to establish market demand,
  discover pricing, and raise capital.

The Confidence auction is designed for participants making qualifying purchases between 100 and 5,000 USDC, with matching IRN rewards and a bonus lottery.

Successful completion of these phases is the intended milestone for expanding access to Academy's creation and scenario capabilities.

The objective is to demonstrate the technology through actual execution before opening it to additional projects.

**[Explore the Gridiron Auction](https://academy.tradesphere.org/gridiron)**

---

## Application Architecture

Academy uses a server/browser architecture that separates application orchestration, blockchain monitoring, and transaction authorization.

### Blazor Server & .NET 10

Academy is built with **.NET 10, Blazor Server, and Fluent UI Blazor 5**.

The application uses strongly typed C# domain models and services for auction registration, configuration, execution, calculations, and presentation.

Blazor Server provides:

- Component-based interfaces for auctions, bids, positions, and market visualization.
- Direct integration with .NET domain models and application services.
- Centralized blockchain synchronization and auction calculations.
- Shared application state and updates for connected participants.
- Reduced redundant RPC requests compared with independent browser polling.

JavaScript and Reown handle browser wallet operations.

The current architecture does not require a Blazor WebAssembly client.

### Blockchain Integration & Transaction Execution

Academy uses **Nethereum** and **Reown** for Ethereum-compatible blockchain integration.

The transaction path depends on the account responsible for authorization.

| Operation | Execution |
|---|---|
| Read-only blockchain operations | Nethereum |
| Participant bidding | Reown / connected wallet |
| Participant exiting and claiming | Reown / connected wallet |
| System-managed bidding | Nethereum |
| System-managed exits and claims | Nethereum |
| Auction creation | User-authorized or system-managed |
| Administrative operations | User-authorized or system-managed |

Connected participants authorize transactions through their own wallets.

System-managed operations use accounts controlled by the appropriate application services.

**The distinction is who authorizes the transaction, not which contract is being accessed.**

Uniswap CCA smart contracts remain authoritative for auction execution, clearing, and settlement.

### Application Services

Academy's application services coordinate:

- Auction registration, configuration, and deployment
- Existing CCA contract loading and integration
- Contract interaction and transaction execution
- Blockchain monitoring and synchronization
- Auction checkpoints and clearing calculations
- Bid and position management
- Scenario execution and controlled test bots
- Reconstruction, replay, and verification

Application-side calculations support monitoring and analysis without replacing authoritative on-chain execution.

For the technologies and transaction architecture, see [Technology Stack](technology.md).

---

## Academy Auction Campaign Model

TradeSphere Academy provides infrastructure for projects to create, operate, and manage on-chain token auctions using Uniswap Continuous Clearing Auctions (CCA).

Projects may use a single auction to launch a token market or organize multiple auctions into a broader campaign. Each project defines its own objectives, economic strategy, participation rules, and progression requirements.

**Academy provides the infrastructure. Projects define their campaigns.**

### Campaign Structure

**Campaign → Phase → Auction Attempt → Auction Stages**

| Component | Responsibility |
|---|---|
| **Campaign** | Project objectives, economic allocation, and progression plan |
| **Phase** | A milestone with defined objectives and graduation requirements |
| **Auction Attempt** | One independently executed CCA intended to achieve a phase objective |
| **Scenario** | A reusable strategy selected for an attempt, including distribution and participation behavior |
| **Auction Stages** | Token-release intervals defining relative supply distribution and flow rates within an auction |

The scenario is selected for an auction attempt; it is not permanently tied to a campaign phase. Each attempt has its own configuration, execution, clearing, settlement, exits, and claims.

The structure is descriptive, not a requirement for every project. A simple campaign can consist of one auction without elaborate phases or repeated attempts.

### Auction Attempts & Scenarios

A phase may involve multiple auction attempts before meeting its graduation requirements. An unsuccessful attempt does not necessarily mean an unsuccessful phase.

Based on the results, a project may repeat the same scenario, adjust the configuration of a subsequent attempt, or choose a different scenario. A reusable scenario can also be applied in other phases or projects.

Changes to strategy or configuration apply to future attempts. The deployed Uniswap CCA contract remains authoritative for the terms and outcome of each active auction.

### Graduation & Campaign Progression

A phase defines *what the project is trying to achieve*. Its graduation requirements may include minimum participation, funding objectives, or other published measures.

An auction attempt supplies evidence of progress toward those requirements. A project can evaluate an unsuccessful attempt and decide whether another is appropriate under its campaign rules.

Only after the phase satisfies its graduation requirements does the campaign advance to its next objective. Each attempt retains its own historical results rather than being overwritten by a later execution.

### Gridiron — The Reckoning

Gridiron demonstrates Academy's approach through **The Reckoning**, a five-phase strategy to establish the IRN market, develop liquidity, and support continued project growth.

| Phase | Objective |
|---|---|
| **01 — Discovery** | Establish community participation and qualification |
| **02 — Confidence** | Introduce real capital, discover market pricing, and establish initial funding |
| **03 — Momentum** | Continue controlled token distribution and market development |
| **04 — Expansion** | Broaden participation, capital formation, and liquidity |
| **05 — Peak** | Complete the campaign's planned distribution |

The Discovery phase begins with the Discovery auction on Ethereum Sepolia, using test USDC and test IRN. An extended participation window allows time to attract bidders, with minimum and maximum bidder requirements defining qualification for progression to the Confidence phase.

The Confidence phase introduces the Confidence auction on Arbitrum One, using real USDC to establish market demand, discover prices, and raise capital.

A phase can involve more than one auction attempt, and a subsequent attempt can use a different scenario or adjusted configuration. **The Reckoning is Gridiron's strategy, not a mandatory Academy campaign template.**

### Market Development & Capital Formation

Projects may need funding at different points in their development. Traditional arrangements include private token sales, OTC agreements with investors or institutions, exchange arrangements, and liquidity providers.

Academy provides another mechanism: competitive on-chain auctions that allow participants to bid under published rules, helping establish a market price and allocate tokens. These auctions can serve some of the economic purposes of negotiated token sales without themselves being private OTC transactions.

An auction may support an initial launch, further capital formation, or continued token distribution as a project develops. It does not replace exchanges, market makers, liquidity pools, or private agreements.

Following successful graduation of the Confidence phase, Gridiron intends to establish its initial Uniswap liquidity pool. Subsequent phases may contribute assets to existing liquidity and project treasury reserves, allowing market development to progress alongside additional funding opportunities.

### Relationship to TradeSphere Campaigns

TradeSphere's broader Activity model includes **CampaignActivity**, **CampaignDirectives**, and individual **AuctionActivities**. Directives can coordinate scheduling and progression, including timing, confidence, and consensus.

A similar pattern applies to Gridiron's tournament model, where tournament coordination organizes individual game activities.

The public campaign, phase, and attempt vocabulary describes a project's progression; it does not require Academy users to adopt or understand TradeSphere's internal Activity model. Academy can operate independently while remaining compatible with future integration.

### Implementation Status

Individual CCA creation, execution, scenario evaluation, monitoring, and replay are implemented. Auction creation, scenario administration, and replay currently remain restricted to authorized users.

Unified multi-phase orchestration, cumulative campaign state, adaptive scheduling, and automated graduation management are planned. They can be introduced without replacing the underlying Uniswap CCA contracts.

For campaign behavior, auction stages, bidding, and settlement, see [Auction Mechanics](auction.md).

---

## Auction Registration & Creation

![TradeSphere Academy — Auction Registration](../assets/academy-registration.png)

*Academy's registration workflow for project identity, token configuration, and auction creation. Currently restricted to administrative use.*

Academy organizes project and auction creation through an **AuctionRegistration** model.

Each registration contains three primary components:

| Component | Responsibility |
|---|---|
| **Profile** | Project identity, description, and presentation |
| **Config** | Token information, supply, pricing, duration, contract parameters, and deployment configuration |
| **Scenario** | Distribution strategy, token flow, stages, and execution behavior |

This separation allows a project's identity, auction configuration, and execution strategy to evolve independently.

### Profile

The Profile contains the descriptive information used to identify and present a project and its auction.

It provides the foundation for future project discovery without requiring a project to adopt TradeSphere's organizational model.

### Config

Config defines the auction's economic and contract parameters.

These include:

- Base and quote tokens
- Token supply and auction allocation
- Floor price and pricing parameters
- Auction duration, start, and end times
- Claim timing
- Minimum funding requirements
- Recipient addresses
- Contract deployment settings

**Duration and Floor Price are configuration parameters, not properties of the Scenario.**

Config establishes the operating constraints under which the auction executes.

### Scenario

Scenario defines how the configured auction operates over time.

It includes:

- Token distribution strategy
- Supply allocation across auction stages
- Token flow rates
- Stage structure and relative timing
- Automated test bot populations and behavioral assignments
- Execution and participation rules used for scenario evaluation

The Scenario works within the boundaries established by Config, including the configured auction duration and floor price.

This allows different distribution and participation strategies to be tested without changing the project's identity or duplicating contract configuration.

### Token Creation & Integration

Academy supports creating new tokens and integrating existing tokens.

Projects can configure token and auction contracts through the registration workflow.

Token creation and auction deployment are implemented but currently restricted to administrative use.

### Registration & Project Discovery

Registration provides the foundation for a future community-driven token and project registry.

The intended model allows independent projects to introduce their tokens and make their markets discoverable without requiring centralized approval of their economic value.

Participants can evaluate projects using observable activity, market participation, and transaction history.

Public registration and community discovery remain future capabilities.

**Trust is earned through transactions, participation, and demonstrated behavior—not bestowed through platform approval.**

---

## Existing Uniswap CCA Integration

Academy is not limited to auctions created through its registration and deployment workflows.

It can load existing Uniswap CCA auctions directly using their deployed contract addresses, including auctions created independently of Academy.

This provides an additional path for monitoring, analyzing, and replaying CCA execution.

### Contract-Based Loading

Academy can connect to an existing CCA contract and reconstruct its configuration and execution state from blockchain data.

The application uses its existing domain models, Nethereum services, and calculation engine to represent the loaded auction.

The auction does not need to have been originally deployed through Academy.

### Live Monitoring

Once loaded, an existing auction can be monitored as it progresses.

Academy provides:

- Auction configuration and distribution schedule
- Live clearing prices and token flow
- Bids and participant positions
- Blockchain checkpoints and execution progress
- Auction state, settlement, and allocation calculations

Centralized blockchain monitoring supports a consistent application state while reducing redundant RPC activity.

### Reconstruction & Replay

Academy can reconstruct an auction's execution using blockchain records and checkpoints.

Replay allows the calculation engine to evaluate historical auction behavior, including clearing prices, token distribution, bid competition, and allocations.

Recorded results can be compared with reconstructed calculations to support technical analysis and verification.

### Current Availability

**Existing CCA loading, live monitoring, reconstruction, and replay are implemented capabilities currently restricted to administrators.**

They extend Academy beyond auction creation into a broader operational and analytical environment for Uniswap CCA.

[Detailed Auction Mechanics](auction.md)

---

## Scenario Execution Architecture

Academy's scenario executor supports evaluating auction behavior before committing real assets.

The same general execution model operates across three environments.

| Environment | Execution | Purpose |
|---|---|---|
| **Test** | Mock, off-chain | Accelerated execution and scenario evaluation |
| **Sim** | On-chain testnet | Contract validation using test assets |
| **Live** | Arbitrum One mainnet | Real auction execution and economic commitments |

Scenarios can be cloned from **Test → Sim → Live**, with network-specific assets, contract addresses, and deployment configuration applied as appropriate.

### Controlled Test Bots

Academy uses controlled test bots to exercise auction execution under different bidding conditions.

Its behavioral framework includes bidding strategies, Myers-Briggs personality profiles, temperaments, and quantitative behavioral biases.

These bots are part of Academy's testing infrastructure, not independent external Agents.

System-managed transactions are executed through Nethereum where blockchain interaction is required.

### Replay & Verification

Academy can reconstruct auction execution and compare its calculations against recorded results.

Replay supports analysis of clearing, allocations, checkpoints, and settlement across Test, Sim, and Live.

Scenario administration, bot execution, and replay are implemented but remain restricted to administrative use.

For scenario design, behavioral modeling, and execution details, see [Test Bots & Scenarios](bots.md).

---

## Relationship to TradeSphere

Academy is a standalone application. It does not require projects or participants to adopt TradeSphere's broader organizational architecture.

The TradeSphere Engine provides a larger participation model built around:

| Component | Responsibility |
|---|---|
| **Organizations** | Independent economic and operational groups |
| **Actors** | Human and automated participants |
| **Activities** | Structured environments for participation |
| **Directives** | Coordinated decisions, signals, and commitments |
| **Actions** | Participant behavior and execution |

Supporting services include **Platform Service, Sphere Service, Aura, Flow Service, and Synergy Service**.

### Existing TradeSphere Capabilities

TradeSphere already has operational scenarios and bots executing **Ideas, Missions, and Games**.

These capabilities are part of its existing Activity framework.

Academy extends the same general scenario-driven approach with specialized auction execution and more sophisticated behavioral models.

The enhanced behavioral framework can be integrated into TradeSphere's existing bots without redesigning the scenario infrastructure.

### Planned Integration

Future integration will allow Academy auctions to operate within TradeSphere's broader **Activity → Directive → Action** model.

Auction activity can then contribute to organizational participation, confidence, consensus, and reputation systems.

This integration is an extension, not a dependency.

Projects retain ownership and control of their tokens, assets, participants, and economic relationships regardless of their participation in the broader TradeSphere ecosystem.

**Academy provides the launch infrastructure. Projects decide what comes next.**

---

## Design Principles

**Independent projects.** Projects retain control over their assets, communities, and economic relationships.

**Established protocols.** Use Uniswap CCA for authoritative on-chain auction mechanics rather than developing an unnecessary replacement.

**Separation of concerns.** Keep project identity, auction configuration, scenario behavior, and campaign orchestration distinct.

**Flexible authorization.** Support connected-wallet participation and system-managed execution through appropriate accounts.

**Scenario-driven validation.** Evaluate auction configurations through mock execution and real blockchain environments.

**Observable execution.** Support monitoring, reconstruction, and replay for understanding and verifying auction behavior.

**External CCA compatibility.** Allow independently deployed Uniswap CCA auctions to be loaded, monitored, and analyzed without requiring Academy-based deployment.

**Composable infrastructure.** Build reusable services and domain models that can extend into the broader TradeSphere platform.

---

## Related Documentation

- [TradeSphere Academy](https://academy.tradesphere.org)
- [Explore the Gridiron Auction](https://academy.tradesphere.org/gridiron)
- [Auction Mechanics](auction.md)
- [Technology Stack](technology.md)
- [Test Bots & Scenarios](bots.md)
- [Rewards & Qualification](rewards.md)
- [Uniswap CCA Documentation](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)
- [Fluent UI Blazor](https://www.fluentui-blazor.net/)