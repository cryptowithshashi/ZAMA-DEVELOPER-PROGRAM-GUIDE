# ZAMA DEVELOPER PROGRAM GUIDE

Welcome to the Zama Developer Program a step-by-step journey to learn how to create, deploy, and claim rewards for your Confidential Smart Contracts on Zama.

##  Let's Write Your First Confidential Smart Contract

- Visit this repo: https://github.com/zama-ai/fhevm-hardhat-template

- Try to fork this repo and open new codespace.

## LEVEL - 2 GUIDE: Prepare a Fresh Contracts Directory

Inside your codespace terminal, clear any existing contracts and create a new folder:

```bash
rm -rf contracts/*
mkdir contracts
touch contracts/Calculator.sol
```

### Write the Calculator Contract

- In the explorer sidebar, find the contracts directory.
- Right-click → New File.
- Name it `Calculator.sol.`
- Paste this Solidity code into the file:

```bash
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract Calculator {
    function encryptedAdd(uint32 a, uint32 b) public pure returns (uint32) {
        return a + b;
    }
}
```

### Install Dependencies

Run the following commands to set up your project packages:

```bash
npm install
npm install @fhenixprotocol/contracts --save
```

### Compile Your Contract

```bash
npx hardhat compile
```

✅ If all goes well, you’ll see a message confirming successful compilation.

## Complete Level 2

Head over to the Zama Guild and mark Level 2 as completed: https://guild.xyz/zama/developer-program

## LEVEL - 3 GUIDE: Deploy and Register Your Contract

### Create a Scripts Directory
Make a folder to store your deployment scripts:

```
mkdir scripts
```

### Add the Deployment Script
Create the deployment file:

```bash
touch scripts/deploy.js
```

Then open `deploy.js` and insert this JavaScript code:

```bash

// customized by CryptoWithShashi let's gooo

const hre = require("hardhat");

async function main() {
  const Calculator = await hre.ethers.getContractFactory("Calculator");
  const calculator = await Calculator.deploy();
  await calculator.waitForDeployment();

  console.log("Calculator deployed to:", await calculator.getAddress());
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
```

### Deploy Your Smart Contract

Execute the deployment script:

```bash
npx hardhat run scripts/deploy.js
```

✅ Your terminal will output the contract address, which looks something like:

```bash
Calculator deployed to: 0xYourContractAddress
```

- Copy this address — you’ll need it to claim your next level.

## Complete Level 3

- Go back to the Zama Guild page: https://guild.xyz/zama/developer-program

- Find Level 3: Deploy your confidential contract.
- Paste your contract address to verify your deployment.


## 💬 FAQ

Q: What is Codespaces?
- Codespaces is a cloud-based development environment by GitHub. It lets you run, build, and deploy projects without installing anything locally.

Q: Where do I get help if something fails?
- Check the Zama Discord or the official documentation for troubleshooting tips.

Q: Do I need real tokens?
- No, these steps use test environments and don’t require real assets.

## 🛡️ Disclaimer
This guide is independently created to help developers navigate the Zama Developer Program.
All code, frameworks, and documentation belong to the Zama team.
Refer to official Zama resources for authoritative instructions and updates.

## ABOUT ME

Twitter -- https://x.com/SHASHI522004

Github -- https://github.com/cryptowithshashi
