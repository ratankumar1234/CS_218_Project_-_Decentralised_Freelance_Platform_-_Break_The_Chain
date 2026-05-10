# 🚀 Decentralized Freelance Platform

> ### *Escrow-backed decentralized freelance marketplace built using Solidity, Hardhat, Next.js, Ethers.js, and MetaMask.*

A secure Web3 freelancing platform where clients can hire freelancers with **smart contract escrow protection**, ensuring transparency, fairness, and trustless payments on the blockchain 🔗

---

# *Break the Chain* 💥

| Name | Roll Number |
|---|---|
| *DONDAPATI SUJITH REDDY* | **240001028** |
| *MALTHUM THANUSH* | **240005028** |
| *RAGHAV SHARMA* | **240001056** |
| *RATAN KUMAR* | **240001059** |
| *SANGATI CHAKRADHAR REDDY* | **240001063** |
| *SHAIK RIYAZ* | **240001068** |

---

# ✨ Features

- ✅ **Secure escrow-based payments**
- ✅ **Smart contract powered workflow**
- ✅ **Freelancer reputation system**
- ✅ **Automatic refund handling**
- ✅ **MetaMask wallet integration**
- ✅ **Hardhat local blockchain support**
- ✅ **On-chain audit & fraud analysis**
- ✅ **Fully decentralized architecture**

---

# 🌟 Additional Implemented Features

- 🎭 **Separate UI and pages for Clients and Freelancers**
- 🚨 **Fraud auditing system with suspicious account flagging**
- 📋 **Dedicated service listing page for clients**
- 🔍 **Search functionality for discovering services**
- 📄 **Freelancer CV/Profile section**
- 👤 **Detailed account pages with complete information**
- ⭐ **Service sorting based on ratings and newest listings**
- 🎨 **Enhanced and more modern frontend UI**
- 📚 **History tracking for hired and offered services**
- ❌ **Freelancers can unlist services only when no active contract exists**

---

# 💡 Additional Functionalities

- 📝 **Freelancers can create service listings with title, description, pricing, and deadlines**
- 🌐 **Marketplace displays active services available across the platform**
- 📊 **Average freelancer ratings and total ratings are visible alongside services**
- 👀 **Clients can view complete details of hired services**
- 📂 **Freelancers can manage and monitor all services they offer**
- ⏳ **Clients can claim refunds automatically if deadlines expire without completion**
- 🔄 **Role-based workflow with dedicated Freelancer Mode and Client Mode**
- 📈 **Service status tracking for both clients and freelancers**

---

# 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Solidity** | Smart Contract Development |
| **Hardhat** | Ethereum Development Environment |
| **Next.js** | Frontend Framework |
| **Ethers.js** | Blockchain Interaction |
| **MetaMask** | Wallet Integration |
| **OpenZeppelin** | Smart Contract Security |

---

# 📂 Run Project Locally

## 📌 Prerequisites

Make sure the following are installed:

- **Node.js**
- **npm**
- **MetaMask Browser Extension**

---

# ⚡ Step-by-Step Setup

Open **three PowerShell terminals** inside your project folder.

Example:

```powershell
cd C:\Projects\DecentralizedFreelancePlatform
```

---

# 🧱 Terminal 1 — Start Local Blockchain

```bash
npm install
npm run compile
npm run node
```

Keep this terminal running.

Hardhat will generate **20 demo accounts** and private keys for testing.

---

## ⚠️ If Port 8545 Is Already In Use

```powershell
Get-NetTCPConnection -LocalPort 8545 -State Listen | Select-Object OwningProcess
Stop-Process -Id <OwningProcess> -Force
```

---

## 🔑 Print Demo Accounts Again

```bash
npm run accounts
```

---

# 📦 Terminal 2 — Deploy Smart Contract

```bash
npm run deploy:localhost
```

This writes the deployed contract address to:

```bash
lib/deployment.json
```

---

# 🌐 Terminal 3 — Start Frontend

```bash
npm run dev
```

Open:

```bash
http://localhost:3000
```

Choose a role first, then connect MetaMask 🦊

---

# 🧹 Fix Frontend Errors

If the frontend shows a **500 error** or does not load properly:

```bash
npm run clean
npm run dev
```

Then reopen:

```bash
http://localhost:3000
```

---

# 🦊 MetaMask Setup

Add a custom network using these values:

| Setting | Value |
|---|---|
| **Network Name** | Hardhat Local |
| **RPC URL** | http://127.0.0.1:8545 |
| **Chain ID** | 31337 |
| **Currency Symbol** | ETH |

---

# 🔐 Import Wallet

1. Copy one private key from Terminal 1  
2. Import it into MetaMask  
3. Refresh the dApp  

✅ You are ready to use the platform.

---

# 📜 Smart Contract Design

## *Core Functions*

### **offerService(priceWei, metadataCid)**

Stores:

- Service price
- Freelancer wallet
- Status
- Timestamp
- IPFS metadata CID

---

### **hireFreelancer(serviceId, deadlineTimestamp)**

- Requires exact ETH escrow
- Emits `JobCreated`

---

### **submitWork(jobId, deliverableHash)**

Stores a `bytes32` commitment for submitted work.

---

### **confirmCompletion(jobId)**

- Client-only function
- Reentrancy protected
- Releases escrow to freelancer

---

### **rateFreelancer(jobId, score)**

- Rating allowed only once
- Score range: `1–5`
- Updates freelancer reputation

---

### **cancelJob(jobId)**

Allows cancellation before submission and refunds the client.

---

### **autoCancelExpired(jobId)**

Refunds inactive jobs after deadline expiry.

---

### **auditClient(client)**

Returns:

- Client history
- Escrow totals
- Risk score
- Fraud indicators

---

# 🔗 On-Chain vs Off-Chain

## ✅ Stored On-Chain

- Wallet addresses
- Service IDs
- Job IDs
- Prices
- Ratings
- Escrow totals
- Status
- Timestamps
- Metadata CID
- Deliverable hash

---

## ☁️ Stored Off-Chain

- Service descriptions
- Portfolio files
- Chat data
- Profile details
- Deliverable files
- Banking/email information

---

# 🔒 Security Features

- 🛡️ **OpenZeppelin ReentrancyGuard protection**
- 🛡️ **Escrow locked before work submission**
- 🛡️ **State updated before ETH transfer**
- 🛡️ **Client-only payment release**
- 🛡️ **One-time verified ratings**
- 🛡️ **Real on-chain audit data**

---

# 🧪 Testing

Run smart contract tests using:

```bash
npm test
```

or

```bash
npx hardhat test
```

---

# 📊 Reports & Testing

## ⛽ Generate Gas Report

```bash
npm run gas
```

---

## ⚙️ Generate Unoptimized Gas Report

```bash
npm run gas:unoptimized
```

---

## 🧪 Generate Coverage Report

```bash
npm run coverage
```

---

# 🌟 Project Vision

> *To build a decentralized freelance ecosystem that ensures fairness, transparency, secure payments, and trustless collaboration using blockchain technology.*

---

# 🚀 Future Improvements

- 🌐 IPFS File Upload Integration
- ⚖️ DAO-Based Dispute Resolution
- 🔗 Multi-Chain Deployment
- 🤖 AI-Powered Freelancer Recommendations
- 🖼️ NFT-Based Freelancer Portfolios

---

# ❤️ Built With Passion By

# *Break the Chain* 💥

> ### *“Decentralization is not just technology — it’s trust rewritten.”*
