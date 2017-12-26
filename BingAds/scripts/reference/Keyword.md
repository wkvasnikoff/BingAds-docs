# Keyword
Represents a keyword. For more information, see [Keyword](/bingads/guides/entity-hierarchy-limits#keyword).

See also:

- [KeywordSelector](./KeywordSelector)
- [KeywordIterator](./KeywordIterator)


# Methods
|Method Name|Return Type|Description|
|-|-|-
[bidding](#bidding)|[KeywordBidding](./KeywordBidding)|Provides methods to access keyword bidding details.
[clearDestinationUrl](#cleardestinationurl)|void|Clears the destination URL of this keyword.
[enable](#enable)|void|Enables this keyword.
[getAdGroup](#getadgroup)|[AdGroup](AdGroup)|Returns the ad group this keyword belongs to.
[getCampaign](#getcampaign)|[Campaign](./Campaign)|Returns the campaign this keyword belongs to.
[getEntityType](#getentitytype)|String|Returns the entity type.
[getId](#getid)|long|Returns the ID of this keyword.
[getMatchType](#getmatchtype)|String|Returns the match type of this keyword.
[getStats](#getstats)|[Stats](./Stats)|Returns statistics for this keyword.
[getStatsFor(String dateRange)](#getstatsfor~string-daterange~)|[Stats](./Stats)|Returns an object which provides performance metrics for the predefined date range.
[getText](#gettext)|String|Returns the text of this keyword.
[isEnabled](#isenabled)|Boolean|Returns a Boolean value that determines if this keyword is enabled.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that determines if this keyword is paused.
[pause](#pause)|void|Pauses this keyword.
[remove](#remove)|void|Removes this keyword.
[urls](#urls)|[KeywordUrls](./KeywordUrls)|Returns the URL fields of this keyword.

## <a name="bidding"></a>bidding
Provides methods to access keyword bidding details. 

### Returns:
|Type|Description|
|-|-
[KeywordBidding](./KeywordBidding)|Methods to access information about the keywords bidding.

## <a name="cleardestinationurl"></a>clearDestinationUrl
Clears the destination URL of this keyword.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="enable"></a>enable
Enables this keyword.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getadgroup"></a>getAdGroup
Returns the ad group this keyword belongs to.

### Returns:
|Type|Description|
|-|-
[AdGroup](AdGroup)|Ad group this keyword belongs to.

## <a name="getcampaign"></a>getCampaign
Returns the campaign this keyword belongs to.

### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|Campaign this keyword belongs to.

## <a name="getentitytype"></a>getEntityType
Returns the entity type.

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "Keyword".

## <a name="getid"></a>getId
Returns the ID of this keyword.

### Returns:
|Type|Description|
|-|-
long|ID of this keyword.

## <a name="getmatchtype"></a>getMatchType
Returns the match type of this keyword. Possible return values are:

- BROAD
- PHRASE
- EXACT


### Returns:
|Type|Description|
|-|-
String|Match type of this keyword.

## <a name="getstats"></a>getStats
Returns statistics for this keyword. 

### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|Statistics for the keyword.

## <a name="getstatsfor~string-daterange~"></a>getStatsFor(String dateRange)
Returns an object which provides performance metrics for the predefined date range. [!INCLUDE[date-range-constants](../includes/date-range-constants.md)]


### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range for which the stats are requested.
### Returns:
|Type|Description|
|-|-
[Stats](./Stats)|Performance metrics for the specified date range.

## <a name="gettext"></a>getText
Returns the text of this keyword. The text is returned in one of the following formats based on the keyword's match type:

- books - broad match
- "books" - phrase match
- [hardcover books] - exact match


### Returns:
|Type|Description|
|-|-
String|Text of this keyword.

## <a name="isenabled"></a>isEnabled
Returns a Boolean value that determines if this keyword is enabled.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this keyword is enabled.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that determines if this keyword is paused.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this keyword is paused.

## <a name="pause"></a>pause
Pauses this keyword.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="remove"></a>remove
Removes this keyword.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="urls"></a>urls
Returns the URL fields of this keyword.

### Returns:
|Type|Description|
|-|-
[KeywordUrls](./KeywordUrls)|URL fields of this keyword.

