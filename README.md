# MailSlurp
[MailSlurp](https://www.mailslurp.com) is an end-to-end email testing service. It has a [web-app](https://www.mailslurp.com/dashboard) for managing your account and a [REST API](https://api.mailslurp.com) for sending and receiving emails from randomly generated email addresses.  ## Why? MailSlurp was built to test the integration of email services within an app. If your application relies on the sending or receiving of emails, then MailSlurp will let you test that functionality. This is a more common need than you might think: if your app has a sign up process that requires email verification, how do you currently test that?  ## Getting started - [API Docs](https://www.mailslurp.com/documentation) - [Code Examples](https://www.mailslurp.com/documentation/examples) - [Swagger Definition](https://api.mailslurp.com/v2/api-docs)  Every API request requires a valid API Key appended as a query parameter. [To obtain an API Key visit your account dashboard](https://www.mailslurp.com/dashboard).    The general flow is as follows:  - Create a new inbox during a test. The email address will be returned in the response.  - Send an email to that address or trigger an action in your test that does so. - Fetch the email for your new inbox and check if its content is what you expected, or use the content in another action.  ## SDK - There is an official [Javascript SDK](https://www.npmjs.com/package/mailslurp-client) available on npm. - You can also use the [swagger JSON definition](https://api.mailslurp.com/v2/api-docs) and [swagger-codegen](https://github.com/swagger-api/swagger-codegen) to generate a swagger client in a language of your choice.  ## Legal The Mailslurp API code is owned by [PettmanUG](http://pettmanug.site) and uses a proprietary [software licence](http://www.binpress.com/license/view/l/c8376a01eca7465027a978d3fde5a1e2). The SDKs are free to use in any project and have an ISC licence.  ## Bugs, features, support To report bugs or request features please see the [contact page](https://www.mailslurp.com/contact). For help see [support](https://www.mailslurp.com/support).

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 0.0.1
- Package version: 0.1.0
- Build package: io.swagger.codegen.languages.PhpClientCodegen

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/quartzy/mailslurp-swagger.git"
    }
  ],
  "require": {
    "quartzy/mailslurp-swagger": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/MailSlurp/vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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

## Documentation for API Endpoints

All URIs are relative to *https://api.mailslurp.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*InboxControllerApi* | [**createRandomInboxUsingPOST**](docs/Api/InboxControllerApi.md#createrandominboxusingpost) | **POST** /inboxes | Create an inbox
*InboxControllerApi* | [**deleteInboxUsingDELETE**](docs/Api/InboxControllerApi.md#deleteinboxusingdelete) | **DELETE** /inboxes/{uuid} | Delete an inbox
*InboxControllerApi* | [**getEmailsForInboxUsingGET**](docs/Api/InboxControllerApi.md#getemailsforinboxusingget) | **GET** /inboxes/{uuid} | Fetch emails for a given inbox
*InboxControllerApi* | [**getListOfInboxesUsingGET**](docs/Api/InboxControllerApi.md#getlistofinboxesusingget) | **GET** /inboxes | List your inboxes
*InboxControllerApi* | [**sendEmailFromUserUsingPOST**](docs/Api/InboxControllerApi.md#sendemailfromuserusingpost) | **POST** /inboxes/{uuid} | Send an email
*UserControllerApi* | [**getUserUsingGET**](docs/Api/UserControllerApi.md#getuserusingget) | **GET** /user | Fetch a user


## Documentation For Models

 - [EmailDto](docs/Model/EmailDto.md)
 - [InboxDto](docs/Model/InboxDto.md)
 - [Response](docs/Model/Response.md)
 - [ResponseInboxDto_](docs/Model/ResponseInboxDto_.md)
 - [ResponseListEmailDto_](docs/Model/ResponseListEmailDto_.md)
 - [ResponseListInboxDto_](docs/Model/ResponseListInboxDto_.md)
 - [SendEmailDto](docs/Model/SendEmailDto.md)
 - [UserDto](docs/Model/UserDto.md)


## Documentation For Authorization

 All endpoints do not require authorization.


## Author




