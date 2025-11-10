# ESIMRSPApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getEUICCProfile**](ESIMRSPApi.md#getEUICCProfile) | **GET** /euicc-profiles/{iccid} | Get eUICC profile for eSIM |
| [**getQRCode**](ESIMRSPApi.md#getQRCode) | **GET** /euicc-profiles/{iccid}/qrcode | Generate QR code for eSIM |


<a id="getEUICCProfile"></a>
# **getEUICCProfile**
> GetEUICCProfileResponse getEUICCProfile(iccid)

Get eUICC profile for eSIM

Returns the eUICC profile information for a specific ICCID

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = ESIMRSPApi()
val iccid : kotlin.String = 8910300000045681955 // kotlin.String | The ICCID of the eSIM (19-20 digits)
try {
    val result : GetEUICCProfileResponse = apiInstance.getEUICCProfile(iccid)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ESIMRSPApi#getEUICCProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ESIMRSPApi#getEUICCProfile")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **iccid** | **kotlin.String**| The ICCID of the eSIM (19-20 digits) | |

### Return type

[**GetEUICCProfileResponse**](GetEUICCProfileResponse.md)

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

<a id="getQRCode"></a>
# **getQRCode**
> java.io.File getQRCode(iccid)

Generate QR code for eSIM

Generates a QR code image containing the LPA activation code for eSIM provisioning

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = ESIMRSPApi()
val iccid : kotlin.String = 8910300000045681955 // kotlin.String | The ICCID of the eSIM (19-20 digits)
try {
    val result : java.io.File = apiInstance.getQRCode(iccid)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ESIMRSPApi#getQRCode")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ESIMRSPApi#getQRCode")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **iccid** | **kotlin.String**| The ICCID of the eSIM (19-20 digits) | |

### Return type

[**java.io.File**](java.io.File.md)

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

