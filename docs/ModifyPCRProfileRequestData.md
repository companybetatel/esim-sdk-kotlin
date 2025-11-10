
# ModifyPCRProfileRequestData

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **state** | [**inline**](#State) | Desired state of the data profile (required when data object is provided) |  |
| **activeThrottling** | [**inline**](#ActiveThrottling) | Desired throttling speed configuration |  |


<a id="State"></a>
## Enum: state
| Name | Value |
| ---- | ----- |
| state | ENABLED, DISABLED |


<a id="ActiveThrottling"></a>
## Enum: active_throttling
| Name | Value |
| ---- | ----- |
| activeThrottling | NO_LIMIT, SPEED_100_KBPS, SPEED_500_KBPS, SPEED_1000_KBPS, SPEED_2000_KBPS, SPEED_3000_KBPS, SPEED_5000_KBPS |



