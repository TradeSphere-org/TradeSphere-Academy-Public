# TradeSphere Academy

**On-Chain Auctions · Continuous Price Discovery · Market-Driven Token Launches**

**Great projects need more than great ideas. They need an economy.**

TradeSphere Academy helps projects launch token economies through on-chain auctions, market-driven funding, price discovery, and community participation.

Built on **Uniswap's Continuous Clearing Auction (CCA)** protocol, Academy provides the infrastructure to design, test, operate, and participate in token launches.

Projects can begin with a single auction or develop a campaign of phases and repeated auction attempts. Academy supports market-driven approaches that fit each project’s goals.

**Working software. Real blockchain transactions. Observable results.**

![TradeSphere Academy — Official Auction Portal](assets/academy-overview.png)

*TradeSphere Academy — on-chain auctions powered by Uniswap CCA.*

## Launching a Token Is an Event. Building an Economy Is a Process.

An initial token sale may establish a price, but projects need more than a launch event to succeed. They need participants, capital, liquidity, and opportunities to grow.

Academy provides a structured approach to building that foundation.

Projects can:

- Introduce token supply through competitive on-chain auctions.
- Discover prices through actual bids rather than arbitrary valuations.
- Raise capital as development progresses.
- Establish and expand secondary-market liquidity.
- Attract participants through project-defined campaign phases.
- Test economic strategies before committing real assets.

Participants can discover emerging projects, bid for tokens, develop strategies, and take part in building new economies.

### And Then Comes Graduation

Academy isn't the destination. It's the beginning.

Projects that establish their economic foundation can expand into the broader TradeSphere ecosystem, using infrastructure for organizations, Actors, activities, and participation markets.

**Projects remain independent.** They retain ownership and control of their tokens, organizations, communities, subscribers, and economic relationships.

Graduation into TradeSphere is an opportunity, not a requirement.

**Your project. Your economy. Your future.**

---

## Your Campaign. Your Strategy.

A project might launch a single auction—or design a campaign with several phases and objectives. **Gridiron's The Reckoning** uses five phases, but that is Gridiron's plan, not a requirement for other projects.

A phase may require more than one **attempt**: each attempt executes an individual Uniswap CCA, with its own bidding, clearing, settlement, exits, and claims. The project can repeat or change its **scenario** (distribution and participation strategy) in a subsequent attempt.

An unsuccessful auction attempt does not automatically end its campaign phase. Advancement depends on the phase's published graduation rules and the project's decision to proceed. Within an auction, **stages** describe changes in token distribution and flow—not campaign phases.

The objective is not to guarantee success or eliminate market risk. It is to provide a repeatable, market-driven framework for launching and developing token economies.

*Individual CCA execution is operational. Unified campaign orchestration and adaptive progression are planned extensions.*

### Liquidity & Treasury Growth

A successful initial mainnet auction can establish the project's first Uniswap liquidity pool.

Subsequent auctions can contribute additional assets to the existing pool and increase treasury reserves.

This allows funding and market liquidity to develop throughout a campaign instead of depending entirely on the initial launch.

**The auction launches the market. The campaign helps build the economy.**


### Market Development & Capital Formation

Projects need funding at different stages of their development.
Traditionally, this may involve private token sales, OTC agreements
with investors or institutions, exchange arrangements, and
liquidity providers.

Academy offers another approach: competitive, on-chain auctions
where participants help discover the price and determine how
capital is allocated to the project.

An auction may support an initial market launch, additional
funding, or continued token distribution as the project grows.
Projects can also establish and expand liquidity pools or pursue
exchange listings independently.

The Reckoning is Gridiron's five-phase campaign strategy.
Other projects may use entirely different approaches, including
a single auction.

**Markets evolve. Funding opportunities should evolve with them.**

---

## Featured Project — Gridiron

We're putting Academy to work on our own projects first.

**Gridiron** is our first featured project, introducing the IRN token economy through a five-phase campaign of progressive distribution, funding, and participation.

| Phase | Network | Purpose | Liquidity |
|---|---|---|---|
| **01 — Discovery** | Ethereum Sepolia | Participation and qualification | — |
| **02 — Confidence** | Arbitrum One | Initial funding and price discovery | Launch initial pool |
| **03 — Momentum** | Arbitrum One | Continue controlled distribution | Add liquidity |
| **04 — Expansion** | Arbitrum One | Broaden participation and capital formation | Add liquidity |
| **05 — Peak** | Arbitrum One | Complete the planned campaign allocation | Add liquidity |

Each phase advances when its graduation criteria are satisfied. Subsequent phases can contribute additional assets to the existing liquidity pool and project treasury.


### The Discovery Auction — Live Test Auction

The Discovery auction is Academy's first public test auction,
running on **Ethereum Sepolia** using **test USDC and test IRN**.

The auction runs for a defined period, with a limited number of
participants and a minimum participation requirement to advance
the campaign to the Confidence phase.

Participants can experience real on-chain bidding and continuous
price discovery without committing real purchase funds.

Participation in the Discovery auction can establish eligibility
for matching IRN rewards in the Confidence auction.

**Qualification requires placing a bid in the Discovery auction,
not simply connecting a wallet.**

Academy provides test USDC once per wallet, immediately before
the first bid—not upon connection, and not again after bidding.

**[Join the Discovery Auction](https://academy.tradesphere.org/gridiron)**

### The Confidence Auction — Real Participation, Real Incentives

The Confidence auction is the planned first **Arbitrum One mainnet auction**, conditional on the Discovery auction meeting its minimum participation requirement of 100 bidders.

The auction will use **real USDC** and is designed for participants making purchases in the **$100–$5,000 range**.

Participants can purchase IRN through Uniswap CCA, with two additional incentives:

- **IRN Matching Rewards:** Qualified Discovery auction participants who make eligible settled Confidence auction purchases can receive additional IRN, up to 1:1 matching. Matching is proportional when qualifying demand exceeds the available reward reserve.
- **USDC + IRN Bonus Lottery:** Eligible Confidence auction participants can qualify for a bonus calculated from 3% of settled USDC proceeds, together with an equivalent IRN amount based on the final clearing price. Participation in the Discovery auction is not required for lottery eligibility.

The campaign reserves **5 billion IRN** for the IRN bonus and proportional matching rewards.

Matching eligibility requires the same wallet address used in the Discovery auction and a qualifying settled Confidence auction purchase within the published limits.

The lottery, matching distributions, and final eligibility rules are subject to the applicable campaign conditions.

**[Rewards & Qualification](docs/rewards.md)**

---

## Powered by Uniswap CCA

Academy uses **Uniswap Continuous Clearing Auctions** for on-chain token distribution and price discovery.

Participants submit bids specifying their spending limits and maximum acceptable prices.

Tokens become available over time according to the auction's configured distribution schedule. Competing bids influence the clearing price and allocations.

Academy makes that execution visible through:

- Live auction metrics and clearing prices
- Stage-based token flow visualization
- Wallet-connected bidding and position management
- Realized and unrealized allocation calculations
- On-chain settlement and claims
- Scenario testing, automated test bots, and replay

![Live Academy auction — transition from Stage 3 to Stage 4](assets/academy-auction-live.gif)

*Live auction execution: Stage 3 transitions to Stage 4 as the token-flow rate and remaining supply update. *

**Uniswap provides the auction protocol. Academy provides the tools to configure, operate, and understand it.**

[Detailed Auction Mechanics](docs/auction.md) · [Uniswap CCA Documentation](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)


### Connect to Existing Auctions

Academy can load existing Uniswap CCA auctions directly by contract address, including auctions deployed outside Academy.

Once loaded, auctions can be monitored live or replayed using Academy's auction engine and visualizations.

This provides developers and project teams with additional tools for observing, analyzing, and verifying auction behavior without requiring deployment through Academy.

**Existing-auction loading, live monitoring, and replay are implemented capabilities currently restricted to administrators.**

---

## Built with Modern .NET & Ethereum Technology

Academy combines a predominantly C# application stack with Ethereum-compatible smart contracts on Sepolia and Arbitrum One, and participant-controlled wallets.

| Technology | Role |
|---|---|
| **.NET 10 / Blazor Server** | Interactive application and server-managed services |
| **Fluent UI Blazor 5** | Component framework and user interface |
| **Nethereum** | Blockchain integration, contract operations, and managed transactions |
| **Reown** | Connected-wallet authorization and transactions |
| **Uniswap CCA** | On-chain auction execution and price discovery |
| **Ethereum Sepolia** | Discovery auction and on-chain testnet validation |
| **Arbitrum One** | Production auctions and mainnet settlement |
| **Infura** | Blockchain RPC infrastructure |
| **Microsoft Azure** | Application hosting |

Academy uses **Blazor Server** to coordinate auction state, calculations, monitoring, and real-time UI updates. JavaScript and Reown handle participant wallet interactions directly in the browser.

Centralized blockchain monitoring reduces redundant RPC activity across connected participants.

We've also upgraded to **Fluent UI Blazor 5**, combining Microsoft's Fluent components with Academy's custom auction controls, visualizations, and market interfaces.

[Technology Stack](docs/technology.md) · [Architecture](docs/architecture.md)

---

## Scenarios, Test Bots & Replay

A successful auction launch requires more than a working smart contract. It requires understanding how the auction behaves under different conditions.

Academy's scenario executor supports three environments:

| Environment | Purpose |
|---|---|
| **Test** | Accelerated off-chain simulation and evaluation |
| **Sim** | On-chain testnet validation using real contracts and test assets, including Ethereum Sepolia |
| **Live** | Arbitrum One mainnet execution with real economic commitments |

Scenarios can progress from **Test → Sim → Live**, preserving their distribution strategy while applying the appropriate network configuration.

### Behavioral Test Bots

Academy includes controlled test bots with configurable bidding strategies and behavioral models.

The framework incorporates five bidding strategies, sixteen Myers-Briggs personality profiles, four temperaments, and quantitative behavioral biases.

These models introduce variation in participation, price sensitivity, spending, and competitive behavior.

**Academy test bots are not independent external Agents.** They are controlled participants used for simulation, testing, and validation.

TradeSphere already operates bots and scenarios across Ideas, Missions, and Games. Academy's enhanced behavioral model is designed to extend those existing capabilities.

### Replay & Verification

Auction execution can be reconstructed and replayed, allowing calculated results to be compared against recorded activity. A complete execution can be reviewed in an accelerated 20-second replay; see [Test Bots & Scenarios](docs/bots.md) for the clip and explanation.

Test bots, scenario administration, and replay are implemented capabilities that currently remain restricted to administrators.

[Test Bots & Scenarios](docs/bots.md)

---

## Built First. Proven Through Use.

Academy is operational, with public access focused on discovering and participating in existing auctions.

The underlying application already supports token and auction creation, scenario configuration, automated testing, blockchain execution, and replay.

These creation and administration capabilities remain restricted during the initial launch period.

We're using the IRN campaign to validate the technology and economic approach through actual participation before expanding access to other projects.

**We're building the infrastructure we intend to use—and making it available for others to build on.**

---

## Documentation

| Document | Description |
|---|---|
| [Architecture](docs/architecture.md) | Application structure, campaign model, registration, and services |
| [Auction Mechanics](docs/auction.md) | Continuous clearing, bidding, flow, allocations, and settlement |
| [Technology Stack](docs/technology.md) | Frameworks, blockchain integration, and hosting |
| [Test Bots & Scenarios](docs/bots.md) | Behavioral simulation, Test/Sim/Live, and replay |
| [Rewards & Qualification](docs/rewards.md) | Discovery eligibility, Confidence matching, and bonus lottery |

## Where's the Code?

TradeSphere Academy's application source is currently maintained in a private development repository.

This repository presents the architecture, technology, implementation details, and demonstrations of the working system.

Selected libraries, components, and integration interfaces may be released separately as they become ready.

**The software is real. The source is private for now.**

---

## Explore TradeSphere

**[TradeSphere Academy](https://academy.tradesphere.org)** — Explore the platform and participate in live auctions.

**[Gridiron Discovery Auction](https://academy.tradesphere.org/gridiron)** — Participate in the live Sepolia test auction.

**[TradeSphere Website](https://www.tradesphere.org)** — Explore the ecosystem and its applications.

**[TradeSphere GitHub Organization](https://github.com/TradeSphere-org)** — Projects, architecture, and technical documentation.

**[Uniswap CCA](https://developers.uniswap.org/docs/liquidity/liquidity-launchpad/overview)** — The underlying auction protocol.

**[Fluent UI Blazor](https://www.fluentui-blazor.net/)** — The application component framework.

**[Discord](https://discord.gg/QkJqp4snHQ)** — Community and discussion.

**Contact:** [info@tradesphere.com](mailto:info@tradesphere.com)

---

**TradeSphere™ — Participation Markets for Humans and Autonomous Agents.**