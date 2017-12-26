# KeywordSelector
Provides methods for selecting keywords. For information about Selectors, see [Selectors](../concepts/selectors).
See also:

- [KeywordIterator](./KeywordIterator)
- [Keyword](./Keyword)


# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[KeywordSelector](./KeywordSelector)|Returns a selector with the start and end dates applied.
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[KeywordSelector](./KeywordSelector)|Returns a selector with the predefined date range applied.
[get](#get)|[KeywordIterator](./KeywordIterator)|Returns an iterator that you use to get keywords based on the selector's selection criteria.
[orderBy(String orderBy)](#orderby~string-orderby~)|[KeywordSelector](./KeywordSelector)|Returns a selector with the specified ordering applied.
[withCondition(String condition)](#withcondition~string-condition~)|[KeywordSelector](./KeywordSelector)|Returns a selector that limits the keywords it returns to those that match the filter criteria.
[withIds(long[] ids)](#withids~long-ids~)|[KeywordSelector](./KeywordSelector)|Returns a selector that returns only keywords with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[KeywordSelector](./KeywordSelector)|Returns a selector that limits the number of keywords it returns to the top *n* keywords that match the selection criteria.

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
[KeywordSelector](./KeywordSelector)|Selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector with the predefined date range applied. [!INCLUDE[date-range-constants](../includes/date-range-constants.md)] [!INCLUDE[date-range-conditions-message](../includes/date-range-conditions-message.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range to apply to the selector.
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector with date range applied.

## <a name="get"></a>get
Returns an iterator that you use to get keywords based on the selector's selection criteria.

### Returns:
|Type|Description|
|-|-
[KeywordIterator](./KeywordIterator)|Iterator that you use to get keywords based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering applied. Specify the orderBy parameter in the form, "columnName orderDirection" where:

- columnName is a supported column, see [Supported Columns](#supported-keyword-columns).
- orderDirection is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns results in ascending order by AverageCpc.

<code>keywordSelector = keywordSelector.orderBy("AverageCpc");</code>

[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the keywords it returns to those that match the filter criteria. Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is a supported column, see [Supported Columns](#supported-keyword-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-keyword-columns"></a>
Supported columns for keyword filtering. 

|Column|Type|Example|Bing Web UI filter|
|-|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`|Avg. CPC
AverageCpm|double|`withCondition("AverageCpm > 0.48")`|Avg. CPM
AveragePageviews|double|`withCondition("AveragePageviews > 0")`|
AveragePosition|double|`withCondition("AveragePosition > 7.5")`|Avg. pos.
BounceRate|double|`withCondition("BounceRate < 0.5")`|
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`|Conv. Rate
Clicks|long|`withCondition("Clicks >= 21")`|Clicks
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`|Conv.
Cost|double|`withCondition("Cost > 4.48"). The value is in the currency of the account.`|Spend
Ctr|double|`withCondition("Ctr > 0.01"). Note that Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.`|CTR
Impressions|long|`withCondition("Impressions != 0")`|Impr.
&nbsp;|&nbsp;|&nbsp;|&nbsp;
<strong>Keyword</strong>|
Status|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`DISABLED`|`withCondition("Status = PAUSED")`|Status
Text|String|`withCondition("Text STARTS_WITH 'books'")`|Keyword Text
KeywordMatchType|Enumeration:<br />&nbsp;`BROAD`<br />&nbsp;`EXACT`<br />&nbsp;`PHRASE`<br />&nbsp;`CONTENT`|`withCondition("KeywordMatchType = EXACT")`|Match type
MaxCpc|double|`withCondition("MaxCpc > 0.40"). The value specified is in the currency of the current account.`|Bid
DestinationUrl|String|`withCondition("DestinationUrl STARTS_WITH 'http://www.example.com'")`|Destination URL
FinalUrls|String|`withCondition("FinalUrls CONTAINS 'http://www.example.com'")`|
QualityScore|int|`withCondition("QualityScore > 5")`|Qual. score
FirstPageCpc|double|`withCondition("FirstPageCpc > 6.00"). The value specified is in the currency of the current account.`|Est. first page bid
TopOfPageCpc|double|`withCondition("TopOfPageCpc > 8.00"). The value specified is in the currency of the current account.`|Est. mainline bid
&nbsp;|&nbsp;|&nbsp;|&nbsp;


### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that returns only keywords with the specified IDs. [!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only keyword 33333.

```javascript
BingAdsApp.keywords()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[][]|Array of keyword IDs.
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that limits the number of keywords it returns to the top *n* keywords that match the selection criteria.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|Number of results to return.
### Returns:
|Type|Description|
|-|-
[KeywordSelector](./KeywordSelector)|Selector with limit applied.

