
# CreatePackageResponse

## Properties
| Name | Type                                                                                | Description | Notes |
| ------------ |-------------------------------------------------------------------------------------| ------------- | ------------- |
| **id** | **kotlin.String**                                                                   | Created package ID |  |
| **sim** | **kotlin.String**                                                                   | SIM ICCID |  |
| **createdDate** | **kotlin.Long**                                                                     | Unix timestamp of package creation |  |
| **expiryDate** | **kotlin.Long**                                                                      | Unix timestamp of package expiry |  |
| **activatedDate** | **kotlin.Long**                                                                      | Unix timestamp when package was activated (0 if not activated) |  |
| **terminatedDate** | **kotlin.Long**                                                                      | Unix timestamp when package was terminated (0 if not terminated) |  |
| **windowActivationStart** | **kotlin.Long**                                                                      | Unix timestamp of activation window start |  |
| **windowActivationEnd** | **kotlin.Long**                                                                      | Unix timestamp of activation window end |  |
| **status** | [**inline**](#Status)                                                               | Current package status |  |
| **voiceUsageRemaining** | **kotlin.Long**                                                                      | Remaining voice minutes |  |
| **dataUsageRemaining** | **kotlin.Long**                                                                      | Remaining data in bytes |  |
| **smsUsageRemaining** | **kotlin.Long**                                                                      | Remaining SMS count |  |
| **timeAllowance** | **kotlin.Long**                                                                      | Time allowance in seconds |  |
| **packageTemplate** | [**CreatePackageResponsePackageTemplate**](CreatePackageResponsePackageTemplate.md) |  |  |
| **apn** | **kotlin.String**                                                                   | Access Point Name |  |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | NOT_ACTIVE, ACTIVE, SUSPENDED, TERMINATED |



