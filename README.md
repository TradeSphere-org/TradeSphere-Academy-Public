# TradeSphere Academy

**On-Chain Auctions · Continuous Price Discovery · Scenario-Driven Execution**

TradeSphere Academy is a dedicated application for creating, operating, and participating in on-chain token auctions.

Built around **Uniswap's Continuous Clearing Auction (CCA) protocol**, Academy combines Ethereum smart contracts with real-time auction visualization, wallet connectivity, position management, and TradeSphere's scenario-driven execution architecture.

The application is operational, with ongoing development focused on auction capabilities, automation, and integration with the broader TradeSphere ecosystem.

**Working software. Real blockchain transactions. Observable results.**

![TradeSphere Academy — Official Auction Portal](assets/academy-overview.png)

*TradeSphere Academy — on-chain auctions powered by Uniswap CCA.*

## Why Academy?

**Great projects need more than great ideas. They need an economy.**

TradeSphere Academy is designed to help new projects get off the ground through cryptocurrency tokenomics, market-driven funding, and community participation.

Through on-chain auctions, projects can establish their initial economic foundation, distribute tokens, discover market value, and attract the participants who will help bring them to life.

Along the way, participants learn by doing—exploring blockchain technology, developing strategies, and experiencing decentralized markets firsthand.

### And Then Comes Graduation

Academy isn't the destination. It's the beginning.

Once a project establishes its economic foundation, it can graduate into the broader TradeSphere ecosystem, gaining access to infrastructure for organizations, actors, activities, and participation markets.

**Projects remain independent.** They retain ownership and control of their organizations, tokens, communities, subscribers, and economic relationships. TradeSphere provides the infrastructure, tools, and services to help them operate and grow.

Graduation is a progression, not a requirement. Projects are free to chart their own course.

**Your project. Your economy. Your future.**

### Building It. Using It. Proving It.

We're putting Academy to work on our own projects first.

**IRN** provides the initial tokenomics, while **Gridiron** introduces a competitive approach to building liquidity pools, bringing projects, teams, and participants together around shared economic opportunities.

Through *The Reckoning* campaign, we're using Academy to bootstrap our own ecosystem, validate the technology, and refine the economic model through actual participation.

The objective goes beyond launching a token. We're developing a repeatable approach that other projects can use to establish markets, attract participants, build liquidity, and grow independent economies.

**We're building the infrastructure we intend to use—and making it available for others to build on.**

## Powered by Uniswap CCA

Academy integrates Uniswap's Continuous Clearing Auction protocol for transparent, on-chain price discovery.

CCA distributes tokens continuously over an auction period while bids compete for available supply. Clearing prices and provisional allocations evolve as new bids enter the market.

TradeSphere builds on this foundation with:

- Real-time auction monitoring and visualization
- Bid creation and position management
- Round-based token flow and clearing displays
- On-chain settlement and token claims
- Scenario-driven auction execution and simulation
- Automated bidders with configurable behaviors
- Auction replay and result verification

**Protocol documentation:** [Uniswap Liquidity Launchpad / CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)

Uniswap provides the underlying auction protocol. TradeSphere Academy provides the application, execution services, and participant experience around it.

## How Auctions Work

Participants connect an Ethereum-compatible wallet, select an auction, and place bids specifying spending limits and maximum prices.

As the auction progresses, tokens become available according to the configured release schedule. Bids compete for available supply, and the clearing price determines which bids receive allocations.

Auction positions are dynamic. New bids can change provisional allocations, including reducing or eliminating a previously winning position.

When the auction concludes, final settlement determines token allocations, spending, claims, and recoverable funds.

![TradeSphere Academy — Auction Execution](assets/academy-auction.png)

*Academy Test execution — automated bidding, continuous clearing, rounds, token flow, and market activity.*

**[Detailed auction mechanics](docs/auction.md)**

## Technology

Academy is built with modern .NET technologies and Ethereum infrastructure.

| Technology | Role |
|---|---|
| **Blazor Server / .NET 10** | Interactive application and server-side services |
| **Fluent UI Blazor 5** | User interface components |
| **Nethereum** | Smart contract and Ethereum integration |
| **Uniswap CCA** | On-chain auction protocol |
| **Reown** | Wallet connectivity |
| **MetaMask** | Ethereum wallet interaction |
| **Infura** | Ethereum RPC infrastructure |
| **Microsoft Azure** | Hosting and application infrastructure |

The application uses Blazor Server for interface rendering and server-managed updates, with JavaScript and Reown handling wallet interactions.

This architecture centralizes blockchain monitoring rather than requiring every connected browser to perform independent RPC polling.

**[Technology details](docs/technology.md)** · **[Architecture](docs/architecture.md)**

## Scenarios, Bots & Replay

Academy also demonstrates capabilities from the broader TradeSphere execution architecture.

### Scenario-Driven Execution

Auction scenarios define execution parameters such as duration, token release schedules, participant behavior, and operating conditions.

TradeSphere's execution services support simulation, controlled testing, and live operation.

### Automated Participants

Configurable bots can participate in auction scenarios with different bidding behaviors and strategies.

Bots help evaluate auction dynamics, clearing behavior, competition, and system performance under varying participation conditions.

### Replay & Verification

Auction activity can be reconstructed and replayed from recorded events.

Replay also recalculates auction results, providing a means to analyze execution behavior and compare reconstructed values with observed outcomes.

**[Bots & Scenarios](docs/bots.md)** · **[Architecture](docs/architecture.md)**

## Featured Campaign — Gridiron: The Reckoning

The Reckoning is a planned five-auction campaign introducing IRN participation within the TradeSphere ecosystem.

| Stage | Network | Purpose |
|---|---|---|
| **Discovery** | Sepolia | Qualification and community discovery |
| **Confidence** | Mainnet | Initial economic auction and participant rewards |
| **Momentum** | Mainnet | Continued market participation |
| **Expansion** | Mainnet | Broader participation |
| **Peak** | Mainnet | Final campaign stage |

Discovery uses Sepolia test assets to let participants experience auction mechanics and establish eligibility for potential mainnet rewards.

If sufficient interest is demonstrated, the campaign is intended to progress to Confidence on mainnet.

The Confidence stage includes proposed matching IRN rewards for eligible Discovery participants who complete qualifying settled purchases, together with an additional IRN bonus lottery.

These incentives are campaign-specific and subject to the published rules and the mainnet launch proceeding.

**[Rewards & Qualification](docs/rewards.md)**

## Documentation

| Document | Description |
|---|---|
| [Architecture](docs/architecture.md) | Application structure, services, and execution model |
| [Auction Mechanics](docs/auction.md) | Continuous clearing, bidding, token flow, and settlement |
| [Technology](docs/technology.md) | Frameworks, libraries, and blockchain integrations |
| [Bots & Scenarios](docs/bots.md) | Automated participants, simulation, and replay |
| [Rewards](docs/rewards.md) | The Reckoning campaign incentives and qualification |

## Where's the Code?

TradeSphere Academy's application source is maintained in a private development repository.

This repository provides public-facing technical documentation, architecture, implementation explanations, and demonstrations of the working system.

Selected libraries, components, and integration interfaces may be released separately as they become ready.

**The software is real. The source is private for now.**

## Explore TradeSphere

**[TradeSphere Website](https://www.tradesphere.org)** — The ecosystem and its applications.

**[TradeSphere GitHub Organization](https://github.com/TradeSphere-org)** — Platform architecture, projects, and documentation.

**[Uniswap CCA Documentation](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)** — The underlying auction protocol.

**[Fluent UI Blazor](https://www.fluentui-blazor.net/)** — The application component library.

**[Discord](https://discord.gg/QkJqp4snHQ)** — Community and discussion.

**Contact:** info@tradesphere.com

---

**TradeSphere™ — Participation Markets for Humans and Autonomous Agents.**
