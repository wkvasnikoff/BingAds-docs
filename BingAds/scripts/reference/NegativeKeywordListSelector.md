# NegativeKeywordListSelector
Provides methods for selecting negative keyword lists. For information about Selectors, see [Selectors](../concepts/selectors).

Example usage:
```javascript
var negativeKeywordListSelector = BingAdsApp
     .negativeKeywordLists()
     .withCondition("MemberCount > 5")
     .orderBy("Name");

 var negativeKeywordListIterator = negativeKeywordListSelector.get();
 while (negativeKeywordListIterator.hasNext()) {
   var negativeKeywordList = negativeKeywordListIterator.next();
 }
```

See also:
- [NegativeKeywordListIterator](./NegativeKeywordListIterator)
- [NegativeKeywordList](./NegativeKeywordList)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[get](#get)|[NegativeKeywordListIterator](./NegativeKeywordListIterator)|Returns an iterator that you use to get negative keywords lists based on the selector's selection criteria.
[orderBy(String orderBy)](#orderby~string-orderby~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Returns a selector with the specified ordering applied.
[withCondition(String condition)](#withcondition~string-condition~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Returns a selector that limits the negative keyword lists it returns to those that match the filter criteria.
[withIds(long[] ids)](#withids~long-ids~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Returns a selector that returns only negative keyword lists with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Returns a selector that limits the number of negative keyword lists it returns to the top *n* negative keyword lists that match the selection criteria.

## <a name="get"></a>get
Returns an iterator that you use to get negative keywords lists based on the selector's selection criteria.

### Returns:
|Type|Description|
|-|-
[NegativeKeywordListIterator](./NegativeKeywordListIterator)|Iterator that you use to get negative keywords lists based on the selector's selection criteria.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering applied. Specify the orderBy parameter in the form, "columnName orderDirection" where:

- columnName is a supported column, see [Supported Columns](#supported-negative-keyword-list-columns).
- orderDirection is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

For example, the following call returns results in ascending order by MemberCount.

<code>negativeKeywordListSelector = negativeKeywordListSelector.orderBy("MemberCount");</code>

[!INCLUDE[order-by-limit](../includes/order-by-limit.md)]

### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
### Returns:
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the negative keyword lists it returns to those that match the filter criteria. Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is a supported column, see [Supported Columns](#supported-negative-keyword-list-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

[!INCLUDE[operators](../includes/operators.md)]

<a name="supported-negative-keyword-list-columns"></a>
### Supported Columns

|Column|Type|Example|
|-|-|-|-
<strong>Shared Set Attributes</strong>|
MemberCount|int|`withCondition("MemberCount > 5")`
Name|String|`withCondition("Name = 'negative keyword list'")`
ReferenceCount|int|`withCondition("ReferenceCount > 5")`
SharedSetId|double|`withCondition("SharedSetId > 5")`
Status|Enumeration:<br />&nbsp;`ACTIVE`<br />&nbsp;`DELETED`<br />|`withCondition("Status = ACTIVE")`
&nbsp;|&nbsp;|&nbsp;|&nbsp;


### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
### Returns:
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that returns only negative keyword lists with the specified IDs. [!INCLUDE[with-ids-chaining](../includes/with-ids-chaining.md)] For example, the following call selects only negative keywords list 33333.

```javascript
BingAdsApp.negativeKeywordLists()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

[!INCLUDE[maximum-number-of-ids](../includes/maximum-number-of-ids.md)] 



### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of ad group IDs.
### Returns:
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that limits the number of negative keyword lists it returns to the top *n* negative keyword lists that match the selection criteria.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|Number of results to return.
### Returns:
|Type|Description|
|-|-
[NegativeKeywordListSelector](./NegativeKeywordListSelector)|Selector with limit applied.

