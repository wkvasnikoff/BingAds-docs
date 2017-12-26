# Campaign
Represents a campaign. For more information, see [Campaign](/bingads/guides/entity-hierarchy-limits#campaign).

# Methods
|Method Name|Return Type|Description|
|-|-|-
[addNegativeKeywordList(NegativeKeywordList negativeKeywordList)](#addnegativekeywordlist~negativekeywordlist-negativekeywordlist~)|void|Adds a negative keyword list to this campaign.
[enable](#enable)|void|Enables this campaign.
[getBiddingStrategyType](#getbiddingstrategytype)|String|Returns the campaign's bidding strategy.
[getBudget](#getbudget)|[Budget](./Budget)|Returns the budget for this campaign.
[getEntityType](#getentitytype)|String|Returns the entity type.
[getId](#getid)|long|Returns the ID of this campaign.
[getName](#getname)|String|Returns the name of this campaign.
[isPaused](#ispaused)|Boolean|Returns a Boolean value that determines if this campaign is paused.
[isRemoved](#isremoved)|Boolean|Returns a Boolean value that determines if this campaign is removed.
[pause](#pause)|void|Pauses this campaign.
[remove](#remove)|void|Removes this campaign.
[setName(String name)](#setname~string-name~)|void|Sets the name of this campaign.
[urls](#urls)|[CampaignUrls](./CampaignUrls)|Returns the URL fields of this campaign.

## <a name="addnegativekeywordlist~negativekeywordlist-negativekeywordlist~"></a>addNegativeKeywordList(NegativeKeywordList negativeKeywordList)
Adds a negative keyword list to this campaign. 

### Arguments:
|Name|Type|Description|
|-|-|-
negativeKeywordList|[NegativeKeywordList](./NegativeKeywordList)|Negative keyword list to add to the campaign.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="enable"></a>enable
Enables this campaign.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getbiddingstrategytype"></a>getBiddingStrategyType
Returns the campaign's bidding strategy. Possible return values are:

<ul>
  <li>ManualCpc</li>
  <li>MaxClicks</li>
  <li>MaxConversions</li>
  <li>EnhancedCpc</li>
  <li>TargetCpa</li>
</ul>

For more information, see [Bid Strategy Types](/bingads/guides/budget-bid-strategies#bidstrategytypes).


### Returns:
|Type|Description|
|-|-
String|Type of the campaign's bidding strategy.

## <a name="getbudget"></a>getBudget
Returns the budget for this campaign.

### Returns:
|Type|Description|
|-|-
[Budget](./Budget)|Budget for this campaign.

## <a name="getentitytype"></a>getEntityType
Returns the entity type.

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "Campaign".

## <a name="getid"></a>getId
Returns the ID of this campaign.

### Returns:
|Type|Description|
|-|-
long|ID of this campaign.

## <a name="getname"></a>getName
Returns the name of this campaign.

### Returns:
|Type|Description|
|-|-
String|Name of this campaign.

## <a name="ispaused"></a>isPaused
Returns a Boolean value that determines if this campaign is paused.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this campaign is paused.

## <a name="isremoved"></a>isRemoved
Returns a Boolean value that determines if this campaign is removed.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this campaign is removed.

## <a name="pause"></a>pause
Pauses this campaign.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="remove"></a>remove
Removes this campaign.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this campaign.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|New name for the campaign.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="urls"></a>urls
Returns the URL fields of this campaign.

### Returns:
|Type|Description|
|-|-
[CampaignUrls](./CampaignUrls)|URL fields of this campaign.

