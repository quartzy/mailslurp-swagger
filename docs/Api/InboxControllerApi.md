# MailSlurp\Swagger\InboxControllerApi

All URIs are relative to *https://api.mailslurp.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createRandomInboxUsingPOST**](InboxControllerApi.md#createRandomInboxUsingPOST) | **POST** /inboxes | Create an inbox
[**deleteInboxUsingDELETE**](InboxControllerApi.md#deleteInboxUsingDELETE) | **DELETE** /inboxes/{uuid} | Delete an inbox
[**getEmailsForInboxUsingGET**](InboxControllerApi.md#getEmailsForInboxUsingGET) | **GET** /inboxes/{uuid} | Fetch emails for a given inbox
[**getListOfInboxesUsingGET**](InboxControllerApi.md#getListOfInboxesUsingGET) | **GET** /inboxes | List your inboxes
[**sendEmailFromUserUsingPOST**](InboxControllerApi.md#sendEmailFromUserUsingPOST) | **POST** /inboxes/{uuid} | Send an email


# **createRandomInboxUsingPOST**
> \MailSlurp\Swagger\Model\ResponseInboxDto_ createRandomInboxUsingPOST($apiKey)

Create an inbox

Create a new random inbox and return the id and email address for it. Send emails to this address and they will be stored for this inbox.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MailSlurp\Swagger\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apiKey = "test"; // string | Your API Key. Sign up and find it in your dashboard.

try {
    $result = $apiInstance->createRandomInboxUsingPOST($apiKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->createRandomInboxUsingPOST: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apiKey** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]

### Return type

[**\MailSlurp\Swagger\Model\ResponseInboxDto_**](../Model/ResponseInboxDto_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **deleteInboxUsingDELETE**
> \MailSlurp\Swagger\Model\Response deleteInboxUsingDELETE($apiKey, $uuid)

Delete an inbox

Delete an inbox and all the emails associated with it.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MailSlurp\Swagger\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apiKey = "test"; // string | Your API Key. Sign up and find it in your dashboard.
$uuid = "uuid_example"; // string | The inbox's id.

try {
    $result = $apiInstance->deleteInboxUsingDELETE($apiKey, $uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->deleteInboxUsingDELETE: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apiKey** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]
 **uuid** | **string**| The inbox&#39;s id. |

### Return type

[**\MailSlurp\Swagger\Model\Response**](../Model/Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getEmailsForInboxUsingGET**
> \MailSlurp\Swagger\Model\ResponseListEmailDto_ getEmailsForInboxUsingGET($apiKey, $uuid, $minCount, $maxWait, $since)

Fetch emails for a given inbox

Return a list of emails stored in a given inbox. Each email contains various properties including the email body (in eml format), subject, and sender. The `since` parameter is a ISO8601 LocalDateTime that will filter for emails received on or after the given DateTime. Note that because an inbox may take 5 to 10 seconds to receive an email, you can use the `waitFor` parameter to hold a request open until the desired number of emails is present. If this number is not met after 60 seconds, an error will be returned.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MailSlurp\Swagger\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apiKey = "test"; // string | Your API Key. Sign up and find it in your dashboard.
$uuid = "uuid_example"; // string | The inbox's id.
$minCount = 56; // int | Wait a maximum of 60 seconds for atleast this many emails in an inbox before returning a result.
$maxWait = 789; // int | Maximum seconds API should spend retrying your inbox until the minCount is satisfied
$since = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Filter for emails received on or after this ISO8601 LocalDateTime.

try {
    $result = $apiInstance->getEmailsForInboxUsingGET($apiKey, $uuid, $minCount, $maxWait, $since);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->getEmailsForInboxUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apiKey** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]
 **uuid** | **string**| The inbox&#39;s id. |
 **minCount** | **int**| Wait a maximum of 60 seconds for atleast this many emails in an inbox before returning a result. | [optional]
 **maxWait** | **int**| Maximum seconds API should spend retrying your inbox until the minCount is satisfied | [optional]
 **since** | **\DateTime**| Filter for emails received on or after this ISO8601 LocalDateTime. | [optional]

### Return type

[**\MailSlurp\Swagger\Model\ResponseListEmailDto_**](../Model/ResponseListEmailDto_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getListOfInboxesUsingGET**
> \MailSlurp\Swagger\Model\ResponseListInboxDto_ getListOfInboxesUsingGET($apiKey)

List your inboxes

Return a list of your inboxes. Each inbox has a uuid and an email address. Emails sent to the email address are stored in the inbox and can be fetched via `/inboxes/{uuid}`.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MailSlurp\Swagger\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apiKey = "test"; // string | Your API Key. Sign up and find it in your dashboard.

try {
    $result = $apiInstance->getListOfInboxesUsingGET($apiKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->getListOfInboxesUsingGET: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apiKey** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]

### Return type

[**\MailSlurp\Swagger\Model\ResponseListInboxDto_**](../Model/ResponseListInboxDto_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **sendEmailFromUserUsingPOST**
> \MailSlurp\Swagger\Model\Response sendEmailFromUserUsingPOST($apiKey, $uuid, $sendEmailDto)

Send an email

Send an email from the given inbox's email address. Useful if you need to test a user contacting you, for instance.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new MailSlurp\Swagger\Api\InboxControllerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$apiKey = "test"; // string | Your API Key. Sign up and find it in your dashboard.
$uuid = "uuid_example"; // string | The inbox's id.
$sendEmailDto = new \MailSlurp\Swagger\Model\SendEmailDto(); // \MailSlurp\Swagger\Model\SendEmailDto | The email to send.

try {
    $result = $apiInstance->sendEmailFromUserUsingPOST($apiKey, $uuid, $sendEmailDto);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxControllerApi->sendEmailFromUserUsingPOST: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **apiKey** | **string**| Your API Key. Sign up and find it in your dashboard. | [default to test]
 **uuid** | **string**| The inbox&#39;s id. |
 **sendEmailDto** | [**\MailSlurp\Swagger\Model\SendEmailDto**](../Model/SendEmailDto.md)| The email to send. |

### Return type

[**\MailSlurp\Swagger\Model\Response**](../Model/Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

