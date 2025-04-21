

# PRD – WagerChess

## Overview

WagerChess is a browser-based chess platform designed for casual, real-time 1v1 games — with a long-term roadmap for crypto wagering. The platform will launch first as a **simple wallet-connected chess game**, and later evolve into a **wager-enabled dApp** on **Abstract (EVM-compatible L2)**.

The core idea:  
> A visually polished, on-chain-native chess experience with future-ready mechanics for staked games.

---

## Design & Aesthetic

- **Visual tone**: Light, fun, expressive — with a playful but clean Web3-native aesthetic.
- **Inspiration**: [abs.xyz](https://abs.xyz) (clean, sharp UX) + [Pudgy Penguins](https://pudgypenguins.com) (friendly, fun, branded)
- Design should feel Web3-native — with **simple UX**, **delightful micro-interactions**, and **soft visuals** that appeal to both degen and casual users.

---

## Version 1 – Wallet-Connected Chess Game (No Wagering)

### Objective

Launch a clean and engaging 1v1 chess game with wallet connection, no tokens or crypto wagers yet.

### Core Features

- **Connect Wallet**: Abstract-compatible (MetaMask, Rainbow, etc.)
- **Play Chess**:
  - 1v1 matchmaking (via link or simple lobby)
  - Chess rules powered by `Chess.js`
  - Visual board with `Chessboard.js`
  - 5 or 10-minute timer per player
- **Game Result**: win, lose, draw, timeout
- **Identity**: Display player as ENS name or shortened wallet
- **Frontend only**: No smart contract interaction yet

### Tech Stack

| Layer       | Tech                            |
|-------------|---------------------------------|
| Frontend    | Next.js, Tailwind CSS           |
| Game Logic  | Chess.js, Chessboard.js         |
| Wallet      | Wagmi + Ethers.js (or RainbowKit/Thirdweb) |
| Hosting     | Vercel                          |
| Chain       | Ethereum-compatible wallet (no txs in v1) |

---

## Version 2 – Wager-Based Chess on Abstract

### Objective

Add smart contract-based wagering: players can stake ETH or tokens on their game, and the winner claims the pot.

### Wagering Features

- Create or Join a game with a wager
- Wager funds deposited into an **existing escrow contract**
- Game ends → both players confirm result → escrow releases funds
- Draw → refund
- Optional timeout logic or admin override

### Smart Contract

Use an existing escrow base (e.g. OpenZeppelin `PullPayment`, Thirdweb base contract, or minimal custom):

```solidity
function createGame(uint256 wager) external payable;
function joinGame(uint256 gameId) external payable;
function declareWinner(uint256 gameId, address winner) external;
function withdraw(uint256 gameId) external;
```

Contracts will be deployed to **Abstract**, using ETH or ERC-20 tokens.

### v2 Additions

- Wager UI: Amount input, confirm modal, on-chain transaction steps
- Result declaration logic (initially manual)
- Contract interaction layer via Ethers.js or Thirdweb SDK
- Game state indexed via local backend or lightweight subgraph (optional)

---

## Long-Term Structure

| Phase | Functionality                          |
|-------|----------------------------------------|
| v1    | Wallet chess game, no wagers           |
| v2    | Escrow-based wagering & payouts        |
| v3    | Leaderboards, ELO, tournaments         |
| v4    | Anti-cheat, arbitration, oracle layers |

