# Daemon RPC Interface

The Salvium daemon provides a JSON-RPC interface for interacting with the blockchain. This document outlines the available methods and their usage.

## Available Methods

### Get Supply Info
**Description:** Returns information about the total supply of assets in the Salvium blockchain.

#### Request:
- **Method:** `get_supply_info`
- **Parameters:** None required

#### Response:
```json
{
    "circulating_supply": "184400000",
    "current_supply": "92200000",
    "emission_speed": "18.2",
    "height": "720000"
}
```

### Get Blocks Fast
**Description:** Retrieves block information efficiently.

#### Request:
```json
{
    "method": "get_blocks_fast",
    "params": {
        "start_height": 1000000,
        "limit": 100
    }
}
```

### Send Raw Transaction
**Description:** Submits a raw transaction to the network.

#### Request:
```json
{
    "method": "send_raw_transaction",
    "params": {
        "tx_as_hex": "[transaction_hex_data]"
    }
}
```

#### Response:
```json
{
    "status": "OK",
    "double_spend": false,
    "fee_too_low": false,
    "invalid_input": false,
    "invalid_output": false,
    "low_mixin": false,
    "not_relayed": false,
    "overspend": false,
    "reason": "",
    "too_big": false
}
