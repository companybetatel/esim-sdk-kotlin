# SystemApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getStatus**](SystemApi.md#getStatus) | **GET** /api/v1/status | Check API status |


<a id="getStatus"></a>
# **getStatus**
> StatusResponse getStatus()

Check API status

Returns the current status of the eSIM API service, including version information and health check

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = SystemApi()
try {
    val result : StatusResponse = apiInstance.getStatus()
    println(result)
} catch (e: ClientException) {
    println("4xx response calling SystemApi#getStatus")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling SystemApi#getStatus")
    e.printStackTrace()
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**StatusResponse**](StatusResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

