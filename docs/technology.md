# TradeSphere Academy — Technology Stack

## Overview

TradeSphere Academy is built on **.NET 10, Blazor Server, Fluent UI Blazor 5, Nethereum, Reown, and Uniswap Continuous Clearing Auctions (CCA)**.

The architecture combines a C# application stack with Ethereum smart contracts, connected wallets, automated execution, and real-time market visualization.

Rather than developing a proprietary auction protocol, Academy builds on Uniswap CCA and extends its capabilities through configuration, scenario execution, automation, monitoring, and replay.

## Core Technologies

| Technology | Role |
|---|---|
| **.NET 10 / C#** | Application services, domain models, auction calculations, and execution |
| **Blazor Server** | Interactive application UI and server-managed state |
| **Fluent UI Blazor 5** | Reusable interface components and design system |
| **Nethereum** | Ethereum contract integration, RPC operations, and managed transactions |
| **Reown** | Browser wallet connectivity and user-authorized transactions |
| **Uniswap CCA** | On-chain auction execution and continuous price discovery |
| **Ethereum** | Mainnet auction execution |
| **Sepolia** | Testnet auction execution and validation |
| **Infura** | Blockchain RPC connectivity |
| **Microsoft Azure** | Application hosting |
| **GitHub** | Source management and technical documentation |

## .NET 10 & C#

C# is used throughout Academy's application architecture, including:

- Domain models and application services
- Auction registration and configuration
- Scenario execution and automated participants
- Fixed-point price and token calculations
- Blockchain integration
- Interactive UI components
- Replay and result verification

Using a shared language across these responsibilities allows business logic, execution models, and application components to integrate without requiring separate implementations in multiple programming languages.

### Strongly Typed Domain Models

Academy's domain models represent auction configurations, registrations, scenarios, bids, positions, and execution states.

These models are shared throughout the application services and UI components.

The approach is particularly useful for blockchain applications where token decimals, large integer values, fixed-point prices, and contract parameters require careful handling.

## Blazor Server

Academy uses Blazor Server for its interactive web application.

The server maintains the application model and coordinates blockchain state monitoring, auction calculations, and UI updates.

### Why Blazor?

Several characteristics influenced the architecture:

**Component-based development**

Auction interfaces contain many reusable elements, including metrics, bidding controls, positions, status indicators, and market visualizations.

Blazor supports building these as composable C# components.

**Integration with application services**

UI components work directly with the application's strongly typed .NET models and services.

**Centralized blockchain monitoring**

Academy can monitor blockchain state through shared application services rather than requiring every connected browser to independently query RPC providers.

**C# application development**

The same language and development environment support application logic, blockchain integration, automated execution, and presentation.

JavaScript remains available where browser-specific functionality is required.

![TradeSphere Academy — Application Interface](../assets/academy-overview.png)

*Academy's Blazor Server application, built with .NET 10 and Fluent UI Blazor 5.*

## Fluent UI Blazor 5

Academy uses **Fluent UI Blazor 5** for its application component framework.

Fluent components support interactive controls, navigation, dialogs, data presentation, and forms.

Academy combines these components with its own layouts, auction-specific controls, and visualizations.

The objective is to provide a consistent application interface while retaining the flexibility required for specialized market functionality.

Official project: [Fluent UI Blazor](https://www.fluentui-blazor.net/)

## Nethereum

Nethereum provides Academy's .NET integration with Ethereum-compatible networks.

It supports contract interaction, blockchain queries, transaction construction, and managed account execution.

### Read Operations

Academy uses Nethereum for blockchain monitoring and read-only contract operations, including auction configuration, state, bids, checkpoints, and settlement information.

### Managed Transactions

Nethereum also supports system-managed operations, including:

- Auction and contract creation
- Administrative transactions
- Automated bidding
- Bid exits
- Token and funds claims

These transactions are executed by the appropriate managed accounts.

### Contract Models & Numeric Handling

Ethereum contract values frequently use integer representations with explicit decimal scaling.

Academy provides conversion and calculation utilities for token units and Uniswap CCA's fixed-point price representations, including Q96 values.

These calculations are used for contract communication, auction monitoring, scenario execution, and replay.

Official project: [Nethereum](https://nethereum.com/)

## Reown & Wallet Connectivity

Academy uses **Reown** for browser-based wallet connectivity and participant-authorized transactions.

Connected participants can:

- Connect supported wallets
- Select or switch networks
- Authorize token allowances
- Submit bids
- Exit eligible bids
- Claim settlement balances

Wallet authorization remains under the participant's control.

Reown complements Nethereum rather than replacing it.

The application selects the appropriate transaction path based on whether an operation is user-authorized or system-managed.

Official project: [Reown](https://reown.com/)

## Uniswap Continuous Clearing Auctions

Academy uses Uniswap CCA smart contracts for on-chain token distribution and price discovery.

The protocol provides the underlying auction mechanics, including competitive bidding, clearing, and settlement.

Academy contributes the surrounding application infrastructure:

- Auction registration and configuration
- Contract deployment and management
- Scenario design and evaluation
- Test, Sim, and Live execution
- Automated participants
- Auction monitoring and visualization
- Bid and position management
- Replay and verification

Uniswap CCA determines authoritative on-chain auction behavior. Academy provides tools to configure, operate, and understand that behavior.

Official documentation: [Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)

## Blockchain Networks

Academy supports distinct execution environments.

| Environment | Network | Purpose |
|---|---|---|
| **Test** | Off-chain | Mock execution, accelerated scenarios, and evaluation |
| **Sim** | Sepolia / testnet | Actual smart contract execution using test assets |
| **Live** | Mainnet | Real auction transactions and market participation |

Scenarios can be cloned from Test to Sim and from Sim to Live.

Network-specific assets, addresses, and contract configuration are applied when moving between environments.

## Execution & Automation

Academy's execution capabilities support configurable scenarios, automated participants, and replay.

### Scenario Execution

Scenarios define auction allocation, distribution, flow, rounds or steps, duration, pricing, and participant behavior.

Test scenarios can execute at configurable speeds without blockchain transactions.

Sim and Live scenarios coordinate execution with actual blockchain networks.

### Automated Participants

Automated bidders can execute under configured behavioral strategies.

System bidding uses managed accounts and Nethereum for blockchain transactions when operating on-chain.

Bots provide a practical method for evaluating auction behavior, competition, and calculation accuracy.

### Replay

Auction execution can be reconstructed and replayed across Test, Sim, and Live environments.

Replay recalculates auction results and supports comparison with recorded execution.

These capabilities are currently restricted to administrative use.

## Hosting & Operations

Academy is hosted using Microsoft Azure infrastructure.

The application coordinates server-managed UI sessions, backend services, and blockchain RPC connectivity.

Infura provides Ethereum network access for contract queries and transaction operations.

The architecture centralizes blockchain observation where practical to reduce redundant network requests from connected participants.

## Public Availability

The public Academy application currently supports auction discovery, wallet connection, bidding, monitoring, positions, and appropriate settlement operations.

Auction creation, scenario administration, automated execution, and replay have been implemented but are not yet available through the public interface.

Broader access is planned following successful validation of the initial IRN Discovery and Confidence auctions.

## Development Philosophy

Academy's technology choices emphasize:

**Established infrastructure.** Use proven blockchain protocols and development frameworks where they meet the requirements.

**Strong domain modeling.** Keep economic configuration, execution behavior, and application presentation clearly separated.

**Reusable components.** Build specialized market interfaces from composable application elements.

**Flexible authorization.** Support direct wallet participation and managed system actors.

**Scenario-driven validation.** Evaluate auction behavior before committing to mainnet execution.

**Observable execution.** Make auction mechanics understandable through monitoring, visualization, and replay.

**Interoperability.** Build complementary infrastructure around established open protocols rather than unnecessarily replacing them.

---

## Related Documentation

- [Architecture](architecture.md)
- [Auction Mechanics](auction.md)
- [Bots & Scenarios](bots.md)
- [Rewards & Qualification](rewards.md)
- [Fluent UI Blazor](https://www.fluentui-blazor.net/)
- [Nethereum](https://nethereum.com/)
- [Reown](https://reown.com/)
- [Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)
