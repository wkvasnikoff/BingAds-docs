---
title: GetAdExtensionIdsByAccountId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the ad extensions from the account's ad extension library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAdExtensionIdsByAccountId Service Operation - Campaign Management
Gets the ad extensions from the account's ad extension library.

## <a name="request"></a>Request Elements
The *GetAdExtensionIdsByAccountIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that contains the ad extensions to get.|**long**|
|<a name="adextensiontype"></a>AdExtensionType|The types of ad extensions to get from the account. You can specify one or more types. For possible values, see [AdExtensionsTypeFilter](adextensionstypefilter.md).|[AdExtensionsTypeFilter](adextensionstypefilter.md)|
|<a name="associationtype"></a>AssociationType|A value that filters the extensions based on whether they?re associated with a specific entity type. For possible values, see [AssociationType](associationtype.md).<br /><br /> To get all extensions including those not associated with any entity, set this element to NULL.|[AssociationType](associationtype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdExtensionIdsByAccountIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensionids"></a>AdExtensionIds|A list of ad extension IDs. To get the extension, call the [GetAdExtensionsByIds](getadextensionsbyids.md) operation.|**long** array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetAdExtensionIdsByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdExtensionIdsByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <AdExtensionType>ValueHere</AdExtensionType>
      <AssociationType i:nil="false">ValueHere</AssociationType>
    </GetAdExtensionIdsByAccountIdRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdExtensionIdsByAccountIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdExtensionIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AdExtensionIds>
    </GetAdExtensionIdsByAccountIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdExtensionIdsByAccountIdResponse> GetAdExtensionIdsByAccountIdAsync(
	long accountId,
	AdExtensionsTypeFilter adExtensionType,
	AssociationType? associationType)
{
	var request = new GetAdExtensionIdsByAccountIdRequest
	{
		AccountId = accountId,
		AdExtensionType = adExtensionType,
		AssociationType = associationType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdExtensionIdsByAccountIdAsync(r), request));
}
```
```java
static GetAdExtensionIdsByAccountIdResponse getAdExtensionIdsByAccountId(
	java.lang.Long accountId,
	ArrayList<AdExtensionsTypeFilter> adExtensionType,
	AssociationType associationType) throws RemoteException, Exception
{
	GetAdExtensionIdsByAccountIdRequest request = new GetAdExtensionIdsByAccountIdRequest();

	request.setAccountId(accountId);
	request.setAdExtensionType(adExtensionType);
	request.setAssociationType(associationType);

	return CampaignManagementService.getService().getAdExtensionIdsByAccountId(request);
}
```
```php
static function GetAdExtensionIdsByAccountId(
	$accountId,
	$adExtensionType,
	$associationType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdExtensionIdsByAccountIdRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionType = $adExtensionType;
	$request->AssociationType = $associationType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdExtensionIdsByAccountId($request);
}
```
```python
response=campaignmanagement_service.GetAdExtensionIdsByAccountId(
	AccountId=AccountId,
	AdExtensionType=AdExtensionType,
	AssociationType=AssociationType)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

