
# Package

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.String** | Unique package identifier |  |
| **sim** | **kotlin.String** | SIM ICCID associated with this package |  |
| **packageTemplate** | **kotlin.Int** | Package template ID |  |
| **status** | [**inline**](#Status) | Current package status |  |
| **activationDate** | **kotlin.Long** | Unix timestamp when package was activated |  [optional] |
| **terminationDate** | **kotlin.Long** | Unix timestamp when package was terminated |  [optional] |
| **timeAllowance** | **kotlin.Long** | Time allowance in seconds |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | NOT_ACTIVE, ACTIVE, TERMINATED |



