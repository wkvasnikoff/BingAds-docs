# AdGroupUrls
Provides access to the URLs for this ad group. See [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls) for more information.


Example usage:
```javascript
var adGroupSelector = BingAdsApp.adGroups();
 var adGroupIterator = adGroupSelector.get();
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();

   var adGroupUrls = adGroup.urls();
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Clears the tracking template of this ad group.
[getCustomParameters](#getcustomparameters)|Object|Returns the custom parameters of this ad group.
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this ad group.
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the custom parameters of this ad group.
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the tracking template of this ad group.

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Clears the tracking template of this ad group. For information about tracking templates, see [Tracking Templates](/bingads/guides/url-tracking-upgraded-urls#trackingtemplatevalidation).

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom parameters of this ad group. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns:
|Type|Description|
|-|-
Object|Custom parameters of the ad group as a map of the form: `{key1: 'value1', key2: 'value2', key3: 'value3'}`.

## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this ad group. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns:
|Type|Description|
|-|-
String|Tracking template of the ad group.

## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters of this ad group. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

This method replaces any existing custom parameters.

To clear the custom parameters of the ad group pass an empty object (for example, `setCustomParameters({})`).

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|Custom parameters of the ad group as a map of the following form: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(String trackingTemplate)
Sets the tracking template of this ad group. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|Tracking template of the ad group.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

