# faxplus\FilesApi

All URIs are relative to *https://restapi.fax.plus/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getFile**](FilesApi.md#getFile) | **GET** /accounts/self/files/{fax_id} | get a file
[**uploadFile**](FilesApi.md#uploadFile) | **POST** /accounts/self/files | upload a file


# **getFile**
> \SplFileObject getFile($fax_id, $format)

get a file

Get your fax archive file using it's id.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\FilesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$fax_id = "fax_id_example"; // string | 
$format = "format_example"; // string | can be 'pdf' or 'tiff'

try {
    $result = $apiInstance->getFile($fax_id, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FilesApi->getFile: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fax_id** | **string**|  |
 **format** | **string**| can be &#39;pdf&#39; or &#39;tiff&#39; | [optional]

### Return type

[**\SplFileObject**](../Model/\SplFileObject.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/pdf, image/tiff

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **uploadFile**
> \faxplus\model\File uploadFile($fax_file, $format)

upload a file

Before sending a fax you need to upload your files using this API. In order to upload your fax file, you have to send a `multipart/form-data` request with your file. If the upload was successful you would receive a `file_path` which you can use to send your fax.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: fax_oauth
$config = faxplus\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new faxplus\Api\FilesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$fax_file = "/path/to/file.txt"; // \SplFileObject | 
$format = "format_example"; // string | can be 'pdf' or 'tiff'

try {
    $result = $apiInstance->uploadFile($fax_file, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FilesApi->uploadFile: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fax_file** | **\SplFileObject**|  |
 **format** | **string**| can be &#39;pdf&#39; or &#39;tiff&#39; | [optional]

### Return type

[**\faxplus\model\File**](../Model/File.md)

### Authorization

[fax_oauth](../../README.md#fax_oauth)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

