
# Inventory

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int** | Unique inventory identifier |  |
| **name** | **kotlin.String** | Inventory name |  |
| **createdDate** | **kotlin.Int** | Unix timestamp of creation date |  |
| **modifiedDate** | **kotlin.Int** | Unix timestamp of last modification |  |
| **company** | **kotlin.Int** | Company ID that owns this inventory |  |
| **status** | [**inline**](#Status) | Current inventory status |  |
| **note** | **kotlin.String** | Optional notes about the inventory |  [optional] |
| **deletedDate** | **kotlin.Int** | Unix timestamp of deletion (0 if not deleted) |  [optional] |
| **parentInventory** | **kotlin.Int** | Parent inventory ID (0 if root inventory) |  [optional] |
| **deactivatedDate** | **kotlin.Int** | Unix timestamp of deactivation (0 if active) |  [optional] |
| **wallet** | **kotlin.Int** | Associated wallet ID |  [optional] |
| **whitelist** | **kotlin.Int** | Whitelist configuration ID |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | NOT_ACTIVE, ACTIVE |



