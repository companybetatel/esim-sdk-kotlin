
# CreatePackageTemplateRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **name** | **kotlin.String** | Package template name |  |
| **supportedCountries** | **kotlin.collections.List&lt;kotlin.String&gt;** | Array of supported country ISO3 codes |  |
| **activationType** | [**inline**](#ActivationType) | Package activation type |  |
| **dataUsageAllowance** | **kotlin.Int** | Data allowance in bytes |  |
| **timeAllowance** | [**TimeAllowance**](TimeAllowance.md) |  |  |
| **activationTimeAllowance** | **kotlin.Int** | Time allowance for activation in seconds |  |
| **earliestAvailableDate** | **kotlin.Int** | Unix timestamp for earliest availability |  |
| **latestAvailableDate** | **kotlin.Int** | Unix timestamp for latest availability |  |
| **inventory** | **kotlin.Int** | Inventory ID to associate the template with |  |


<a id="ActivationType"></a>
## Enum: activation_type
| Name | Value |
| ---- | ----- |
| activationType | AUTO, MANUAL |



