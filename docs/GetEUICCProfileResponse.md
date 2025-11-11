
# GetEUICCProfileResponse

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **iccid** | **kotlin.String** | Integrated Circuit Card Identifier |  |
| **imsi** | **kotlin.String** | International Mobile Subscriber Identity |  |
| **state** | **kotlin.String** | Current state of the eUICC profile |  |
| **lastOperationDate** | **kotlin.Long** | Unix timestamp of last operation |  |
| **activationCode** | **kotlin.String** | LPA activation code for eSIM provisioning |  |
| **reuseRemainingCount** | **kotlin.Int** | Number of remaining profile reuses |  [optional] |
| **reuseEnabled** | **kotlin.Boolean** | Whether profile reuse is enabled |  [optional] |
| **profileReusePolicy** | [**ProfileReusePolicy**](ProfileReusePolicy.md) |  |  [optional] |
| **releaseDate** | **kotlin.Long** | Unix timestamp of profile release |  [optional] |
| **ccRequired** | **kotlin.Boolean** | Whether confirmation code is required |  [optional] |
| **ccRetries** | **kotlin.Int** | Number of confirmation code retries |  [optional] |
| **eid** | **kotlin.String** | EID (eUICC Identifier) of the eSIM |  [optional] |



