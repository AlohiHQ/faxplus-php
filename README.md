# FAX.PLUS PHP SDK
This is the FAX.PLUS API v1 developed for third party developers and organizations. In order to have a better coding experience with this API, let's quickly go through some points:
- This API assumes **/accounts** as an entry point with the base url of **https://restapi.fax.plus/v1**. 
- This API treats all date and times sent to it in requests as **UTC**. Also, all dates and times returned in responses are in **UTC**
- Once you have an access_token, you can easily send a request to the resource server with the base url of **https://restapi.fax.plus/v1** to access your permitted resources. As an example to get the user's profile info you would send a request to **https://restapi.fax.plus/v1/accounts/self** when **Authorization** header is set to \"Bearer YOUR_ACCESS_TOKEN\" and custom header of **x-fax-clientid** is set to YOUR_CLIENT_ID

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

You can simply run `composer require faxplus/faxplus-api` to add faxplus-api to your composer.json and install it (faxplus-api is published to packagist).

Alternatively, to install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json` or your local composer config:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/alohi/faxplus-php.git"
    }
  ],
  "require": {
    "faxplus/faxplus-api": "*@dev"
  }
}
```

Then run `composer install`

## Getting Started

There's a [sample application](https://github.com/alohi/faxplus-sample-php) which is intended to get you started using this SDK. Follow sample app instructions to run your first app.

## Documentation for API Endpoints

All URIs are relative to *https://restapi.fax.plus/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountsApi* | [**getAccounts**](docs/Api/AccountsApi.md#getaccounts) | **GET** /accounts | Get account information of all members of your corporate account
*AccountsApi* | [**getMemberDetails**](docs/Api/AccountsApi.md#getmemberdetails) | **GET** /accounts/self/member-details/{member_id} | Get member details
*AccountsApi* | [**getUser**](docs/Api/AccountsApi.md#getuser) | **GET** /accounts/{user_id} | Get account information for admin or member
*AccountsApi* | [**updateMemberDetails**](docs/Api/AccountsApi.md#updatememberdetails) | **PUT** /accounts/self/member-details/{member_id} | Modify member details
*AccountsApi* | [**updateUser**](docs/Api/AccountsApi.md#updateuser) | **PUT** /accounts/self | Modify account information
*ArchivesApi* | [**deleteFax**](docs/Api/ArchivesApi.md#deletefax) | **DELETE** /accounts/self/archives/{fax_id} | Delete a fax
*ArchivesApi* | [**getFax**](docs/Api/ArchivesApi.md#getfax) | **GET** /accounts/self/archives/{fax_id} | Get a fax record
*ArchivesApi* | [**listFaxes**](docs/Api/ArchivesApi.md#listfaxes) | **GET** /accounts/{user_id}/archives | Get fax records
*ArchivesApi* | [**updateFax**](docs/Api/ArchivesApi.md#updatefax) | **PUT** /accounts/self/archives/{fax_id} | Modify fax record
*FilesApi* | [**getFile**](docs/Api/FilesApi.md#getfile) | **GET** /accounts/self/files/{fax_id} | get a file
*FilesApi* | [**uploadFile**](docs/Api/FilesApi.md#uploadfile) | **POST** /accounts/self/files | upload a file
*NumbersApi* | [**getNumber**](docs/Api/NumbersApi.md#getnumber) | **GET** /accounts/self/numbers/{number} | Get number information
*NumbersApi* | [**listNumbers**](docs/Api/NumbersApi.md#listnumbers) | **GET** /accounts/self/numbers | Get your numbers
*NumbersApi* | [**revokeNumber**](docs/Api/NumbersApi.md#revokenumber) | **DELETE** /accounts/self/numbers/{number} | Revoke number
*NumbersApi* | [**updateNumber**](docs/Api/NumbersApi.md#updatenumber) | **PUT** /accounts/self/numbers/{number} | Assign number
*OutboxApi* | [**deleteOutboxFax**](docs/Api/OutboxApi.md#deleteoutboxfax) | **DELETE** /accounts/self/outbox/{outbox_fax_id} | Delete a fax from outbox
*OutboxApi* | [**getOutboxFax**](docs/Api/OutboxApi.md#getoutboxfax) | **GET** /accounts/self/outbox/{outbox_fax_id} | Get an outbox record
*OutboxApi* | [**listOutboxFaxes**](docs/Api/OutboxApi.md#listoutboxfaxes) | **GET** /accounts/self/outbox | Get outbox records
*OutboxApi* | [**sendFax**](docs/Api/OutboxApi.md#sendfax) | **POST** /accounts/self/outbox | Send a fax
*OutboxApi* | [**updateOutboxFax**](docs/Api/OutboxApi.md#updateoutboxfax) | **PUT** /accounts/self/outbox/{outbox_fax_id} | Modify a fax record in outbox


## Documentation For Models

 - [Account](docs/Model/Account.md)
 - [AccountAccountData](docs/Model/AccountAccountData.md)
 - [AccountSettings](docs/Model/AccountSettings.md)
 - [AccountSettingsSendFax](docs/Model/AccountSettingsSendFax.md)
 - [AccountSettingsSendFaxRetry](docs/Model/AccountSettingsSendFaxRetry.md)
 - [Error](docs/Model/Error.md)
 - [Fax](docs/Model/Fax.md)
 - [FaxCostDetails](docs/Model/FaxCostDetails.md)
 - [File](docs/Model/File.md)
 - [MemberDetail](docs/Model/MemberDetail.md)
 - [Number](docs/Model/Number.md)
 - [NumberNotifications](docs/Model/NumberNotifications.md)
 - [Outbox](docs/Model/Outbox.md)
 - [OutboxComment](docs/Model/OutboxComment.md)
 - [OutboxFileChanges](docs/Model/OutboxFileChanges.md)
 - [OutboxFiles](docs/Model/OutboxFiles.md)
 - [OutboxInitiatedFrom](docs/Model/OutboxInitiatedFrom.md)
 - [OutboxStatusChanges](docs/Model/OutboxStatusChanges.md)
 - [PayloadFaxModification](docs/Model/PayloadFaxModification.md)
 - [PayloadNumberModification](docs/Model/PayloadNumberModification.md)
 - [PayloadOutbox](docs/Model/PayloadOutbox.md)
 - [PayloadOutboxComment](docs/Model/PayloadOutboxComment.md)
 - [PayloadOutboxModification](docs/Model/PayloadOutboxModification.md)
 - [PayloadOutboxOptions](docs/Model/PayloadOutboxOptions.md)
 - [PayloadOutboxOptionsRetry](docs/Model/PayloadOutboxOptionsRetry.md)
 - [ResponseAccountList](docs/Model/ResponseAccountList.md)
 - [ResponseArchive](docs/Model/ResponseArchive.md)
 - [ResponseArchiveData](docs/Model/ResponseArchiveData.md)
 - [ResponseNumberList](docs/Model/ResponseNumberList.md)
 - [ResponseOutboxList](docs/Model/ResponseOutboxList.md)


## Documentation For Authorization


## fax_oauth

- **Type**: OAuth
- **Flow**: accessCode
- **Authorization URL**: https://accounts.fax.plus/login?response_type=code&client_id=YOUR_CLIENT_ID&redirect_uri=http://localhost&scope=all
- **Scopes**: 
 - **all**: for now when a user grant permission, all grants will be permitted



