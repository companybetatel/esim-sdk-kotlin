# CoreApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCountries**](CoreApi.md#getCountries) | **GET** /countries | Get list of countries |


<a id="getCountries"></a>
# **getCountries**
> GetCountriesResponse getCountries(count, offset)

Get list of countries

Returns a paginated list of all available countries with their ISO codes

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = CoreApi()
val count : kotlin.Int = 56 // kotlin.Int | Number of items to return per page
val offset : kotlin.Int = 56 // kotlin.Int | Number of items to skip (for pagination)
try {
    val result : GetCountriesResponse = apiInstance.getCountries(count, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling CoreApi#getCountries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling CoreApi#getCountries")
    e.printStackTrace()
}
```

### Parameters
| **count** | **kotlin.Int**| Number of items to return per page | [optional] [default to 100] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| Number of items to skip (for pagination) | [optional] [default to 0] |

### Return type

[**GetCountriesResponse**](GetCountriesResponse.md)

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

