# MailSlurp\Swagger\UserControllerApi

All URIs are relative to *https://api.mailslurp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getUserUsingGET**](UserControllerApi.md#getUserUsingGET) | **GET** /user | Fetch a user


# **getUserUsingGET**
> \MailSlurp\Swagger\MailSlurp\Swagger\Model\UserDto getUserUsingGET($jwtToken)

Fetch a user

Used by the dashboard to fetch user information.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MailSlurp\Swagger\Api\UserControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$jwtToken = "jwtToken_example"; // string | jwtToken

try {
    $result = $apiInstance->getUserUsingGET($jwtToken);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UserControllerApi->getUserUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **jwtToken** | **string**| jwtToken |

### Return type

[**\MailSlurp\Swagger\MailSlurp\Swagger\Model\UserDto**](../Model/UserDto.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

