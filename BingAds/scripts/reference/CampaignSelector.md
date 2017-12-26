# CampaignSelector
Provides methods for selecting campaigns. For information about Selectors, see [Selectors](../concepts/selectors).

Example usage:
```javascript
 var campaignSelector = BingAdsApp
     .campaigns()
     .withCondition("Impressions > 100")
     .forDateRange("LAST_MONTH")
     .orderBy("Clicks DESC");

 var campaignIterator = campaignSelector.get();
 while (campaignIterator.hasNext()) {
   var campaign = campaignIterator.next();
 }
```

See also:
- [CampaignIterator](./CampaignIterator)
- [Campaign](./Campaign)


# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[CampaignSelector](CampaignSelector)|Returns a selector with the start and end dates applied.
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[CampaignSelector](./CampaignSelector)|Returns a selector with the predefined date range applied.
[get](#get)|[CampaignIterator](./CampaignIterator)|Returns an iterator that you use to get campaigns based on the selector's selection criteria.
[orderBy(String orderBy)](#orderby~string-orderby~)|[CampaignSelector](./CampaignSelector)|Returns a selector with the specified ordering applied.
[withCondition(String condition)](#withcondition~string-condition~)|[CampaignSelector](./CampaignSelector)|Returns a selector that limits the campaigns it returns to those that match the filter criteria.
[withIds(long[] ids)](#withids~long-ids~)|[CampaignSelector](./CampaignSelector)|Returns a selector that returns only campaigns with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[CampaignSelector](./CampaignSelector)|Returns a selector that limits the number of campaigns it returns to the top *n* campaigns that match the selection criteria.

## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector with the start and end dates applied. [!INCLUDE[date-range-objects](../includes/date-range-objects.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
dateFrom|Object|Start date of the date range.
dateTo|Object|End date of the date range.
### Returns:
|Type|Description|
|-|-
[CampaignSelector](CampaignSelector)|Selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector with the predefined date range applied. [!INCLUDE[date-range-constants](../includes/date-range-constants.md)] [!INCLUDE[date-range-conditions-message](../includes/date-range-conditions-message.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range to apply to the selector.
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector with date range applied.

## <a name="get"></a>get
Returns an iterator that you use to get campaigns based on the selector's selection criteria.

### Returns:
|Type|Description|
|-|-
[CampaignIterator](./CampaignIterator)|Iterator that you use to get campaigns based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering applied. Specify the orderBy parameter in the form, "columnName orderDirection" where:

- columnName is a supported column, see [Supported Columns](#supported-campaign-columns).
- orderDirection is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns results in ascending order by AverageCpc.

<code>campaignSelector = campaignSelector.orderBy("AverageCpc");</code>

Only one orderBy column is supported.

### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the campaigns it returns to those that match the filter criteria. Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is a supported column, see [Supported Columns](#supported-campaign-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-campaign-columns"></a>
Supported columns for campaign filtering. 

|Column|Type|Example|
|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`
AverageCpm|double|`withCondition("AverageCpm > 0.48")`
AveragePageviews|double|`withCondition("AveragePageviews > 0")`
AveragePosition|double|`withCondition("AveragePosition > 7.5")`
BounceRate|double|`withCondition("BounceRate < 0.5")`
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`
Clicks|long|`withCondition("Clicks >= 21")`
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`
Cost|double|`withCondition("Cost > 4.48")`<br /> The value is in the currency of the account.|Spend
Ctr|double|`withCondition("Ctr > 0.01")`<br /> Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.|CTR
Impressions|long|`withCondition("Impressions != 0")`
&nbsp;|&nbsp;|&nbsp;
<strong>Campaign attributes</strong>|
Status|Enumeration:<br />&nbsp;ENABLED<br />&nbsp;PAUSED<br />&nbsp;REMOVED<br />&nbsp;BUDGET_PAUSED<br />&nbsp;BUDGET_AND_USER_PAUSED|`withCondition("Status = PAUSED")`
Name|String|`withCondition("Name CONTAINS_IGNORE_CASE 'promotion'")`
Budget|double|`withCondition("Budget > 10.0")`
Type|Enumeration:<br />&nbsp;SEARCH_AND_CONTENT<br />&nbsp;SHOPPING<br />&nbsp;DYNAMIC_SEARCH_ADS|`withCondition("Type = 'SEARCH_AND_CONTENT'")`
BudgetType|Enumeration:<br />&nbsp;STANDARD<br />&nbsp;ACCELERATED|`withCondition("BudgetType = 'ACCELERATED'")`
DeliveryStatus|Enumeration:<br />&nbsp;ELIGIBLE<br />&nbsp;LIMITED_BY_BUDGET<br />&nbsp;HOLD<br />&nbsp;CAMPAIGN_OUT_OF_BUDGET<br />&nbsp;CAMPAIGN_SUSPENDED<br />&nbsp;CAMPAIGN_PAUSED|`withCondition("DeliveryStatus NOT IN ['LIMITED_BY_BUDGET', 'HOLD', 'CAMPAIGN_OUT_OF_BUDGET']")`
&nbsp;|&nbsp;|&nbsp;


### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that returns only campaigns with the specified IDs. [!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only campaign 33333.

```javascript
BingAdsApp.campaigns()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 


### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of campaign IDs.
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that limits the number of campaigns it returns to the top *n* campaigns that match the selection criteria.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|Number of results to return.
### Returns:
|Type|Description|
|-|-
[CampaignSelector](./CampaignSelector)|Selector with limit applied.

