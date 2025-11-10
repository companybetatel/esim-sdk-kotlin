
# ESIM

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **iccid** | **kotlin.String** | Integrated Circuit Card Identifier |  |
| **simStatus** | [**inline**](#SimStatus) | Current status of the SIM |  |
| **group** | [**ESIMGroup**](ESIMGroup.md) |  |  [optional] |
| **inventory** | [**ESIMInventory**](ESIMInventory.md) |  |  [optional] |
| **company** | [**ESIMCompany**](ESIMCompany.md) |  |  [optional] |
| **provisionedDate** | **kotlin.Int** | Unix timestamp when SIM was provisioned |  [optional] |
| **terminatedDate** | **kotlin.Int** | Unix timestamp when SIM was terminated (0 if active) |  [optional] |
| **imsis** | [**kotlin.collections.List&lt;IMSI&gt;**](IMSI.md) | List of associated IMSIs |  [optional] |
| **mappedImsi** | **kotlin.Int** | Currently mapped IMSI |  [optional] |


<a id="SimStatus"></a>
## Enum: sim_status
| Name | Value |
| ---- | ----- |
| simStatus | WAITING_FOR_ASSIGNMENT, ASSIGNED, ACTIVE, SUSPENDED, TERMINATED |



