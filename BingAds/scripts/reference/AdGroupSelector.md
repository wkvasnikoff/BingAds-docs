# AdGroupSelector
Provides methods for selecting ad groups. For information about Selectors, see [Selectors](../concepts/selectors).

Example usage:
```javascript
var adGroupSelector = BingAdsApp
     .adGroups()
     .withCondition("Impressions > 100")
     .forDateRange("LAST_MONTH")
     .orderBy("Clicks DESC");

 var adGroupIterator = adGroupSelector.get();
 while (adGroupIterator.hasNext()) {
   var adGroup = adGroupIterator.next();
 }
```

See also:
- [AdGroupIterator](./AdGroupIterator)
- [AdGroup](./AdGroup)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with the start and end dates applied.
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with the predefined date range applied.
[get](#get)|[AdGroupIterator](./AdGroupIterator)|Returns an iterator that you use to get ad groups based on the selector's selection criteria.
[orderBy(String orderBy)](#orderby~string-orderby~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector with the specified ordering applied.
[withCondition(String condition)](#withcondition~string-condition~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector that limits the ad groups it returns to those that match the filter criteria.
[withIds(long[] ids)](#withids~long-ids~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector that returns only ad groups with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[AdGroupSelector](./AdGroupSelector)|Returns a selector that limits the number of ad groups it returns to the top *n* ad groups that match the selection criteria.

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
[AdGroupSelector](./AdGroupSelector)|Selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector with the predefined date range applied. [!INCLUDE[date-range-constants](../includes/date-range-constants.md)] [!INCLUDE[date-range-conditions-message](../includes/date-range-conditions-message.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range to apply to the selector.
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|Selector with date range applied.

## <a name="get"></a>get
Returns an iterator that you use to get ad groups based on the selector's selection criteria.

### Returns:
|Type|Description|
|-|-
[AdGroupIterator](./AdGroupIterator)|Iterator that you use to get ad groups based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering applied. Specify the orderBy parameter in the form, "columnName orderDirection" where:

- columnName is a supported column, see [Supported Columns](#supported-ad-group-columns).
- orderDirection is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.


For example, the following call returns results in ascending order by AverageCpc.

<code>adGroupSelector = adGroupSelector.orderBy("AverageCpc");</code>


Only one orderBy column is supported.

### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the ad groups it returns to those that match the filter criteria. Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is a supported column, see [Supported Columns](#supported-ad-group-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-ad-group-columns"></a>
### Supported Columns
Supported columns for ad group filtering. 

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
Cost|double|`withCondition("Cost > 4.48")`<br /> The value is in the currency of the account.
Ctr|double|`withCondition("Ctr > 0.01")`<br /> Note that the Ctr is in the range 0..1, so a 5% Ctr is represented as 0.05.
Impressions|long|`withCondition("Impressions != 0")`
&nbsp;|&nbsp;|&nbsp;
<strong>Ad group attributes</strong>|
Status|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`|`withCondition("Status = PAUSED")`
Name|String|`withCondition("Name CONTAINS_IGNORE_CASE 'shoes'")`
CampaignName|String|`withCondition("CampaignName CONTAINS_IGNORE_CASE 'promotion'")`
KeywordMaxCpc|double|`withCondition("KeywordMaxCpc > 10.0")`<br /> The value is in the currency of the account.
CampaignStatus|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`|`withCondition("CampaignStatus = ENABLED")`<br /> Use to return ad groups from only ENABLED campaigns.
&nbsp;|&nbsp;|&nbsp;

### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|Selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that returns only ad groups with the specified IDs. [!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only ad group 33333.

```javascript
BingAdsApp.adGroups()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 


### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of ad group IDs. The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the get method will fail.
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that limits the number of ad groups it returns to the top *n* ad groups that match the selection criteria.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|Number of results to return.
### Returns:
|Type|Description|
|-|-
[AdGroupSelector](./AdGroupSelector)|Selector with limit applied.

