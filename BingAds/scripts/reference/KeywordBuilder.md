# KeywordBuilder
Provides methods for defining and building a keyword. For information about Builders, see [Builders](../concepts/builders).

Example usage:
```javascript
 var keywordOperation = adGroup.newKeywordBuilder()
    .withText("text")
    .withCpc(1.5)
    .withFinalUrl("http://www.example.com")
    .build();
 var keyword = keywordOperation.getResult();
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[KeywordOperation](./KeywordOperation)|Returns a keyword operation which represents the keyword to create.
[withCpc(double cpc)](#withcpc~double-cpc~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the CPC property set to the specified value.
[withCustomParameters(Object customParameters)](#withcustomparameters~object-customparameters~)|[KeywordBuilder](./KeywordBuilder)|Sets the keyword's custom parameters.
[withFinalUrl(String finalUrl)](#withfinalurl~string-finalurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the final URL set to the specified value.
[withMobileFinalUrl(String mobileFinalUrl)](#withmobilefinalurl~string-mobilefinalurl~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the mobile final URL set to the specified value.
[withText(String text)](#withtext~string-text~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the text set to the specified value.
[withTrackingTemplate( String trackingTemplate)](#withtrackingtemplate~-string-trackingtemplate~)|[KeywordBuilder](./KeywordBuilder)|Returns a keyword builder with the tracking template set to the specified value.

## <a name="build"></a>build
Returns a keyword operation which represents the keyword to create.

### Returns:
|Type|Description|
|-|-
[KeywordOperation](./KeywordOperation)|Keyword operation which represents the keyword to create.

## <a name="withcpc~double-cpc~"></a>withCpc(double cpc)
Returns a keyword builder with the CPC property set to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
cpc|double|Max CPC bid of the keyword.
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the specified max CPC.

## <a name="withcustomparameters~object-customparameters~"></a>withCustomParameters(Object customParameters)
Sets the keyword's custom parameters. [!INCLUDE[custom-parameters](../includes/custom-parameters.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
customParameters|Object|Custom parameters of the keyword as a map of the<br />        following form: <code>{key1: 'value1', key2: 'value2', key3: 'value3'}</code>.
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the custom parameters applied.

## <a name="withfinalurl~string-finalurl~"></a>withFinalUrl(String finalUrl)
Returns a keyword builder with the final URL set to the specified value. The final URL represents the actual landing page for your ad. [!INCLUDE[final-url](../includes/final-url.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
finalUrl|String|Final URL for the keyword.
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the specified final URL.

## <a name="withmobilefinalurl~string-mobilefinalurl~"></a>withMobileFinalUrl(String mobileFinalUrl)
Returns a keyword builder with the mobile final URL set to the specified value. The mobile final URL represents the actual landing page for your ad on a mobile device. The final mobile URL must be the URL of the page that the user ends up on after clicking on your ad on a mobile device, once all the redirects have taken place.

Mobile final URLs follow the same override rules as destination URLs. For example, a mobile final URL at the keyword level overrides a mobile final URL at an ad level.

### Arguments:
|Name|Type|Description|
|-|-|-
mobileFinalUrl|String|Mobile final URL for the keyword.
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the specified final URL.

## <a name="withtext~string-text~"></a>withText(String text)
Returns a keyword builder with the text set to the specified value. To specify match type for the new keyword:

- `keywordBuilder.withText("books")` - broad match.
- `keywordBuilder.withText("\"books\"")` - phrase match.
- `keywordBuilder.withText("[hardcover books]")` - exact match.


### Arguments:
|Name|Type|Description|
|-|-|-
text|String|Text of the keyword.
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the specified text.

## <a name="withtrackingtemplate~-string-trackingtemplate~"></a>withTrackingTemplate( String trackingTemplate)
Returns a keyword builder with the tracking template set to the specified value. [!INCLUDE[tracking-templates](../includes/tracking-templates.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
trackingTemplate|String|Tracking template for the keyword.
### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|Keyword builder with the specified tracking template.

