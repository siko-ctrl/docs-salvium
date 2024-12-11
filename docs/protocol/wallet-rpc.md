# Wallet RPC API Documentation

This document provides comprehensive documentation for the Salvium Wallet RPC interface. The Wallet RPC allows programmatic interaction with Salvium wallets for integration into applications, exchanges, and services.

## Overview

The Wallet RPC service provides a JSON-RPC 2.0 interface for wallet operations. All requests should be made via HTTP POST to the configured RPC endpoint.

### Default Configuration
- Default port: 18089
- Default RPC endpoint: `http://localhost:18089/json_rpc`
- Authentication: Required (Basic HTTP Authentication)

## General Format

### Request Format
```json
{
    "jsonrpc": "2.0",
    "id": "0",
    "method": "method_name",
    "params": {
        // method-specific parameters
    }
}
```

### Response Format
```json
{
    "jsonrpc": "2.0",
    "id": "0",
    "result": {
        // method-specific response data
    }
}
```

## Authentication

All RPC calls require authentication:
```bash
curl -u username:password -X POST http://localhost:18089/json_rpc
```

## Available Methods

### Wallet Management

#### `create_wallet`
Creates a new wallet.

```json
{
    "method": "create_wallet",
    "params": {
        "filename": "wallet_name",
        "password": "wallet_password",
        "language": "English"
    }
}
```

#### `open_wallet`
Opens an existing wallet.

```json
{
    "method": "open_wallet",
    "params": {
        "filename": "wallet_name",
        "password": "wallet_password"
    }
}
```

#### `close_wallet`
Closes the currently opened wallet.

```json
{
    "method": "close_wallet"
}
```

### Account Operations

#### `get_balance`
Retrieves the wallet's balance.

```json
{
    "method": "get_balance",
    "params": {
        "account_index": 0,
        "address_indices": [0, 1]
    }
}
```

Response:
```json
{
    "balance": 1000000000000,
    "unlocked_balance": 1000000000000
}
```

#### `get_address`
Gets the wallet's address.

```json
{
    "method": "get_address",
    "params": {
        "account_index": 0,
        "address_index": 0
    }
}
```

### Transaction Operations

#### `transfer`
Creates and sends a transaction.

```json
{
    "method": "transfer",
    "params": {
        "destinations": [
            {
                "amount": 1000000000,
                "address": "Sal..."
            }
        ],
        "priority": 1,
        "ring_size": 11
    }
}
```

#### `get_transfers`
Retrieves transfer history.

```json
{
    "method": "get_transfers",
    "params": {
        "in": true,
        "out": true,
        "pending": true,
        "failed": true,
        "pool": true
    }
}
```

#### `sweep_all`
Sends all unlocked balance to an address.

```json
{
    "method": "sweep_all",
    "params": {
        "address": "Sal...",
        "priority": 1,
        "ring_size": 11
    }
}
```

### Key Management

#### `query_key`
Retrieves various wallet keys.

```json
{
    "method": "query_key",
    "params": {
        "key_type": "mnemonic"
    }
}
```

#### `make_integrated_address`
Creates an integrated address.

```json
{
    "method": "make_integrated_address",
    "params": {
        "payment_id": "..."
    }
}
```

### Multisig Operations

#### `prepare_multisig`
Prepares a wallet for multisig conversion.

```json
{
    "method": "prepare_multisig"
}
```

#### `make_multisig`
Converts the wallet to multisig.

```json
{
    "method": "make_multisig",
    "params": {
        "multisig_info": [],
        "threshold": 2
    }
}
```

## Error Handling

Errors are returned in the following format:
```json
{
    "jsonrpc": "2.0",
    "id": "0",
    "error": {
        "code": -32601,
        "message": "Error message"
    }
}
```

Common error codes:
- -32601: Method not found
- -32602: Invalid parameters
- -32603: Internal error
- -32000: Wallet error

## Rate Limiting

- Default rate limit: 1000 requests per minute
- Burst limit: 100 requests
- Exceeded limits return HTTP 429 (Too Many Requests)

## Best Practices

1. **Security**
   - Use HTTPS for production environments
   - Implement IP whitelisting
   - Rotate passwords regularly
   - Monitor for suspicious activity

2. **Performance**
   - Cache responses when appropriate
   - Implement request batching
   - Use connection pooling
   - Monitor resource usage

3. **Error Handling**
   - Implement proper error handling
   - Add request retries with backoff
   - Log all errors for debugging
   - Monitor error rates

## Example Implementation

Python example using requests:
```python
import requests
import json

def make_rpc_request(method, params=None):
    url = "http://localhost:18089/json_rpc"
    headers = {"Content-Type": "application/json"}
    auth = ("username", "password")
    
    payload = {
        "jsonrpc": "2.0",
        "id": "0",
        "method": method,
        "params": params or {}
    }
    
    response = requests.post(
        url,
        headers=headers,
        auth=auth,
        data=json.dumps(payload)
    )
    
    return response.json()

# Example: Get wallet balance
result = make_rpc_request("get_balance", {"account_index": 0})
print(f"Balance: {result['result']['balance']}")
```

## Support

For additional support:
- [API Reference](https://docs.salvium.io/api)
- [GitHub Issues](https://github.com/salvium/salvium/issues)
- [Developer Discord](https://discord.gg/salvium)
