

# PRD – Chex.fun

## Overview

**Chex.fun** is a wallet-connected Web3 chess platform designed for casual players, crypto enthusiasts, and streamers. The product will evolve in two phases:

- **v1**: Clean, fun, and social chess gameplay with wallet identity and streamer support — no wagering
- **v2**: Add crypto-based wagers with an on-chain escrow contract and a 2.5% platform fee

Chex.fun is built for launch on **Abstract**, an EVM-compatible Layer 2.

---

## Visual Identity & Tone

- **Visual style**: Web3-native, fun, minimal — sleek UX and brand-friendly design
- **Inspiration**: [abs.xyz](https://abs.xyz) and [Pudgy Penguins](https://pudgypenguins.com)
- **Design goals**:
  - Fast, elegant UI with instant feedback
  - Streamable layout and branding-friendly match links
  - Playful but polished identity

---

## Version 1 – Wallet Chess Platform (No Wagering)

### Objective

Deliver a delightful, low-friction chess experience designed to attract users and streamers. Focus is on identity, accessibility, and shareability.

### Core Features

| Feature | Description |
|--------|-------------|
| **Wallet Login** | Connect via MetaMask or Abstract-compatible wallet |
| **ENS Display** | Show ENS names or short wallet address for identity |
| **Chess Game** | Powered by `Chess.js` and `Chessboard.js`, standard rules |
| **Time Control** | 5 and 10 minute match timers |
| **Game Sharing** | Shareable match links to challenge viewers/friends |
| **Spectator Mode** | Anyone with link can view live game |
| **Custom Lobby Name** | Optional handle/tag (e.g. @streamer vs challenger) |
| **Result Display** | Win / Lose / Draw / Timeout shown post-game |
| **Streamer Mode** | Auto-show ENS or stream handle, low-clutter board view |

> Optional storage of match history via Firebase or Supabase

---

### Tech Stack

| Layer       | Stack                          |
|-------------|--------------------------------|
| Frontend    | Next.js, Tailwind CSS          |
| Game Logic  | Chess.js, Chessboard.js        |
| Wallet      | Wagmi + Ethers.js or RainbowKit |
| Hosting     | Vercel                         |
| Chain       | Ethereum-compatible wallets (no txs in v1) |

---

## Version 2 – Crypto Wagering (On Abstract)

### Objective

Enable ETH/token wagering on games via on-chain escrow. Players stake into a smart contract, and the winner receives the pot minus a **2.5% platform fee** (configurable).

### Wager Features

| Feature | Description |
|--------|-------------|
| **Wager Input** | Player sets wager in ETH/token |
| **Escrow Deposit** | Both players must match stake to start |
| **Escrow Contract** | Handles holding, payout, and draw logic |
| **Result Declaration** | Manual confirmation or mutual result verification |
| **Payouts** | Winner receives 97.5% of total pot, 2.5% to platform treasury |
| **UI Additions** | Wager confirmation, wallet transaction flow, payout screen |

> Contracts will be deployed on **Abstract L2**

### Smart Contract

Suggested minimal functions:

```solidity
function createGame(uint256 wager, address token) external payable;
function joinGame(uint256 gameId) external payable;
function declareWinner(uint256 gameId, address winner) external;
function withdraw(uint256 gameId) external;
```

Built using OpenZeppelin or Thirdweb primitives.

---

## Anti-Cheating Solutions

### Available Options for Integration

| Tool | Description | Integration Level |
|------|-------------|-------------------|
| **Chess.com Fair Play API** | Used internally, not publicly available | ❌ |
| **Lichess Open Source Detection** | Open-source analysis engine (`lichess-bot`, `lichess-db`) | ⚠️ Heavy, not plug-and-play |
| **DeCeptive (by DeFi Safety)** | AI-based fraud detection (not chess-specific) | ⚠️ Experimental |
| **Custom AI cheat detector (Lichess/Stockfish diff)** | Analyze move accuracy vs engine | ✅ Possible but intensive |

> ✅ Suggestion for future: Build basic **move accuracy scoring** vs Stockfish and flag perfect play as potential cheat

---

## Long-Term Structure

| Phase | Features |
|-------|----------|
| **v1** | Wallet chess, shareable matches, streamer-focused UX |
| **v2** | Escrowed wagers, smart contract payouts, platform fee |
| **v3** | Match history, profiles, ladder system |
| **v4** | Cheating detection, tournament mode, token incentives |

