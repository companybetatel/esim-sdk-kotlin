# PCRApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createPackageTemplate**](PCRApi.md#createPackageTemplate) | **POST** /package-templates | Create a new package template |
| [**getPackageTemplate**](PCRApi.md#getPackageTemplate) | **GET** /package-templates/{id} | Get package template by ID |
| [**getPackageTemplates**](PCRApi.md#getPackageTemplates) | **GET** /package-templates | Get list of package templates |


<a id="createPackageTemplate"></a>
# **createPackageTemplate**
> CreatePackageTemplateResponse createPackageTemplate(createPackageTemplateRequest)

Create a new package template

Creates a new package template with specified data, time, and activation configurations

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PCRApi()
val createPackageTemplateRequest : CreatePackageTemplateRequest =  // CreatePackageTemplateRequest | 
try {
    val result : CreatePackageTemplateResponse = apiInstance.createPackageTemplate(createPackageTemplateRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PCRApi#createPackageTemplate")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PCRApi#createPackageTemplate")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createPackageTemplateRequest** | [**CreatePackageTemplateRequest**](CreatePackageTemplateRequest.md)|  | |

### Return type

[**CreatePackageTemplateResponse**](CreatePackageTemplateResponse.md)

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

<a id="getPackageTemplate"></a>
# **getPackageTemplate**
> PackageTemplate getPackageTemplate(id)

Get package template by ID

Returns detailed information about a specific package template

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PCRApi()
val id : kotlin.Int = 21145354 // kotlin.Int | Package template ID
try {
    val result : PackageTemplate = apiInstance.getPackageTemplate(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PCRApi#getPackageTemplate")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PCRApi#getPackageTemplate")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.Int**| Package template ID | |

### Return type

[**PackageTemplate**](PackageTemplate.md)

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

<a id="getPackageTemplates"></a>
# **getPackageTemplates**
> GetPackageTemplatesResponse getPackageTemplates(count, offset, inventory)

Get list of package templates

Returns a paginated list of all available package templates with optional filtering

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PCRApi()
val count : kotlin.Int = 56 // kotlin.Int | Number of items to return
val offset : kotlin.Int = 56 // kotlin.Int | Number of items to skip
val inventory : kotlin.Int = 56 // kotlin.Int | Filter by inventory ID (optional)
try {
    val result : GetPackageTemplatesResponse = apiInstance.getPackageTemplates(count, offset, inventory)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PCRApi#getPackageTemplates")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PCRApi#getPackageTemplates")
    e.printStackTrace()
}
```

### Parameters
| **count** | **kotlin.Int**| Number of items to return | [optional] [default to 100] |
| **offset** | **kotlin.Int**| Number of items to skip | [optional] [default to 0] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **inventory** | **kotlin.Int**| Filter by inventory ID (optional) | [optional] |

### Return type

[**GetPackageTemplatesResponse**](GetPackageTemplatesResponse.md)

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

