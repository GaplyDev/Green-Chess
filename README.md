PRD – Chex.fun
Project Summary
Chex.fun is a Web3-native chess platform that combines the familiar fun of real-time 1v1 chess with crypto-native features — like wallet-based identity, on-chain wagers, and dynamic platform fees. The project is designed to run on Abstract L2 and integrates directly with Abstract Wallet (abs.xyz) (not to be confused with wallet abstraction patterns).
The core experience:
Competitive chess meets Web3, where users can play, wager, spectate, and stream games, all powered by the blockchain.


PRD – Chex.fun
Project Summary
Chex.fun is a Web3-native chess platform that combines the familiar fun of real-time 1v1 chess with crypto-native features — like wallet-based identity, on-chain wagers, and dynamic platform fees. The project is designed to run on Abstract L2 and integrates directly with Abstract Wallet (abs.xyz) (not to be confused with wallet abstraction patterns).
The core experience:
Competitive chess meets Web3, where users can play, wager, spectate, and stream games, all powered by the blockchain.

Objectives
Deliver a chess platform optimized for Web3 users and streamers


Enable crypto-based wagering using any EVM-compatible token


Implement fee-based revenue via escrow smart contracts


Make the experience familiar, snappy, and shareable — like Chess.com, but with crypto



Target Users
Web3 streamers and NFT influencers


Crypto-native casual gamers


Web3 communities & DAOs running internal tournaments


Degen traders looking for a fun, skill-based alternative to gambling



Key Features
A. Core Gameplay (v1)
Feature
Description
Wallet login
Connect with Abstract Wallet (abs.xyz)
ENS name / short address
Display user identity on match screen
Create/join match
Chess.com-style lobby: invite link, open challenges
Time control
Choose 5-min, 10-min, or custom blitz options
Game result handling
Win, loss, draw, or timeout shown at match end
Spectator mode
Public match links for streaming and sharing
Streamer mode
Minimal UI overlay for OBS / abstract-friendly view


B. Wagering & Smart Contracts 
Feature
Description
Wager selection
User selects amount and token (ETH or any EVM token)
Matched wager requirement
Game only starts when both players match the stake
Escrow smart contract
Funds are locked on-chain until result
Result confirmation
Both players confirm winner OR timeout auto-triggers result
Refunds
In case of draw, funds returned to both wallets
Platform fee
2.5% (default) of the total pot, taken from the total pot on match start.
Multi-token support
ERC-20 tokens and ETH accepted via Abstract-compatible wallet



Smart Contract Example Logic
function createGame(uint256 wagerAmount, address tokenAddress) external payable;
function joinGame(uint256 gameId) external payable;
function declareResult(uint256 gameId, address winner) external;
function claimWinnings(uint256 gameId) external;
function setPlatformFee(uint256 newFeeBps) external onlyAdmin;

Platform fee is adjustable via admin panel (in basis points, e.g. 250 = 2.5%)

C. Admin Panel (v3)
Feature
Description
Set platform fee %
Adjust fee dynamically 
Token allowlist
Manage accepted tokens for wagers
Game logs
View history of completed matches
Ban/report system
Flag users for cheating or abuse
Manual overrides
Declare results or cancel games (for support use)


D. Anti-Cheat & Fair Play (v4)
Anti-Cheat Feature
Description
Move accuracy engine
Compare moves to Stockfish score to detect perfect play
Cheater flagging
Flag high-accuracy players for admin review
Reporting system
Let users report suspicious games
Match history visualization
Heatmap and graph of performance, blunders, accuracy

Third-party cheat detection APIs like Chess.com are not public, so we’ll use open-source analysis tools and a basic Stockfish-based accuracy system.

Match Creation Flow (Like Chess.com)
Click “Play”


Choose:


Time control (5|10|Custom)


Game type: Public, Invite Only
A Normal or Wagered Checkbox (Wager preselected)


If wagered:


Choose token (ETH or approved ERC-20)


Set amount


Click “Create Match”


Get sharable link or wait in open lobby


Opponent joins → match starts



Tech Stack (But not limited to these)
Layer
Tech
Frontend
Next.js + Tailwind CSS
Chess Engine
Chess.js, Chessboard.js
Wallet
Abstract Wallet (abs.xyz)
Blockchain
Abstract L2 (EVM compatible)
Smart Contract
Solidity (Thirdweb or custom)
Hosting
Vercel
DB (optional)
Supabase / Firebase (for history)


Token Support
Accept any EVM-compatible token or native ETH


Admin panel will allow setting a token allowlist


Abstract handles wallet integration, token balances, and gas abstraction (if needed)



Monetization
Platform fee is taken from the total prize pool.


Fee is adjustable (default: 2.5%) via admin dashboard



Phases Summary
Phase
Feature Set
v1
Wallet login, chess gameplay, streamer-ready UX
v2
Wagering (ETH/tokens), escrow smart contracts, fee payouts
v3
Admin panel: fees, token lists, override tools
v4
Anti-cheat detection, reporting, match review UI







Objectives
Deliver a chess platform optimized for Web3 users and streamers


Enable crypto-based wagering using any EVM-compatible token


Implement fee-based revenue via escrow smart contracts


Make the experience familiar, snappy, and shareable — like Chess.com, but with crypto



Target Users
Web3 streamers and NFT influencers


Crypto-native casual gamers


Web3 communities & DAOs running internal tournaments


Degen traders looking for a fun, skill-based alternative to gambling



Key Features
A. Core Gameplay (v1)
Feature
Description
Wallet login
Connect with Abstract Wallet (abs.xyz)
ENS name / short address
Display user identity on match screen
Create/join match
Chess.com-style lobby: invite link, open challenges
Time control
Choose 5-min, 10-min, or custom blitz options
Game result handling
Win, loss, draw, or timeout shown at match end
Spectator mode
Public match links for streaming and sharing
Streamer mode
Minimal UI overlay for OBS / abstract-friendly view


B. Wagering & Smart Contracts 
Feature
Description
Wager selection
User selects amount and token (ETH or any EVM token)
Matched wager requirement
Game only starts when both players match the stake
Escrow smart contract
Funds are locked on-chain until result
Result confirmation
Both players confirm winner OR timeout auto-triggers result
Refunds
In case of draw, funds returned to both wallets
Platform fee
2.5% (default) of the total pot, taken from the total pot on match start.
Multi-token support
ERC-20 tokens and ETH accepted via Abstract-compatible wallet



Smart Contract Example Logic
function createGame(uint256 wagerAmount, address tokenAddress) external payable;
function joinGame(uint256 gameId) external payable;
function declareResult(uint256 gameId, address winner) external;
function claimWinnings(uint256 gameId) external;
function setPlatformFee(uint256 newFeeBps) external onlyAdmin;

Platform fee is adjustable via admin panel (in basis points, e.g. 250 = 2.5%)

C. Admin Panel (v3)
Feature
Description
Set platform fee %
Adjust fee dynamically 
Token allowlist
Manage accepted tokens for wagers
Game logs
View history of completed matches
Ban/report system
Flag users for cheating or abuse
Manual overrides
Declare results or cancel games (for support use)


D. Anti-Cheat & Fair Play (v4)
Anti-Cheat Feature
Description
Move accuracy engine
Compare moves to Stockfish score to detect perfect play
Cheater flagging
Flag high-accuracy players for admin review
Reporting system
Let users report suspicious games
Match history visualization
Heatmap and graph of performance, blunders, accuracy

Third-party cheat detection APIs like Chess.com are not public, so we’ll use open-source analysis tools and a basic Stockfish-based accuracy system.

Match Creation Flow (Like Chess.com)
Click “Play”


Choose:


Time control (5|10|Custom)


Game type: Public, Invite Only
A Normal or Wagered Checkbox (Wager preselected)


If wagered:


Choose token (ETH or approved ERC-20)


Set amount


Click “Create Match”


Get sharable link or wait in open lobby


Opponent joins → match starts



Tech Stack (But not limited to these)
Layer
Tech
Frontend
Next.js + Tailwind CSS
Chess Engine
Chess.js, Chessboard.js
Wallet
Abstract Wallet (abs.xyz)
Blockchain
Abstract L2 (EVM compatible)
Smart Contract
Solidity (Thirdweb or custom)
Hosting
Vercel
DB (optional)
Supabase / Firebase (for history)


Token Support
Accept any EVM-compatible token or native ETH


Admin panel will allow setting a token allowlist


Abstract handles wallet integration, token balances, and gas abstraction (if needed)



Monetization
Platform fee is taken from the total prize pool.


Fee is adjustable (default: 2.5%) via admin dashboard



Phases Summary
Phase
Feature Set
v1
Wallet login, chess gameplay, streamer-ready UX
v2
Wagering (ETH/tokens), escrow smart contracts, fee payouts
v3
Admin panel: fees, token lists, override tools
v4
Anti-cheat detection, reporting, match review UI



