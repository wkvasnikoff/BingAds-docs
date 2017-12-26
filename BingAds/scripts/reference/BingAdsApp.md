# BingAdsApp
This is the root object of Bing Ads Scripts API. It provides methods to access different entities such as campaigns and keywords for a single Bing Ads account.
# Methods
|Method Name|Return Type|Description|
|-|-|-
[adGroups](#adgroups)|[AdGroupSelector](./AdGroupSelector)|Returns a selector of all ad groups in this account.
[ads](#ads)|[AdSelector](./AdSelector)|Returns a selector of all ads in this account.<br />
[campaigns](#campaigns)|[CampaignSelector](./CampaignSelector)|Returns a selector of all campaigns in this account.
[getExecutionInfo](#getexecutioninfo)|[ExecutionInfo](./ExecutionInfo)|Returns information about the environment in which the script is currently executing.
[keywords](#keywords)|[KeywordSelector](./KeywordSelector)|Returns a selector of all keywords in this account.
[negativeKeywordLists](#negativekeywordlists)|[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Returns a selector of all negative keyword lists in this account.
[newNegativeKeywordListBuilder](#newnegativekeywordlistbuilder)|[NegativeKeywordListBuilder](./NegativeKeywordListBuilder)|Returns a new negative keyword list builder for this account.

## <a name="adgroups"></a>adGroups
Returns a selector of all ad groups in this account. 

### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|Selector of all ad groups in the current account.

## <a name="ads"></a>ads
Returns a selector of all ads in this account.


### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|Selector of all ads in this account.

## <a name="campaigns"></a>campaigns
Returns a selector of all campaigns in this account. 

### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector of all campaigns in this account.

## <a name="getexecutioninfo"></a>getExecutionInfo
Returns information about the environment in which the script is currently executing.

### Returns:
|Type|Description|
|-|-
[ExecutionInfo](./ExecutionInfo)|Information about the environment in which the script is currently executing.

## <a name="keywords"></a>keywords
Returns a selector of all keywords in this account.

### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector of all keywords in the current account.

## <a name="negativekeywordlists"></a>negativeKeywordLists
Returns a selector of all negative keyword lists in this account. 

### Returns:
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Selector of all negative keyword lists in this account.

## <a name="newnegativekeywordlistbuilder"></a>newNegativeKeywordListBuilder
Returns a new negative keyword list builder for this account. 

### Returns:
|Type|Description|
|-|-
[NegativeKeywordListBuilder](./NegativeKeywordListBuilder)|New negative keyword list builder for the current account.

