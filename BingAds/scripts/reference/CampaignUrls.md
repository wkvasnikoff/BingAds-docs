# CampaignUrls
Provides access to the URLs for this campaign. See [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls) for more information.
# Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Clears the tracking template of this campaign.
[getCustomParameters](#getcustomparameters)|Object|Returns the custom parameters of this campaign.
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this campaign.
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the custom parameters of this campaign.
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the tracking template of this campaign.

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Clears the tracking template of this campaign. For information about tracking templates, see [Tracking Templates](/bingads/guides/url-tracking-upgraded-urls#trackingtemplatevalidation).

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom parameters of this campaign.  [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns:
|Type|Description|
|-|-
Object|Custom parameters of the campaign as a map of the following form: `{key1: 'value1', key2: 'value2', key3: 'value3'}`.

## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this campaign. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns:
|Type|Description|
|-|-
String|Tracking template of the campaign.

## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters of this campaign. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

This method will replace any existing custom parameters.

To clear the custom parameters of the campaign pass an empty object, for example `setCustomParamters({})`.  If custom parameters are cleared at a lower level entity (for example a keyword). and custom parameters are specified on a higher level entity, (for example, the parent ad group), then Bing Ads uses the custom parameters specified at the higher level (for example, the ad group custom parameters will be used).  To completely clear custom parameters they must be cleared at all levels.

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|Custom parameters of the campaign as a map of the<br /> form <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(String trackingTemplate)
Sets the tracking template of this campaign. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|Tracking template of the campaign.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

