# RustChain Python SDK Tutorial

Complete guide for using the RustChain Python SDK.

## Installation

```bash
pip install rustchain-sdk
```

## Quick Start

```python
from rustchain import Client, Wallet

# Initialize client
client = Client(network='mainnet')

# Create wallet
wallet = Wallet.create()
print(f"Address: {wallet.address}")
```

## Wallet Operations

### Check Balance
```python
balance = client.get_balance(wallet.address)
print(f"Balance: {balance} RTC")
```

### Send Transaction
```python
tx = wallet.send(
    to='0xRecipientAddress',
    amount=10.5,
    token='RTC'
)
print(f"Transaction hash: {tx.hash}")
```

## Smart Contract Interaction

```python
from rustchain import Contract

# Load contract
contract = Contract(
    address='0xContractAddress',
    abi='contract_abi.json'
)

# Call function
result = contract.call('balanceOf', wallet.address)
print(f"Token balance: {result}")
```

## Error Handling

```python
from rustchain.exceptions import InsufficientBalance, InvalidAddress

try:
    tx = wallet.send(to='invalid', amount=100)
except InvalidAddress:
    print("Invalid recipient address")
except InsufficientBalance:
    print("Insufficient balance")
```

## Next Steps
- Read the [API Reference](../api/reference.md)
- Check [Examples](../../examples/)
- Join our [Discord](https://discord.gg/rustchain)

Reward: 15 RTC
