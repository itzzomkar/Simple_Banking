# Simple Banking App Project

This project contains two files for Blockchain Project:
1. **`SimpleBank.sol`** - The Solidity Smart Contract.
2. **`index.html`** - The frontend user interface.

## 🏛 Architecture 
The smart contract implements a secure dual-balance system to prevent liquidity draining:
* **Token Balance**: Every new registered account receives 100 free **Bank Tokens**. These can be transferred between registered users.
* **ETH Balance**: Users can deposit and withdraw actual ETH (in Wei).

This fixes a common "conceptual issue" in simple banking Apps where free internal tokens and deposited ETH are mixed in a single variable, which would allow users to withdraw their free tokens as actual ETH and drain the bank's reserves!



We will deploy this to the **Sepolia Testnet**. Testnets use "fake" ETH that has no real-world value, so it is 100% free!

### Step 1: Get MetaMask & Fake ETH
1. Install the **[MetaMask](https://metamask.io/)** extension in your browser.
2. In MetaMask, go to Settings -> Advanced -> **Turn on "Show test networks"**.
3. Switch your network to **Sepolia Testnet**.
4. Go to a Sepolia Faucet like **[Alchemy Sepolia Faucet](https://sepoliafaucet.com/)** or **[Infura Faucet](https://www.infura.io/faucet/sepolia)**. (You may need to create a free account).
5. Enter your MetaMask wallet address and request fake ETH.

### Step 2: Deploy on Remix
1. Open **[Remix IDE](https://remix.ethereum.org/)**.
2. Create a new file in Remix called `SimpleBank.sol` and copy-paste the code from the `SimpleBank.sol` file in this folder.
3. On the left side of Remix, click the **Solidity Compiler** icon and click **"Compile SimpleBank.sol"**.
4. Click the **Deploy & Run Transactions** icon below the compiler.
5. In the **ENVIRONMENT** dropdown, change it from "Remix VM" to **"Injected Provider - MetaMask"**. MetaMask will pop up asking for permission to connect to Remix.
6. Make sure your Sepolia testnet address is selected.
7. Click the orange **"Deploy"** button. MetaMask will ask you to confirm a free testnet transaction.
8. Once deployed, scroll down to "Deployed Contracts" and **copy the Contract Address** (there's a small copy icon next to it).

### Step 3: Run the Frontend
1. Open the `index.html` file in your code editor.
2. Locate `CONTRACT_ADDRESS` in the `<script>` section:
   ```javascript
   const CONTRACT_ADDRESS = "YOUR_CONTRACT_ADDRESS_HERE"; 
   ```
3. Replace `"YOUR_CONTRACT_ADDRESS_HERE"` with the deployed contract address you copied from Remix.
4. Save the file.
5. Serve the file using VS Code **Live Server** (or open `index.html` in your browser).
6. Click **"Connect MetaMask"**.
7. You can now Register, Deposit, Withdraw, and Transfer!
