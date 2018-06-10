# faxplus\NumbersApi

All URIs are relative to *https://restapi.fax.plus/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getNumber**](NumbersApi.md#getNumber) | **GET** /accounts/self/numbers/{number} | Get number information
[**listNumbers**](NumbersApi.md#listNumbers) | **GET** /accounts/self/numbers | Get your numbers
[**revokeNumber**](NumbersApi.md#revokeNumber) | **DELETE** /accounts/self/numbers/{number} | Revoke number
[**updateNumber**](NumbersApi.md#updateNumber) | **PUT** /accounts/self/numbers/{number} | Assign number


# **getNumber**
> \faxplus\model\Number getNumber($number)

Get number information

Get info of a single number

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\NumbersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$number = "number_example"; // string | 

try {
    $result = $apiInstance->getNumber($number);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NumbersApi->getNumber: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **number** | **string**|  |

### Return type

[**\faxplus\model\Number**](../Model/Number.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listNumbers**
> \faxplus\model\ResponseNumberList listNumbers()

Get your numbers

List all your purchased numbers

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\NumbersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listNumbers();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NumbersApi->listNumbers: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\faxplus\model\ResponseNumberList**](../Model/ResponseNumberList.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **revokeNumber**
> revokeNumber($number)

Revoke number

Revoke a specific number from your corporate member

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\NumbersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$number = "number_example"; // string | 

try {
    $apiInstance->revokeNumber($number);
} catch (Exception $e) {
    echo 'Exception when calling NumbersApi->revokeNumber: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **number** | **string**|  |

### Return type

void (empty response body)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateNumber**
> updateNumber($number, $payload_number_modification)

Assign number

With this API call you will be able to assign a specific number to a specific account (one of your members).

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\NumbersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$number = "number_example"; // string | 
$payload_number_modification = new \faxplus\model\PayloadNumberModification(); // \faxplus\model\PayloadNumberModification | 

try {
    $apiInstance->updateNumber($number, $payload_number_modification);
} catch (Exception $e) {
    echo 'Exception when calling NumbersApi->updateNumber: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **number** | **string**|  |
 **payload_number_modification** | [**\faxplus\model\PayloadNumberModification**](../Model/PayloadNumberModification.md)|  |

### Return type

void (empty response body)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

