# WiFi Usage Contract

## Overview

This Solidity smart contract, named `WiFiUsageContract`, manages data usage for a WiFi router. It allows the router owner to set a data usage limit and tracks the remaining data available. The owner can use data, and if the limit is reached, they can recharge the data.

## License

This contract is released under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Getting Started

### Prerequisites

- Ethereum development environment with Solidity compiler version 0.8.0 or higher.

### Deployment

1. Deploy the contract to the Ethereum blockchain, specifying the initial data usage limit.
2. The deployer becomes the router owner.

## Contract Functions

### `constructor(uint256 _dataUsageLimit)`

- Initializes the contract with the router owner as the deployer and sets the data usage limit.

### `modifier onlyRouterOwner()`

- Ensures that only the router owner can execute certain functions.

### `function useData(uint256 _dataUsage) external onlyRouterOwner`

- Allows the router owner to use data, deducting the specified amount from the remaining data.
- Emits a `DataUsed` event.
- If the remaining data becomes zero, it reverts with an error message.

### `function rechargeData(uint256 _additionalData) external onlyRouterOwner`

- Allows the router owner to recharge additional data, increasing the remaining data.
- Emits a `DataRecharged` event.

## Events

### `DataUsed(address indexed user, uint256 dataUsage)`

- Triggered when data is used. Provides information about the user and the amount of data used.

### `DataRecharged(address indexed user, uint256 additionalData)`

- Triggered when data is recharged. Provides information about the user and the amount of additional data added.

## Usage Examples

```solidity
// Deploy the contract with a data usage limit of 100
WiFiUsageContract wifiContract = new WiFiUsageContract(100);

// Router owner uses 20 units of data
wifiContract.useData(20);

// Router owner recharges 30 units of data
wifiContract.rechargeData(30);
```

## Contribution 
Sunil ks 
