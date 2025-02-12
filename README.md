# 🚀 MultiSig Wallet

The **MultiSig Wallet** is a smart contract implemented in Solidity that enhances the security of Ethereum transactions by requiring multiple approvals before executing a transaction. This project is ideal for organizations or teams that require consensus-based fund management.

## 🌟 Features
✅ **Multiple Owners**: Supports multiple wallet owners, each with the ability to propose and approve transactions.  
✅ **Multi-Signature Security**: Requires a predefined number of confirmations before executing any transaction.  
✅ **Transaction Management**:  
   -  Submit a transaction proposal.  
   - Confirm a transaction.  
   - Execute a transaction once enough confirmations are gathered.  
   - Revoke a confirmation if needed.  
✅ **Event Logging**: Emits events for deposits, transaction submissions, confirmations, executions, and revocations.

---


### 🔍 Core Components:
1. **👥 Owners & Confirmations**:
   - Stores a list of authorized wallet owners.
   - Maps each owner’s address to a boolean to verify their ownership status.
   - Requires a minimum number of confirmations before executing transactions.

2. **📄 Transaction Structure**:
   - **to**: Address receiving the funds.
   - **value**: Amount of Ether to be transferred.
   - **data**: Optional data payload for contract interactions.
   - **executed**: Boolean flag to track execution status.
   - **numberConfirmations**: Counter for tracking the number of approvals.

3. **🔒 Modifiers for Security**:
   - `onlyOwner`: Restricts access to wallet owners.
   - `txExists(uint _txID)`: Ensures the transaction exists.
   - `notConfirmed(uint _txID)`: Prevents duplicate confirmations.
   - `notExecuted(uint _txID)`: Ensures a transaction has not already been executed.

---

### 🔑 Key Functions

- `📌 submitTx(address _to, uint _value, bytes memory _data)`: Allows an owner to propose a new transaction.
- `✅ confirmTx(uint _txID)`: Owners can confirm a pending transaction.
- `🚀 executeTx(uint _txID)`: Executes the transaction once the required confirmations are met.
- `🔄 revokeConfirmation(uint _txID)`: Allows an owner to revoke their confirmation before execution.
- `👥 getOwners()`: Returns the list of wallet owners.
- `📊 getTransaction(uint _txID)`: Retrieves details of a specific transaction.

---



## 🎯 Usage
- 💰 Fund the contract by sending ETH to its address.
- 📌 Submit a transaction via the `submitTx` function.
- ✅ Confirm transactions until the required threshold is met.
- 🚀 Execute the transaction to complete the transfer.

---

## 🔐 Security Considerations
- **👥 Owner Management**: Ensure owners are trusted entities to prevent malicious activity.
- **⚖️ Threshold Configuration**: Setting an appropriate confirmation threshold is crucial to balancing security and usability.
- **⛽ Gas Optimization**: The contract is designed to minimize unnecessary computations to reduce gas costs.

---


