
# Package

## Properties
| Name | Type                                      | Description | Notes |
| ------------ |-------------------------------------------| ------------- | ------------- |
| **id** | **kotlin.String**                         | Unique package identifier |  |
| **sim** | **kotlin.String**                         | SIM ICCID associated with this package |  |
| **packageTemplate** | [**PackageTemplate**](PackageTemplate.md) | Package template ID |  |
| **status** | [**inline**](#Status)                     | Current package status |  |
| **windowActivationStart** | **kotlin.Long**                           | Unix timestamp for activation window start |  [optional] |
| **windowActivationEnd** | **kotlin.Long**                           | Unix timestamp for activation window end |  [optional] |
| **voiceUsageRemaining** | **kotlin.Long**                           | Remaining voice usage |  [optional] |
| **dataUsageRemaining** | **kotlin.Long**                           | Remaining data usage in bytes |  [optional] |
| **smsUsageRemaining** | **kotlin.Long**                           | Remaining SMS usage |  [optional] |
| **createdDate** | **kotlin.Long**                           | Unix timestamp when package was created |  [optional] |
| **expiryDate** | **kotlin.Long**                           | Unix timestamp when package expires |  [optional] |
| **activationDate** | **kotlin.Long**                           | Unix timestamp when package was activated |  [optional] |
| **terminationDate** | **kotlin.Long**                           | Unix timestamp when package was terminated |  [optional] |
| **timeAllowance** | **kotlin.Long**                           | Time allowance in seconds |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | NOT_ACTIVE, ACTIVE, TERMINATED |



