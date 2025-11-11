 
# ESIMPartial

## Properties
| Name             | Type                                               | Description                            | Notes |
|------------------|----------------------------------------------------|----------------------------------------| ------------- |
| **iccid**        | **kotlin.String**                                  | Integrated Circuit Card Identifier     |  |
| **simStatus**    | [**inline**](#SimStatus)                           | Current status of the SIM              |  |
| **group**        | **kotlin.Int**                                     |                                        |  [optional] |
| **inventory**    | **kotlin.Int**                                     |                                        |  [optional] |
| **company**      | **kotlin.Int**                                     |                                        |  [optional] |
| **createdDate**  | **kotlin.Long**                                    | Unix timestamp when SIM was created    |  [optional] |
| **modifiedDate** | **kotlin.Long**                                    | Unix timestamp when SIM was modified   |  [optional] |
| **imsis**        | [**kotlin.collections.List&lt;IMSI&gt;**](IMSI.md) | List of associated IMSIs               |  [optional] |
| **mappedImsi**   | **kotlin.Long**                                    | Currently mapped IMSI                  |  [optional] |


<a id="SimStatus"></a>
## Enum: sim_status
| Name | Value                                                       |
| ---- |-------------------------------------------------------------|
| simStatus | WAITING_FOR_ASSIGNMENT, PRE_SERVICE, IN_SERVICE, TERMINATED |



