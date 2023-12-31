# USDC

## Description

- [USDC.e](https://zkevm.polygonscan.com/address/0x37eAA0eF3549a5Bb7D431be78a3D99BD360d19e5) (zkEVM) - This contract will match the current USDC contract deployed on Ethereum, with all expected features. Its contract address will be different from the current "wrapped" USDC in use today, and will have the ability to issue and burn tokens as well as "blacklist" addresses.

## Source Code of Contracts

- FiatTokenProxy - USDC's proxy contract (effectively the token address that users interact with)
- FiatTokenV2_1 - implementation of the USDC contract (can be modified through upgrades)

[Ethereum FiatTokenProxy](https://etherscan.io/token/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48#code)

[Ethereum FiatTokenV2_1](https://etherscan.io/address/0xa2327a938febf5fec13bacfb16ae10ecbc4cbdcf#code)

[Arbitrum FiatTokenProxy](https://arbiscan.io/token/0xaf88d065e77c8cc2239327c5edb3a432268e5831#code)

[Arbitrum FiatTokenV2_1](https://arbiscan.io/address/0x0f4fb9474303d10905ab86aa8d5a65fe44b6e04a#code)

NOTE: contracts in `usdc-proxy/` and `usdc-impl/` are copies from Arbitrum, because they are more up to date.

## Deployment

First, copy `.env.example` to `.env` and set the appropriate environment variables

Run the following command to simulate the FiatTokenV1_1.sol deployment locally using Foundry

```bash
forge script script/DeployInitUSDCE.s.sol:DeployInitUSDCE --fork-url ${RPC_URL} -vvvvv
```

To deploy to a particular chain, and verify the contract on Etherscan,

```bash
forge script script/DeployInitUSDCE.s.sol:DeployInitUSDCE --fork-url ${RPC_URL} --broadcast --verify -vvvv
```
