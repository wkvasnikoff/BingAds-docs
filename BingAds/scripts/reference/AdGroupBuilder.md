# AdGroupBuilder
Provides methods for defining and building an ad group. For information about Builders, see [Builders](../concepts/builders).

Example usage:
```javascript
var campaignSelector = BingAdsApp.campaigns();
var campaignIterator = campaignSelector.get();
while(campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var adGroupBuilder = campaign.newAdGroupBuilder();
    var adGroupOperation = adGroupBuilder
        .withName("<AD_GROUP_NAME_GOES_HERE>")
        .withStatus("PAUSED")
        .build();
    
    var adGroup = adGroupOperation.getResult();
}
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[AdGroupOperation](./AdGroupOperation)|Returns an ad group operation which represents the ad group to create.
[withBiddingStrategy(String biddingStrategy)](#withbiddingstrategy~string-biddingstrategy~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the ad group's bidding strategy.
[withCpc(double cpc)](#withcpc~double-cpc~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the maximum CPC bid to use for this new ad group.
[withCustomParameters(Object customParameters)](#withcustomparameters~object-customparameters~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the ad group's custom parameters.
[withName(String name)](#withname~string-name~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the name of this ad group.
[withStatus(String status)](#withstatus~string-status~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the status of this ad group.
[withTrackingTemplate(String trackingTemplate)](#withtrackingtemplate~string-trackingtemplate~)|[AdGroupBuilder](./AdGroupBuilder)|Sets the tracking template of this ad group.

## <a name="build"></a>build
Returns an ad group operation which represents the ad group to create.

### Returns:
|Type|Description|
|-|-
[AdGroupOperation](./AdGroupOperation)|Ad group operation which represents the ad group to create.

## <a name="withbiddingstrategy~string-biddingstrategy~"></a>withBiddingStrategy(String biddingStrategy)
Sets the ad group's bidding strategy. 

### Arguments:
|Name|Type|Description|
|-|-|-
biddingStrategy|String|Bidding strategy of the ad group. Possible values are:<ul><li>ManualCpc</li><li>MaxClicks</li><li>MaxConversions</li><li>EnhancedCpc</li><li>TargetCpa</li></ul>For more information, see [Bid Strategy Types](/bingads/guides/budget-bid-strategies#bidstrategytypes).<br />
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the bidding strategy applied.

## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Sets the maximum CPC bid to use for this new ad group. 

### Arguments:
|Name|Type|Description|
|-|-|-
cpc|double|Max CPC bid of the ad group. If no CPC is specified, the default of 0.30 (USD) is used.
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the specified max CPC.

## <a name="withcustomparameters~object-customparameters~"></a>withCustomParameters(Object customParameters)
Sets the ad group's custom parameters. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|Custom parameters of the ad group in the form:<br /><br /><code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the custom parameters applied.

## <a name="withname~string-name~"></a>withName(String name)
Sets the name of this ad group.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Ad group's name. The string can contain a maximum of 256 characters, and must be unique among all active ad groups within the campaign.
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the name applied.

## <a name="withstatus~string-status~"></a>withStatus(String status)
Sets the status of this ad group. 

### Arguments:
|Name|Type|Description|
|-|-|-
status|String|Ad group's status. If not specified, status defaults to ENABLED.  The following are the possible values: <br/><ul><li>ENABLED</li><li>PAUSED</li><li>REMOVED</li></ul>
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the status applied.

## <a name="withtrackingtemplate~string-trackingtemplate~"></a>withTrackingTemplate(String trackingTemplate)
Sets the tracking template of this ad group. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|Tracking template for the ad group.
### Returns:
|Type|Description|
|-|-
[AdGroupBuilder](./AdGroupBuilder)|Ad group builder with the tracking template applied.

