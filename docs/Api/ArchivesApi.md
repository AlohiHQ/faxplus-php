# faxplus\ArchivesApi

All URIs are relative to *https://restapi.fax.plus/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**deleteFax**](ArchivesApi.md#deleteFax) | **DELETE** /accounts/self/archives/{fax_id} | Delete a fax
[**getFax**](ArchivesApi.md#getFax) | **GET** /accounts/self/archives/{fax_id} | Get a fax record
[**listFaxes**](ArchivesApi.md#listFaxes) | **GET** /accounts/{user_id}/archives | Get fax records
[**updateFax**](ArchivesApi.md#updateFax) | **PUT** /accounts/self/archives/{fax_id} | Modify fax record


# **deleteFax**
> object deleteFax($fax_id)

Delete a fax

Delete a specific fax record by providing its id

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\ArchivesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$fax_id = "fax_id_example"; // string | 

try {
    $result = $apiInstance->deleteFax($fax_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ArchivesApi->deleteFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fax_id** | **string**|  |

### Return type

**object**

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getFax**
> \faxplus\model\Fax getFax($fax_id)

Get a fax record

Get a specific fax record details like duration, pages etc.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\ArchivesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$fax_id = "fax_id_example"; // string | 

try {
    $result = $apiInstance->getFax($fax_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ArchivesApi->getFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fax_id** | **string**|  |

### Return type

[**\faxplus\model\Fax**](../Model/Fax.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listFaxes**
> \faxplus\model\ResponseArchive listFaxes($user_id, $category, $after, $before, $limit)

Get fax records

With this API call you will be able to retrieve a collection of faxes (either sent or received or spam based on the category selected). If you want to filter your archive please provide the `category` parameter

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\ArchivesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_id = "user_id_example"; // string | 'self' or user id of a corporate member
$category = "category_example"; // string | Category parameter can be one of these values: **inbox**, **sent**, **spam**
$after = "after_example"; // string | Start date to get records from that date
$before = "before_example"; // string | End date to get records before that date
$limit = 56; // int | Limit of fax records you want to get per request

try {
    $result = $apiInstance->listFaxes($user_id, $category, $after, $before, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ArchivesApi->listFaxes: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **string**| &#39;self&#39; or user id of a corporate member |
 **category** | **string**| Category parameter can be one of these values: **inbox**, **sent**, **spam** | [optional]
 **after** | **string**| Start date to get records from that date | [optional]
 **before** | **string**| End date to get records before that date | [optional]
 **limit** | **int**| Limit of fax records you want to get per request | [optional]

### Return type

[**\faxplus\model\ResponseArchive**](../Model/ResponseArchive.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateFax**
> updateFax($fax_id, $payload_fax_modification)

Modify fax record

You can modify a fax record's comment or mark it as read

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\ArchivesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$fax_id = "fax_id_example"; // string | 
$payload_fax_modification = new \faxplus\model\PayloadFaxModification(); // \faxplus\model\PayloadFaxModification | 

try {
    $apiInstance->updateFax($fax_id, $payload_fax_modification);
} catch (Exception $e) {
    echo 'Exception when calling ArchivesApi->updateFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fax_id** | **string**|  |
 **payload_fax_modification** | [**\faxplus\model\PayloadFaxModification**](../Model/PayloadFaxModification.md)|  |

### Return type

void (empty response body)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

