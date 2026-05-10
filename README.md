🚀 Decentralized Freelance Platform

💼 Escrow-backed decentralized freelance marketplace built using Solidity, Hardhat, Next.js, Ethers.js, and MetaMask.

A secure Web3 freelancing platform where clients can hire freelancers with smart contract escrow protection, ensuring fairness, transparency, and trustless payments on the blockchain 🔗

✨ Features

✅ Secure escrow-based payments
✅ Smart contract powered workflow
✅ Freelancer reputation system ⭐
✅ Automatic refund handling
✅ MetaMask wallet integration 🦊
✅ Hardhat local blockchain support
✅ On-chain audit & fraud analysis
✅ Fully decentralized architecture 🌐

🛠️ Tech Stack
Technology	Purpose
Solidity	Smart Contract Development
Hardhat	Ethereum Development Environment
Next.js	Frontend Framework
Ethers.js	Blockchain Interaction
MetaMask	Wallet Integration
OpenZeppelin	Smart Contract Security
📂 Project Setup (Run Locally)
📌 Prerequisites

Make sure you have installed:

Node.js
npm
MetaMask Extension
⚡ Run the Project Locally

Open three PowerShell terminals inside your project folder.

Example:

cd C:\Projects\DecentralizedFreelancePlatform
🧱 Terminal 1 — Start Local Blockchain
npm install
npm run compile
npm run node

✅ Keep this terminal running.

Hardhat will generate 20 demo accounts along with their private keys for testing.

⚠️ If Port 8545 Is Already In Use

Sometimes another hidden Hardhat node may already be running.

Run:

Get-NetTCPConnection -LocalPort 8545 -State Listen | Select-Object OwningProcess
Stop-Process -Id <OwningProcess> -Force
🔑 Print Demo Accounts Again
npm run accounts
📦 Terminal 2 — Deploy Smart Contract
npm run deploy:localhost

This deploys the smart contract locally and writes the deployed contract address to:

lib/deployment.json
🌐 Terminal 3 — Start Frontend
npm run dev

Now open:

http://localhost:3000

🎯 Choose a role first, then connect MetaMask.

🧹 Fix Frontend Errors (If Any)

If the frontend shows a 500 error or does not load correctly after switching between build/dev modes:

npm run clean
npm run dev

Then reopen:

http://localhost:3000
🦊 MetaMask Setup

Add a custom network in MetaMask:

Setting	Value
Network Name	Hardhat Local
RPC URL	http://127.0.0.1:8545

Chain ID	31337
Currency Symbol	ETH
🔐 Import Wallet
Copy one private key from Terminal 1
Import it into MetaMask
Refresh the dApp

✅ You are ready to use the platform.

📜 Smart Contract Design
🛠️ Core Functions
offerService(priceWei, metadataCid)

Stores:

Service price
Freelancer wallet
Status
Timestamp
IPFS metadata CID
hireFreelancer(serviceId, deadlineTimestamp)
Requires exact ETH escrow
Creates a job entry
Emits JobCreated
submitWork(jobId, deliverableHash)

Stores a bytes32 hash commitment for submitted work.

confirmCompletion(jobId)
Client-only function
Protected against reentrancy
Releases escrow payment to freelancer
rateFreelancer(jobId, score)
Rating allowed only once
Score range: 1–5
Updates freelancer reputation
cancelJob(jobId)

Allows cancellation before submission and refunds the client.

autoCancelExpired(jobId)

Automatically refunds inactive jobs after deadline expiry.

auditClient(client)

Returns:

Client history
Escrow totals
Risk score
Fraud indicators
🔗 On-Chain vs Off-Chain Storage
✅ Stored On-Chain
Wallet addresses
Service IDs
Job IDs
Prices
Ratings
Escrow totals
Status
Timestamps
Metadata CID
Deliverable hash
☁️ Stored Off-Chain
Service descriptions
Portfolio files
Chat data
Profile details
Deliverable files
Banking/email information
🔒 Security Features

🛡️ OpenZeppelin ReentrancyGuard protection
🛡️ Escrow locked before work submission
🛡️ State updated before ETH transfer
🛡️ Client-only payment release
🛡️ One-time verified ratings
🛡️ Real on-chain audit data (no fake frontend data)

📊 Reports & Testing
⛽ Generate Gas Report
npm run gas
⚙️ Generate Unoptimized Gas Report
npm run gas:unoptimized
🧪 Generate Test Coverage
npm run coverage
👨‍💻 Team Details — Break the Chain
🎓 Team Members
Name	Roll Number
Malthum Thanush	240005028
Raghav Sharma	240001056
Ratan Kumar	240001059
Sangati Chakradhar Reddy	240001063
Shaik Riyaj	240001068
D Sujith Reddy	240001028
🌟 Project Vision

The goal of this project is to build a trustless freelance ecosystem where freelancers and clients can collaborate securely without relying on centralized intermediaries.

By leveraging blockchain technology, escrow smart contracts, and transparent reputation systems, the platform ensures:

Fair payments 💰
Reduced fraud 🚫
Transparent interactions 🔍
Decentralized ownership 🌐
📌 Future Improvements

🚀 IPFS file upload integration
🚀 DAO-based dispute resolution
🚀 Multi-chain deployment
🚀 AI-powered freelancer recommendations
🚀 NFT-based freelancer portfolios

❤️ Built With Passion By
Break the Chain 💥

“Decentralization is not just technology — it’s trust rewritten.”
