
# CreatePackageResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.String** | Created package ID |  |
| **sim** | **kotlin.String** | SIM ICCID |  |
| **createdDate** | **kotlin.Int** | Unix timestamp of package creation |  |
| **expiryDate** | **kotlin.Int** | Unix timestamp of package expiry |  |
| **activatedDate** | **kotlin.Int** | Unix timestamp when package was activated (0 if not activated) |  |
| **terminatedDate** | **kotlin.Int** | Unix timestamp when package was terminated (0 if not terminated) |  |
| **windowActivationStart** | **kotlin.Int** | Unix timestamp of activation window start |  |
| **windowActivationEnd** | **kotlin.Int** | Unix timestamp of activation window end |  |
| **status** | [**inline**](#Status) | Current package status |  |
| **voiceUsageRemaining** | **kotlin.Int** | Remaining voice minutes |  |
| **dataUsageRemaining** | **kotlin.Int** | Remaining data in bytes |  |
| **smsUsageRemaining** | **kotlin.Int** | Remaining SMS count |  |
| **timeAllowance** | **kotlin.Int** | Time allowance in seconds |  |
| **packageTemplate** | [**CreatePackageResponsePackageTemplate**](CreatePackageResponsePackageTemplate.md) |  |  |
| **apn** | **kotlin.String** | Access Point Name |  |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | NOT_ACTIVE, ACTIVE, SUSPENDED, TERMINATED |



