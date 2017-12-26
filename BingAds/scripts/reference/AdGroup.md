# AdGroup
Represents an ad group.  For more information, see [Ad Group](/bingads/guides/entity-hierarchy-limits#adgroup).
# Methods
|Method Name|Return Type|Description|
|-|-|-
[enable](#enable)|void|Enables this ad group.
[getEntityType](#getentitytype)|String|Returns the entity type.
[getId](#getid)|long|Returns the ID of this ad group.
[getName](#getname)|String|Returns the name of this ad group.
[isEnabled](#isenabled)|Boolean|Returns a Boolean value that determines if this ad group is enabled.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that determines if this ad group is paused.
[newAd](#newad)|[AdBuilderSpace](./AdBuilderSpace)|Returns a new ad builder space associated with this ad group, which is used to construct a new ad.
[newKeywordBuilder](#newkeywordbuilder)|[KeywordBuilder](./KeywordBuilder)|Returns a new keyword builder associated with this ad group that is used to construct a new keyword.
[pause](#pause)|void|Pauses this ad group.
[setName(String name)](#setname~string-name~)|void|Sets the name of this ad group.
[urls](#urls)|[AdGroupUrls](./AdGroupUrls)|Returns this ad group's URLs.

## <a name="enable"></a>enable
Enables this ad group.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getentitytype"></a>getEntityType
Returns the entity type.

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "AdGroup".

## <a name="getid"></a>getId
Returns the ID of this ad group.

### Returns:
|Type|Description|
|-|-
long|ID of the ad group.

## <a name="getname"></a>getName
Returns the name of this ad group.

### Returns:
|Type|Description|
|-|-
String|Name of the ad group.

## <a name="isenabled"></a>isEnabled
Returns a Boolean value that determines if this ad group is enabled.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this ad group is enabled.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that determines if this ad group is paused.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this ad group is paused.

## <a name="newad"></a>newAd
Returns a new ad builder space associated with this ad group, which is used to construct a new ad.

### Returns:
|Type|Description|
|-|-
[AdBuilderSpace](./AdBuilderSpace)|A new ad builder space associated with this ad group.

## <a name="newkeywordbuilder"></a>newKeywordBuilder
Returns a new keyword builder associated with this ad group that is used to construct a new keyword.

### Returns:
|Type|Description|
|-|-
[KeywordBuilder](./KeywordBuilder)|New keyword builder associated with this ad group that is used to construct a new keyword.

## <a name="pause"></a>pause
Pauses this ad group.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this ad group.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Name of the ad group. Can contain a maximum of 256 characters, and must be unique among all active ad groups within the campaign.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="urls"></a>urls
Returns this ad group's URLs.

### Returns:
|Type|Description|
|-|-
[AdGroupUrls](./AdGroupUrls)|This ad group's urls.

