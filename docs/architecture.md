# TradeSphere Academy — Architecture

## Overview

TradeSphere Academy is a .NET-based platform for creating, configuring, testing, and operating on-chain token auctions using **Uniswap's Continuous Clearing Auction (CCA)** protocol.

Academy combines token and auction creation, project registration, scenario-driven execution, automated participants, blockchain integration, market visualization, and replay within a unified application.

Its purpose is to help projects establish their initial token economies through market-driven funding, distribution, price discovery, and community participation.

Academy operates independently of the broader TradeSphere organizational model. Projects retain ownership and control of their tokens, organizations, subscribers, and economic relationships.

**TradeSphere provides the infrastructure. Projects build their own economies.**

![TradeSphere Application Stack](../assets/academy-architecture.png)

*TradeSphere application stack — applications, core services, and supporting blockchain infrastructure.*

## Current Availability

Academy is operational, with public access initially focused on participating in existing auctions.

The underlying application includes additional creation, execution, and administrative capabilities that are currently restricted.

| Capability | Availability |
|---|---|
| Auction discovery and participation | Public |
| Wallet connection and on-chain bidding | Public |
| Live auction monitoring, token flow, and positions | Public |
| Auction settlement and claims | Supported through the auction lifecycle |
| Auction registration and creation | Implemented — restricted |
| New token creation and existing token integration | Implemented — restricted |
| Scenario design and configuration | Implemented — restricted |
| Test, Sim, and Live execution environments | Implemented — restricted configuration and administration |
| Automated participants | Implemented — restricted |
| Replay and result verification | Implemented — restricted |
| Auction administration | Implemented — restricted |
| General project access to creation tools | Planned following launch validation |
| TradeSphere organizational Activity integration | Future |

### Initial Launch Validation

We're putting Academy to work on our own projects first.

The initial campaign, **Gridiron: The Reckoning**, uses IRN tokenomics to validate the platform through real auction participation.

The first two auctions establish our initial release milestones:

- **01 — Discovery:** On-chain qualification and scenario validation using Ethereum Sepolia and test assets.
- **02 — Confidence:** The first mainnet auction, contingent on sufficient participation and interest during Discovery.

Successful completion of these auctions is the milestone for opening Academy's broader creation, scenario, and administrative capabilities to other projects.

The objective is to demonstrate the technology through actual execution before expanding public access.

---

## Application Architecture

Academy uses a server/browser architecture that separates application orchestration, blockchain monitoring, and transaction authorization.

### Blazor Server & .NET 10

Academy is built with **.NET 10, Blazor Server, and Fluent UI Blazor 5**.

The choice of Blazor reflects several architectural advantages:

- **C# across the application:** A common language for domain models, calculations, application services, execution logic, and interactive components.
- **Component-based architecture:** Reusable UI components for auction monitoring, bidding, positions, market metrics, visualizations, and administration.
- **Strongly typed domain models:** Consistent representations of auctions, registrations, configurations, scenarios, bids, and execution results.
- **Integrated .NET ecosystem:** Direct integration with Nethereum, application services, and supporting libraries.
- **Server-managed application state:** Centralized coordination, blockchain synchronization, and UI updates.
- **Shared blockchain monitoring:** Reduces redundant RPC requests from individual connected browsers.

The result is an architecture that combines component-based UI development with blockchain services and scenario-driven execution in a predominantly C# application.

### Blockchain Integration & Transaction Execution

Academy uses **Nethereum** and **Reown** for Ethereum-compatible blockchain integration and transaction execution.

The execution path depends on the operation, its context, and the account responsible for authorization.

| Operation | Execution |
|---|---|
| Read-only blockchain operations | Nethereum |
| Participant bidding | Client-side wallet authorization through Reown |
| Participant exiting and claiming | Client-side wallet authorization through Reown |
| System bidding | System-managed transactions through Nethereum |
| System exiting and claiming | System-managed transactions through Nethereum |
| Auction creation | User-authorized or system-managed |
| Administrative operations | User-authorized or system-managed |

This architecture supports both direct human participation and automated execution.

Connected users authorize transactions through their own wallets. System actors, including automated bidders, can execute transactions through managed accounts.

The important distinction is **who authorizes the transaction**, rather than whether the operation is initiated by the browser or server.

Uniswap CCA smart contracts remain authoritative for on-chain auction execution, clearing, and settlement.

### Application Services

Academy's application services coordinate:

- Auction registration, configuration, and deployment
- Blockchain state monitoring and synchronization
- Contract interaction and transaction execution
- Auction metrics, checkpoints, and clearing calculations
- Bid and position management
- Scenario execution and automated participants
- Reconstruction, replay, and result verification

Application-side calculations support monitoring and analysis without replacing authoritative smart contract execution.

---

## Auction Registration & Creation

Academy uses an **AuctionRegistration** model to organize project information, auction creation parameters, and execution strategies.

Each registration contains three primary elements:

| Component | Responsibility |
|---|---|
| **Profile** | Project and auction identity, description, and presentation |
| **Config** | Token information, supply, pricing, contract parameters, and creation settings |
| **Scenario** | Allocation, distribution, flow, rounds/steps, duration, and execution behavior |

This separation allows projects to evaluate alternative auction strategies without tying their identity or token information to a particular execution configuration.

### Token Creation & Integration

Academy supports creating new tokens or using existing tokens when configuring auctions.

Projects can establish token supply, select assets, and configure the associated auction parameters.

Token and auction creation are currently available through restricted administrative functionality.

### Registration & Project Discovery

Registration also establishes the foundation for Academy's future project and token discovery platform.

The long-term direction is a **community-driven registry**, where independent projects can introduce their tokens and make their markets discoverable.

TradeSphere does not intend to operate as a central authority deciding which projects or tokens deserve recognition.

The objective is to make information, participation, and observable economic activity available so participants can make their own decisions.

**Trust is earned through transactions, participation, and demonstrated behavior—not bestowed through platform approval.**

Public registration and community discovery remain future capabilities. The current registration system supports internal creation and management.

### Auction Configuration

Auction configuration contains the parameters required to create an on-chain auction, including:

- Base and quote tokens
- Token allocation and supply
- Floor price and pricing parameters
- Auction start and end times
- Recipient addresses
- Contract configuration and deployment parameters

These parameters work alongside the selected scenario to establish the auction's economic and execution characteristics.

### Auction Creation

Configured auctions can be deployed through Academy's blockchain integration services.

Creation can be performed through user-authorized or system-managed transactions, depending on the operating context.

Auction creation and administration remain restricted during the initial launch campaign.

---

## Scenario Design & Execution

**Auction scenarios allow projects to design and evaluate token distribution strategies before committing to a live launch.**

Determining how much supply to release, how quickly to release it, and over what period can have a substantial effect on auction behavior.

Academy provides execution environments for evaluating these decisions.

### Scenario Parameters

| Parameter | Purpose |
|---|---|
| **Allocation** | Total token supply committed to an auction |
| **Distribution** | How that supply is distributed over time |
| **Flow** | Rate at which tokens become available |
| **Rounds / Steps** | Intervals with defined duration and distribution characteristics |
| **Duration** | Total auction period |
| **Floor Price** | Minimum auction clearing price |
| **Participants** | Bidder populations, strategies, and competitive behavior |

Different scenarios can be evaluated to observe their effects on token allocation, clearing prices, bidding competition, and supply consumption.

Testing helps determine which configurations best serve a project's objectives under the conditions evaluated.

### Execution Environments

Academy supports three execution environments: **Test, Sim, and Live**.

| Environment | Execution | Capabilities |
|---|---|---|
| **Test** | Mock, off-chain | Configurable speed, automated bidders, replay, scenario evaluation |
| **Sim** | On-chain, testnet | Real testnet transactions, test assets, automated bidders, replay |
| **Live** | On-chain, mainnet | Real assets, market participation, replay |

### Test — Mock Execution

Test provides an off-chain environment for evaluating auction designs without deploying smart contracts or executing blockchain transactions.

Scenarios can operate at configurable speeds, allowing long-running auction configurations to be evaluated in compressed time.

Test supports:

- Mock auction execution
- Configurable execution speed
- Automated bidders and behavioral strategies
- Evaluation of distribution and flow
- Clearing and allocation calculations
- Replay and result analysis

Projects can compare different configurations and refine their scenarios before moving to on-chain execution.

A Test scenario can be **cloned into Sim** for testnet validation.

### Sim — Testnet Execution

Sim uses real blockchain execution on a test network such as **Ethereum Sepolia**.

It exercises actual smart contract operations using test assets, allowing projects to evaluate the behavior of a configured auction under blockchain conditions.

Sim supports:

- Testnet auction deployment and execution
- Real blockchain transactions with test assets
- Automated bidders
- Blockchain monitoring and clearing calculations
- Settlement and claims
- Replay and verification

**Gridiron's Discovery auction operates in this environment**, providing an opportunity for participants to experience actual on-chain bidding without committing real purchase funds.

A validated Sim scenario can be **cloned into Live** for mainnet deployment.

### Live — Mainnet Execution

Live operates against mainnet smart contracts using real assets and transactions.

Participants submit bids, compete for allocations, and settle according to the auction's on-chain rules.

Live supports:

- Mainnet auction execution
- User-authorized and system-managed transactions
- Real-time monitoring and visualization
- Position management
- Settlement and claims
- Replay and result verification

### Scenario Progression

**Test → Sim → Live**

Scenario cloning supports progression between execution environments without requiring projects to redesign their auction strategy from the beginning.

Network-specific addresses, assets, and deployment parameters can be adjusted as an auction advances.

Each environment provides a different level of validation:

- **Test:** Does the scenario behave as intended under mock conditions?
- **Sim:** Does the scenario execute correctly using actual smart contracts and blockchain transactions?
- **Live:** How does the scenario perform with real participants and economic commitments?

This progression enables a more disciplined approach to evaluating auction strategies and launch configurations.

### Automated Participants

Academy supports automated bidders with configurable behavior.

Bots can participate in Test and Sim environments to evaluate competition, auction pressure, price movement, and allocation behavior.

System-managed bidding capabilities also support automated participation in Live environments.

Automated participants are useful for validating scenarios, reproducing market conditions, and stress-testing execution behavior.

### Replay & Verification

Academy can reconstruct and replay auction execution.

Replay does more than reproduce a transaction history. It re-evaluates auction calculations, including clearing and allocation results, so reconstructed outcomes can be compared with recorded execution.

Replay is available across **Test, Sim, and Live**, providing a common mechanism for analysis, debugging, and verification.

Scenario creation, execution controls, bots, and replay are implemented capabilities but are not currently exposed through Academy's public participant interface.

---

## Auction Mechanics & Participation

Academy uses **Uniswap Continuous Clearing Auctions** for price discovery and token distribution.

Participants connect their wallets, submit bids with spending limits and price constraints, and compete for token allocations as supply becomes available.

**The bid itself represents an economic commitment.**

No additional organizational staking mechanism is required to participate.

### Continuous Clearing

Tokens are released according to the configured auction distribution schedule.

As participants bid for available supply, clearing prices and provisional allocations evolve.

Academy monitors and visualizes this behavior, including clearing prices, bid competition, token flow, and participant positions.

Final execution and settlement are determined by the underlying CCA smart contracts.

### Rounds & Steps

Academy organizes token distribution into configurable **rounds (steps)**, reflecting the interval-based progression of the auction.

Each round or step can represent a different portion of the auction's duration and supply distribution, producing different token flow rates.

Academy's flow visualization helps participants observe the current distribution rate, remaining supply, and changes in auction pressure.

Rounds and steps describe the auction's distribution schedule; they are not independent auctions.

### Positions & Settlement

Academy presents participant positions, including bids, committed amounts, current allocations, and settlement results.

Allocations remain provisional while an auction is active and can change as competitive bids affect clearing.

Participants can exit or claim according to the auction's state and smart contract rules.

---

## Participation, Discovery & Trust

Academy is designed around open market participation rather than centralized approval.

Projects can create or bring tokens, configure auction scenarios, and establish markets through competitive price discovery.

The platform does not determine what a token is worth or declare a project trustworthy merely because it appears in a registry.

Instead, transactions, bids, allocations, settlement outcomes, and continued participation provide observable evidence of economic behavior.

A community-driven discovery model can use that information to help participants evaluate projects and markets.

TradeSphere's broader confidence, consensus, and reputation metrics are under development and will eventually expand these capabilities.

**Trust is earned through what participants do, not what they say.**

---

## Relationship to TradeSphere

Academy is a standalone application and does not require projects or participants to adopt TradeSphere's broader organizational architecture.

The TradeSphere Engine provides an extended model built around:

- **Organizations:** Independent economic and operational groups
- **Actors:** Human and autonomous participants
- **Activities:** Structured environments for participation and economic operations
- **Directives:** Coordinated decisions, signals, and commitments
- **Actions:** Participant behavior and execution within activities

Supporting services include Platform, Sphere, Aura, Flow, and Synergy.

Future integration will allow Academy auctions to operate within the broader **Activity → Directive → Action** model, with auction bids and transactions contributing to organizational activities, confidence, consensus, and reputation metrics.

This integration is an extension, not a dependency.

Projects retain their independence, assets, subscribers, and economic relationships whether or not they participate in the broader TradeSphere ecosystem.

**Academy provides the launch infrastructure. Projects decide what comes next.**

---

## Technology

Academy's principal technologies include:

| Technology | Role |
|---|---|
| **.NET 10 / C#** | Application services, domain models, execution, and calculations |
| **Blazor Server** | Interactive application and server-managed UI |
| **Fluent UI Blazor 5** | Reusable application components |
| **Nethereum** | Ethereum blockchain and smart contract integration |
| **Reown** | Client-side wallet connection and transaction authorization |
| **Uniswap CCA** | Continuous clearing auction smart contracts |
| **Ethereum / Sepolia** | Mainnet and testnet execution |
| **Infura** | Blockchain RPC infrastructure |
| **Microsoft Azure** | Application hosting |
| **GitHub** | Source management and technical documentation |

---

## Design Principles

**Market-driven price discovery.** Auction outcomes emerge from participant bids and protocol rules, not prices assigned by TradeSphere.

**Independent projects.** Organizations retain control of their tokens, communities, and economies.

**Flexible transaction execution.** Both connected users and system-managed actors can execute supported contract operations.

**Scenario-driven design.** Auction configurations can be evaluated through mock execution and actual blockchain environments.

**Progressive validation.** Test, Sim, and Live provide a path from economic experimentation to mainnet operation.

**Reconstruction and verification.** Auction executions can be replayed and recalculated for analysis and validation.

**Open discovery.** Registration is intended to evolve toward community-driven project and token discovery rather than centralized approval.

**Composable infrastructure.** Academy uses established blockchain protocols and extends them with application services, automation, and market visualization.

---

## Related Documentation

- [Auction Mechanics](auction.md)
- [Technology Stack](technology.md)
- [Bots & Scenarios](bots.md)
- [Rewards & Qualification](rewards.md)
- [Uniswap CCA Documentation](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)
- [Fluent UI Blazor](https://www.fluentui-blazor.net/)
