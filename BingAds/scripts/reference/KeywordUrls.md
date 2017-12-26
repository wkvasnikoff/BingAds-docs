# KeywordUrls
Provides access to the URLs for this keyword. See [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls) for more information.
# Methods
|Method Name|Return Type|Description|
|-|-|-
[clearTrackingTemplate](#cleartrackingtemplate)|void|Clears the tracking template of this keyword.
[getCustomParameters](#getcustomparameters)|Object|Returns the custom parameters of this keyword.
[getFinalUrl](#getfinalurl)|String|Returns the final URL of this keyword.
[getTrackingTemplate](#gettrackingtemplate)|String|Returns the tracking template of this keyword.
[setCustomParameters(Object customParameters)](#setcustomparameters~object-customparameters~)|void|Sets the custom parameters of this keyword.
[setFinalUrl(String finalUrl)](#setfinalurl~string-finalurl~)|void|Sets the final URL of this keyword.
[setTrackingTemplate(String trackingTemplate)](#settrackingtemplate~string-trackingtemplate~)|void|Sets the tracking template of this keyword.

## <a name="cleartrackingtemplate"></a>clearTrackingTemplate
Clears the tracking template of this keyword. For information about tracking templates, see [Tracking Templates](/bingads/guides/url-tracking-upgraded-urls#trackingtemplatevalidation).

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcustomparameters"></a>getCustomParameters
Returns the custom parameters of this keyword. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Returns:
|Type|Description|
|-|-
Object|Custom parameters of the keyword as a map of the following form: {key1: 'value1', key2: 'value2', key3: 'value3'}.

## <a name="getfinalurl"></a>getFinalUrl
Returns the final URL of this keyword. The final URL represents the actual landing page for your ad. The final URL must be the URL of the page that the user ends up on after clicking on your ad, once all the redirects have taken place.

Final URLs follow the same override rules as destination URLs. For example, a final URL at the keyword level overrides a final URL at an ad level.

### Returns:
|Type|Description|
|-|-
String|Final URL of the keyword.

## <a name="gettrackingtemplate"></a>getTrackingTemplate
Returns the tracking template of this keyword. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Returns:
|Type|Description|
|-|-
String|Tracking template of the keyword.

## <a name="setcustomparameters~object-customparameters~"></a>setCustomParameters(Object customParameters)
Sets the custom parameters of this keyword. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

This method will replace any existing custom parameters.

To clear the keyword's custom parameters, pass an empty object. For example, setCustomParamters({}).  


### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|Custom parameters of the keyword as a map of the<br />        form <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setfinalurl~string-finalurl~"></a>setFinalUrl(String finalUrl)
Sets the final URL of this keyword. The final URL represents the actual landing page for your ad. The final URL must be the URL of the page that the user ends up on after clicking on your ad, once all the redirects have taken place.

Final URLs follow the same override rules as destination URLs. For example, a final URL at the keyword level overrides a final URL at an ad level.


### Arguments:
|Name|Type|Description|
|-|-|-
finalUrl|String|Final URL of the keyword.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="settrackingtemplate~string-trackingtemplate~"></a>setTrackingTemplate(String trackingTemplate)
Sets the tracking template of this keyword. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|Tracking template of the keyword.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

