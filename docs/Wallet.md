# Wallet

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** | Wallet identifier |  |
| **owner** | [**WalletOwner**](WalletOwner.md) |  |  |
| **balance** | **kotlin.Long** | Current wallet balance |  |
| **overdraft** | **kotlin.Long** | Overdraft limit |  |
| **walletType** | [**inline**](#WalletType) | Type of wallet |  |


<a id="WalletType"></a>
## Enum: walletType
| Name | Value |
| ---- | ----- |
| walletType | GROUP, INVENTORY, SIM |

