# faxplus\OutboxApi

All URIs are relative to *https://restapi.fax.plus/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**deleteOutboxFax**](OutboxApi.md#deleteOutboxFax) | **DELETE** /accounts/self/outbox/{outbox_fax_id} | Delete a fax from outbox
[**getOutboxFax**](OutboxApi.md#getOutboxFax) | **GET** /accounts/self/outbox/{outbox_fax_id} | Get an outbox record
[**listOutboxFaxes**](OutboxApi.md#listOutboxFaxes) | **GET** /accounts/self/outbox | Get outbox records
[**sendFax**](OutboxApi.md#sendFax) | **POST** /accounts/self/outbox | Send a fax
[**updateOutboxFax**](OutboxApi.md#updateOutboxFax) | **PUT** /accounts/self/outbox/{outbox_fax_id} | Modify a fax record in outbox


# **deleteOutboxFax**
> object deleteOutboxFax($outbox_fax_id)

Delete a fax from outbox

Delete a fax that is being sent and is still in your outbox

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\OutboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$outbox_fax_id = "outbox_fax_id_example"; // string | 

try {
    $result = $apiInstance->deleteOutboxFax($outbox_fax_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OutboxApi->deleteOutboxFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **outbox_fax_id** | **string**|  |

### Return type

**object**

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getOutboxFax**
> \faxplus\model\Outbox getOutboxFax($outbox_fax_id)

Get an outbox record

Get an outbox fax record information

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\OutboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$outbox_fax_id = "outbox_fax_id_example"; // string | 

try {
    $result = $apiInstance->getOutboxFax($outbox_fax_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OutboxApi->getOutboxFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **outbox_fax_id** | **string**|  |

### Return type

[**\faxplus\model\Outbox**](../Model/Outbox.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listOutboxFaxes**
> \faxplus\model\ResponseOutboxList listOutboxFaxes()

Get outbox records

Get outbox fax records information

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\OutboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listOutboxFaxes();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OutboxApi->listOutboxFaxes: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\faxplus\model\ResponseOutboxList**](../Model/ResponseOutboxList.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **sendFax**
> sendFax($payload_outbox)

Send a fax

With this API call you will be able to send a fax (one or more files) to one or more destinations. If you are a corporate member and you don't have a fax number set your **from** parameter to **NO_NUMBER**

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\OutboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$payload_outbox = new \faxplus\model\PayloadOutbox(); // \faxplus\model\PayloadOutbox | 

try {
    $apiInstance->sendFax($payload_outbox);
} catch (Exception $e) {
    echo 'Exception when calling OutboxApi->sendFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **payload_outbox** | [**\faxplus\model\PayloadOutbox**](../Model/PayloadOutbox.md)|  |

### Return type

void (empty response body)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateOutboxFax**
> object updateOutboxFax($outbox_fax_id, $payload_outbox_modification)

Modify a fax record in outbox

Modify outbox record's comment

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\OutboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$outbox_fax_id = "outbox_fax_id_example"; // string | 
$payload_outbox_modification = new \faxplus\model\PayloadOutboxModification(); // \faxplus\model\PayloadOutboxModification | 

try {
    $result = $apiInstance->updateOutboxFax($outbox_fax_id, $payload_outbox_modification);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OutboxApi->updateOutboxFax: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **outbox_fax_id** | **string**|  |
 **payload_outbox_modification** | [**\faxplus\model\PayloadOutboxModification**](../Model/PayloadOutboxModification.md)|  |

### Return type

**object**

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

