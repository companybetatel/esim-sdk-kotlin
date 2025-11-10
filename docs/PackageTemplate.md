
# PackageTemplate

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** | Unique package template identifier |  |
| **name** | **kotlin.String** | Package template name |  |
| **supportedCountries** | **kotlin.collections.List&lt;kotlin.String&gt;** | List of supported country ISO codes |  |
| **dataUsageAllowance** | **kotlin.Int** | Data allowance in bytes |  |
| **activationType** | [**inline**](#ActivationType) | Type of activation |  |
| **createdDate** | **kotlin.Int** | Unix timestamp of creation |  |
| **modifiedDate** | **kotlin.Int** | Unix timestamp of last modification |  |
| **timeAllowance** | [**TimeAllowance**](TimeAllowance.md) |  |  |
| **status** | [**inline**](#Status) | Template status |  |
| **trafficPolicy** | **kotlin.Int** | Traffic policy identifier |  [optional] |
| **voiceUsageAllowance** | **kotlin.Int** | Voice allowance in minutes |  [optional] |
| **smsUsageAllowance** | **kotlin.Int** | SMS allowance count |  [optional] |
| **activationTimeAllowance** | **kotlin.Int** | Time allowance for activation in seconds |  [optional] |
| **earliestActivationDate** | **kotlin.Int** | Unix timestamp of earliest activation date |  [optional] |
| **earliestAvailableDate** | **kotlin.Int** | Unix timestamp of earliest availability |  [optional] |
| **latestAvailableDate** | **kotlin.Int** | Unix timestamp of latest availability |  [optional] |
| **notes** | **kotlin.String** | Additional notes about the template |  [optional] |
| **deactivatedDate** | **kotlin.Int** | Unix timestamp of deactivation (0 if active) |  [optional] |
| **apn** | **kotlin.String** | Access Point Name |  [optional] |


<a id="ActivationType"></a>
## Enum: activation_type
| Name | Value |
| ---- | ----- |
| activationType | AUTO, MANUAL |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | Active, Inactive |



