# faxplus\AccountsApi

All URIs are relative to *https://restapi.fax.plus/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAccounts**](AccountsApi.md#getAccounts) | **GET** /accounts | Get account information of all members of your corporate account
[**getMemberDetails**](AccountsApi.md#getMemberDetails) | **GET** /accounts/self/member-details/{member_id} | Get member details
[**getUser**](AccountsApi.md#getUser) | **GET** /accounts/{user_id} | Get account information for admin or member
[**updateMemberDetails**](AccountsApi.md#updateMemberDetails) | **PUT** /accounts/self/member-details/{member_id} | Modify member details
[**updateUser**](AccountsApi.md#updateUser) | **PUT** /accounts/self | Modify account information


# **getAccounts**
> \faxplus\model\ResponseAccountList getAccounts()

Get account information of all members of your corporate account

Only admin account can send request to this endpoint which returns accounts of all members

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getAccounts();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAccounts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\faxplus\model\ResponseAccountList**](../Model/ResponseAccountList.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getMemberDetails**
> \faxplus\model\MemberDetail getMemberDetails($member_id)

Get member details

Get your member details (quota and role)

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$member_id = "member_id_example"; // string | 

try {
    $result = $apiInstance->getMemberDetails($member_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getMemberDetails: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **member_id** | **string**|  |

### Return type

[**\faxplus\model\MemberDetail**](../Model/MemberDetail.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getUser**
> \faxplus\model\Account getUser($user_id)

Get account information for admin or member

Get account information. For members user_id can only be self. form admin it can be user_id of any <br />**In case you want to get your own account information please use *`self`* as an alias for your user_id.**

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_id = "user_id_example"; // string | 

try {
    $result = $apiInstance->getUser($user_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getUser: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **string**|  |

### Return type

[**\faxplus\model\Account**](../Model/Account.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateMemberDetails**
> updateMemberDetails($member_id, $payload_member_detail)

Modify member details

One of the paramters below is needed to modify member information

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$member_id = "member_id_example"; // string | 
$payload_member_detail = new \faxplus\model\MemberDetail(); // \faxplus\model\MemberDetail | 

try {
    $apiInstance->updateMemberDetails($member_id, $payload_member_detail);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->updateMemberDetails: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **member_id** | **string**|  |
 **payload_member_detail** | [**\faxplus\model\MemberDetail**](../Model/MemberDetail.md)|  |

### Return type

void (empty response body)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateUser**
> updateUser($user_id, $payload_account)

Modify account information

You can only modify your account

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_id = "user_id_example"; // string | 
$payload_account = new \faxplus\model\Account(); // \faxplus\model\Account | 

try {
    $apiInstance->updateUser($user_id, $payload_account);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->updateUser: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **string**|  |
 **payload_account** | [**\faxplus\model\Account**](../Model/Account.md)|  |

### Return type

void (empty response body)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

