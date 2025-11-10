# InventoryApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getESIM**](InventoryApi.md#getESIM) | **GET** /sim-registries/{iccid} | Get eSIM by ICCID |
| [**getESIMs**](InventoryApi.md#getESIMs) | **GET** /sim-registries | Get list of eSIMs |
| [**getInventories**](InventoryApi.md#getInventories) | **GET** /inventories | Get list of inventories |


<a id="getESIM"></a>
# **getESIM**
> ESIM getESIM(iccid)

Get eSIM by ICCID

Validates and returns detailed eSIM information for a specific ICCID

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = InventoryApi()
val iccid : kotlin.String = 8910300000045681955 // kotlin.String | The ICCID of the eSIM (19-20 digits)
try {
    val result : ESIM = apiInstance.getESIM(iccid)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling InventoryApi#getESIM")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling InventoryApi#getESIM")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **iccid** | **kotlin.String**| The ICCID of the eSIM (19-20 digits) | |

### Return type

[**ESIM**](ESIM.md)

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

<a id="getESIMs"></a>
# **getESIMs**
> GetESIMsResponse getESIMs(count, offset, group, inventory)

Get list of eSIMs

Returns a paginated list of all eSIMs with optional filtering by company and inventory

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = InventoryApi()
val count : kotlin.Int = 56 // kotlin.Int | Number of items to return
val offset : kotlin.Int = 56 // kotlin.Int | Number of items to skip
val group : kotlin.Int = 56 // kotlin.Int | Filter by group ID (optional)
val inventory : kotlin.Int = 56 // kotlin.Int | Filter by inventory ID (optional)
try {
    val result : GetESIMsResponse = apiInstance.getESIMs(count, offset, group, inventory)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling InventoryApi#getESIMs")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling InventoryApi#getESIMs")
    e.printStackTrace()
}
```

### Parameters
| **count** | **kotlin.Int**| Number of items to return | [optional] [default to 100] |
| **offset** | **kotlin.Int**| Number of items to skip | [optional] [default to 0] |
| **group** | **kotlin.Int**| Filter by group ID (optional) | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **inventory** | **kotlin.Int**| Filter by inventory ID (optional) | [optional] |

### Return type

[**GetESIMsResponse**](GetESIMsResponse.md)

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

<a id="getInventories"></a>
# **getInventories**
> GetInventoriesResponse getInventories(count, offset, company)

Get list of inventories

Returns a paginated list of all inventories with optional company filtering

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = InventoryApi()
val count : kotlin.Int = 56 // kotlin.Int | Number of items to return
val offset : kotlin.Int = 56 // kotlin.Int | Number of items to skip
val company : kotlin.Int = 56 // kotlin.Int | Filter by company ID (optional)
try {
    val result : GetInventoriesResponse = apiInstance.getInventories(count, offset, company)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling InventoryApi#getInventories")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling InventoryApi#getInventories")
    e.printStackTrace()
}
```

### Parameters
| **count** | **kotlin.Int**| Number of items to return | [optional] [default to 100] |
| **offset** | **kotlin.Int**| Number of items to skip | [optional] [default to 0] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **company** | **kotlin.Int**| Filter by company ID (optional) | [optional] |

### Return type

[**GetInventoriesResponse**](GetInventoriesResponse.md)

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

