# NorthernPay™️ Smart Contract Repository

**Contract Address:** `0xa6cC027c3Bba1793B53b626974Ba1f38321F356b`  
**Network:** Polygon (MATIC)  
**Contact:** info@northernstudios.cc  
**License:** PolyForm Noncommercial License 1.0.0 (see [LICENSE](./LICENSE))

---

## 📖 Overview

This repository hosts the verified Solidity source code for the **NorthernPay™️** smart contract deployed on the Polygon blockchain.  

The purpose of this repository is to:
- Preserve a copy of the **verified source** of the deployed contract.  
- Allow developers and auditors to **inspect, rebuild, and verify** the contract locally.  
- Provide supporting documentation, build instructions, and licensing information.  

This contract is already verified on PolygonScan, and the original source can be obtained directly from the explorer.

---

## 📂 Repository Structure
```
NorthernPay/
├── Contract/
│   ├── NorthernPay Contract
│
├── Security Audits/
│   ├── Tokenomics_audit_report.pdf
│   └── Contract_security_audit.pdf
│
├── src/
│   ├── assets/
│   └── images/
│
├── LICENSE
├── README.md
└── SECURITY.md
```

---

## 🔗 Useful Links

- **PolygonScan (Verified Code):**  
  [View Contract on PolygonScan](https://polygonscan.com/address/0xa6cC027c3Bba1793B53b626974Ba1f38321F356b#code)

- **License (PolyForm Noncommercial):**  
  [PolyForm License NC 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0/)

---

## 📥 Downloading Verified Contract Code

1. Go to the PolygonScan contract page:  
   [PolygonScan Contract Code Tab](https://polygonscan.com/address/0xa6cC027c3Bba1793B53b626974Ba1f38321F356b#code)

2. Click the **"Code"** tab.  

3. Use the **Download** button (or copy code to clipboard).  

4. Place the downloaded file inside the `Contracts/` directory.  

---

## 🛠️ Building & Compiling

### Using Hardhat

1. Install dependencies:
```bash
npm init -y
npm install --save-dev hardhat @nomiclabs/hardhat-ethers ethers
```

2. Initialize project:
```bash
npx hardhat
```
Place your `.sol` file into `Contracts/`.

Update `hardhat.config.js` with the compiler version and optimizer settings listed on PolygonScan.

Compile the contracts:
```bash
npx hardhat compile
```

# Example hardhat.config.js
```js
require("@nomiclabs/hardhat-ethers");
require("@nomiclabs/hardhat-etherscan");

module.exports = {
  solidity: {
    version: "0.8.17", // Match PolygonScan verified compiler version
    settings: {
      optimizer: {
        enabled: true,
        runs: 200 // Match optimizer runs shown on PolygonScan
      }
    }
  },
  networks: {
    polygon: {
      url: "https://polygon-rpc.com",
      accounts: [process.env.DEPLOYER_PRIVATE_KEY]
    }
  },
  etherscan: {
    apiKey: {
      polygon: process.env.POLYGONSCAN_API_KEY
    }
  }
};
```
---

## Using Foundry

Install Foundry:
[Foundry Installation Guide](https://github.com/foundry-rs/foundry#installation)

Place the contracts into `Contracts/`

Run:
```bash
forge build
```
---

## 📡 Fetch ABI & Metadata with Thirdweb CLI

To fetch ABI and metadata of the deployed contract:
```bash
npx thirdweb@latest contract get \
  --address 0xa6cC027c3Bba1793B53b626974Ba1f38321F356b \
  --chain polygon > thirdweb-contract.json
```
---

## ✅ Verifying Contracts Locally

Install Hardhat Etherscan plugin:
```bash
npm install --save-dev @nomiclabs/hardhat-etherscan
```
Add `POLYGONSCAN_API_KEY` to your environment.

Verify contract:
```bash
npx hardhat verify --network polygon 0xa6cC027c3Bba1793B53b626974Ba1f38321F356b "<constructorArg1>" "<constructorArg2>"
```
> Use the exact compiler version, optimizer settings, and constructor arguments shown on PolygonScan.

---

### 🤝 Contributing

Fork the repository and create a feature branch.
Submit Pull Requests for improvements (documentation, build scripts, etc.).
***Do not modify*** `Contracts/` unless you clearly mark changes, since it must remain a reference copy of the verified code.

---

### ⚠️ Security & Disclaimer

This repository only provides the **verified source** for transparency.
No guarantees are made regarding the security or correctness of the code.
**Do not use in production** without a complete audit and risk analysis.
Maintainers are **not responsible** for any loss of funds, damages, or misuse.

---

### 📜 License

This project is distributed under the ***PolyForm Noncommercial License 1.0.0.***

***Summary:***

Free for personal or non-commercial use.
Commercial use is strictly prohibited without explicit written permission.
See [LICENSE](./LICENSE) for the full terms.

## 📧 Contact
For inquiries, questions, or commercial licensing requests:
**Email:** [info@northernstudios.cc](mailto:info@northernstudios.cc)
**Website:**[northernpay.org](https://northernpay.org)
