# PCRProfileApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getPCRProfile**](PCRProfileApi.md#getPCRProfile) | **GET** /sim-pcr-profiles/{iccid} | Get PCR profile for a SIM card |
| [**modifyPCRProfile**](PCRProfileApi.md#modifyPCRProfile) | **PUT** /sim-pcr-profiles/{iccid} | Modify PCR profile for a SIM card |


<a id="getPCRProfile"></a>
# **getPCRProfile**
> GetPCRProfileResponse getPCRProfile(iccid)

Get PCR profile for a SIM card

Returns the Policy and Charging Rules (PCR) profile configuration for a specific SIM card

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PCRProfileApi()
val iccid : kotlin.String = 8910300000045681955 // kotlin.String | The ICCID of the SIM card (19-20 digits)
try {
    val result : GetPCRProfileResponse = apiInstance.getPCRProfile(iccid)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PCRProfileApi#getPCRProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PCRProfileApi#getPCRProfile")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **iccid** | **kotlin.String**| The ICCID of the SIM card (19-20 digits) | |

### Return type

[**GetPCRProfileResponse**](GetPCRProfileResponse.md)

### Authorization


Configure ApiUserId:
    ApiClient.apiKey["x-user-id"] = ""
    ApiClient.apiKeyPrefix["x-user-id"] = ""
Configure ApiKeyAuth:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="modifyPCRProfile"></a>
# **modifyPCRProfile**
> modifyPCRProfile(iccid, modifyPCRProfileRequest)

Modify PCR profile for a SIM card

Updates the Policy and Charging Rules (PCR) profile for a specific SIM card including data, voice, SMS, and wallet configurations

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PCRProfileApi()
val iccid : kotlin.String = 8910300000045681955 // kotlin.String | The ICCID of the SIM card (19-20 digits)
val modifyPCRProfileRequest : ModifyPCRProfileRequest = {"data":{"state":"ENABLED","active_throttling":"SPEED_1000_KBPS"}} // ModifyPCRProfileRequest | 
try {
    apiInstance.modifyPCRProfile(iccid, modifyPCRProfileRequest)
} catch (e: ClientException) {
    println("4xx response calling PCRProfileApi#modifyPCRProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PCRProfileApi#modifyPCRProfile")
    e.printStackTrace()
}
```

### Parameters
| **iccid** | **kotlin.String**| The ICCID of the SIM card (19-20 digits) | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **modifyPCRProfileRequest** | [**ModifyPCRProfileRequest**](ModifyPCRProfileRequest.md)|  | |

### Return type

null (empty response body)

### Authorization


Configure ApiUserId:
    ApiClient.apiKey["x-user-id"] = ""
    ApiClient.apiKeyPrefix["x-user-id"] = ""
Configure ApiKeyAuth:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

