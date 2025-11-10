# PackagesApi

All URIs are relative to *https://esim.betatel.com/api/v1/esim*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**activatePackage**](PackagesApi.md#activatePackage) | **POST** /packages/{id}/activate | Activate a package |
| [**createPackage**](PackagesApi.md#createPackage) | **POST** /packages | Create a new package |
| [**getPackage**](PackagesApi.md#getPackage) | **GET** /packages/{id} | Get package by ID |
| [**getPackages**](PackagesApi.md#getPackages) | **GET** /packages | Get list of packages |
| [**terminatePackage**](PackagesApi.md#terminatePackage) | **POST** /packages/{id}/terminate | Terminate a package |


<a id="activatePackage"></a>
# **activatePackage**
> kotlin.Boolean activatePackage(id)

Activate a package

Activates a specific package for use

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PackagesApi()
val id : kotlin.String = pkg_123456 // kotlin.String | Package ID to activate
try {
    val result : kotlin.Boolean = apiInstance.activatePackage(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PackagesApi#activatePackage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PackagesApi#activatePackage")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.String**| Package ID to activate | |

### Return type

**kotlin.Boolean**

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

<a id="createPackage"></a>
# **createPackage**
> CreatePackageResponse createPackage(createPackageRequest)

Create a new package

Creates a new package for a specific SIM card

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PackagesApi()
val createPackageRequest : CreatePackageRequest =  // CreatePackageRequest | 
try {
    val result : CreatePackageResponse = apiInstance.createPackage(createPackageRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PackagesApi#createPackage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PackagesApi#createPackage")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **createPackageRequest** | [**CreatePackageRequest**](CreatePackageRequest.md)|  | |

### Return type

[**CreatePackageResponse**](CreatePackageResponse.md)

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

<a id="getPackage"></a>
# **getPackage**
> Package getPackage(id)

Get package by ID

Returns detailed information about a specific package

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PackagesApi()
val id : kotlin.String = pkg_123456 // kotlin.String | Package ID
try {
    val result : Package = apiInstance.getPackage(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PackagesApi#getPackage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PackagesApi#getPackage")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.String**| Package ID | |

### Return type

[**Package**](Package.md)

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

<a id="getPackages"></a>
# **getPackages**
> GetPackagesResponse getPackages(count, offset, inventory, packageTemplate, sim, status)

Get list of packages

Returns a paginated and filtered list of packages

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PackagesApi()
val count : kotlin.Int = 56 // kotlin.Int | Number of items to return
val offset : kotlin.Int = 56 // kotlin.Int | Number of items to skip
val inventory : kotlin.Int = 56 // kotlin.Int | Filter by inventory ID
val packageTemplate : kotlin.Int = 56 // kotlin.Int | Filter by package template ID
val sim : kotlin.String = sim_example // kotlin.String | Filter by SIM ICCID
val status : kotlin.String = status_example // kotlin.String | Filter by package status
try {
    val result : GetPackagesResponse = apiInstance.getPackages(count, offset, inventory, packageTemplate, sim, status)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PackagesApi#getPackages")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PackagesApi#getPackages")
    e.printStackTrace()
}
```

### Parameters
| **count** | **kotlin.Int**| Number of items to return | [optional] |
| **offset** | **kotlin.Int**| Number of items to skip | [optional] |
| **inventory** | **kotlin.Int**| Filter by inventory ID | [optional] |
| **packageTemplate** | **kotlin.Int**| Filter by package template ID | [optional] |
| **sim** | **kotlin.String**| Filter by SIM ICCID | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **status** | **kotlin.String**| Filter by package status | [optional] [enum: NOT_ACTIVE, ACTIVE, SUSPENDED, TERMINATED] |

### Return type

[**GetPackagesResponse**](GetPackagesResponse.md)

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

<a id="terminatePackage"></a>
# **terminatePackage**
> kotlin.Boolean terminatePackage(id)

Terminate a package

Terminates an active package

### Example
```kotlin
// Import classes:
//import com.betatel.esim.infrastructure.*
//import com.betatel.esim.models.*

val apiInstance = PackagesApi()
val id : kotlin.String = pkg_123456 // kotlin.String | Package ID to terminate
try {
    val result : kotlin.Boolean = apiInstance.terminatePackage(id)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PackagesApi#terminatePackage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PackagesApi#terminatePackage")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **kotlin.String**| Package ID to terminate | |

### Return type

**kotlin.Boolean**

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

