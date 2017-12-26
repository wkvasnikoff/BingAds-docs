# BingAdsAccountSelector
Provides methods for selecting accounts. For information about Selectors, see [Selectors](../concepts/selectors).
# Methods
|Method Name|Return Type|Description|
|-|-|-
[executeInParallel(String functionName, String optionalCallbackFunctionName)](#executeinparallel~string-functionname_-string-optionalcallbackfunctionname~)|void|Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName.
[executeInParallel(String functionName, String optionalCallbackFunctionName, String optionalInput)](#executeinparallel~string-functionname_-string-optionalcallbackfunctionname_-string-optionalinput~)|void|Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName. The optional optionalInput argument will be used in the parallel function execution, if specified.
[get](#get)|[BingAdsAccountIterator](./BingAdsAccountIterator)|Returns an iterator that you use to get accounts based on the selector's selection criteria.
[withAccountNumbers(String[] accountNumbers)](#withaccountnumbers~string-accountnumbers~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that will return only bing ads accounts with the specified account numbers.
[withCondition(String condition)](#withcondition~string-condition~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that limits the accounts it returns to those that match the filter criteria.
[withIds(long[] ids)](#withids~long-ids~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that returns only accounts with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[BingAdsAccountSelector](./BingAdsAccountSelector)|Returns a selector that limits the number of accounts it returns to the top *n* accounts that match the selection criteria.

## <a name="executeinparallel~string-functionname_-string-optionalcallbackfunctionname~"></a>executeInParallel(String functionName, String optionalCallbackFunctionName)
Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="executeinparallel~string-functionname_-string-optionalcallbackfunctionname_-string-optionalinput~"></a>executeInParallel(String functionName, String optionalCallbackFunctionName, String optionalInput)
Executes the function indicated by functionName on each BingAdsAccount matched by this selector and optionally invokes the callback function indicated by optionalCallbackFunctionName. The optional optionalInput argument will be used in the parallel function execution, if specified.

### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="get"></a>get
Returns an iterator that you use to get accounts based on the selector's selection criteria.

### Returns:
|Type|Description|
|-|-
[BingAdsAccountIterator](./BingAdsAccountIterator)|Iterator that you use to get accounts based on the selector's selection criteria.

## <a name="withaccountnumbers~string-accountnumbers~"></a>withAccountNumbers(String[] accountNumbers)
Returns a selector that will return only bing ads accounts with the specified account numbers. 
The resulting selector can be further filtered by applying additional conditions to it.  All conditions will be 'AND' concatenated including any other ID based conditions.  For example:

```javascript
BingAdsApp.campaigns()
    .withAccountNumbers([11111, 22222, 33333])
    .withAccountNumbers([33333, 44444, 55555])
```

will only get the campaign with account number 33333 because it would be the only one satisfying both conditions.

The maximum number of account numbers that you may specify is 1,000. If you specify more than 1,000 account numbers, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
accountNumbers|String[]|Array of account numbers.<br />
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector restricted to the specified account numbers.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector that limits the accounts it returns to those that match the filter criteria. Multiple conditions may be chained together:

```javascript
selector = selector
	.withCondition("Clicks > 5")
	.withCondition("Name = 'Contoso'");
```

Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is the name of a performance metric to order the results by. For a list of possible values, see [Supported Columns](#supported-ad-group-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

### Operators
The operator that can be used in a condition depends on the type of column. 
For Integer and Long columns: 

```
<  <=  >  >=  =  !=
```
For Double columns: 
```
<  >
```
For String columns: 
```
=  !=  STARTS_WITH  STARTS_WITH_IGNORE_CASE  CONTAINS
 CONTAINS_IGNORE_CASE  DOES_NOT_CONTAIN  DOES_NOT_CONTAIN_IGNORE_CASE
```
For Enumeration columns: 
```
=  !=  IN []  NOT_IN []
```

Operators are case-sensitive: `starts_with` won't work. 

<a name="supported-ad-group-columns"></a>
### Supported Columns

All columns are case-sensitive.
|Column|Type|Example|
|-|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`|
AverageCpm|double|`withCondition("AverageCpm > 0.48")`|
AveragePosition|double|`withCondition("AveragePosition > 7.5")`|
Clicks|long|`withCondition("Clicks >= 21")`|
ConversionRate|double|`withCondition("ConversionRate > 0.1")`|
Conversions|long|`withCondition("Conversions <= 4")`|
Cost|double|`withCondition("Cost > 4.48")`. The value is in the currency of the account.|
Ctr|double|`withCondition("Ctr > 0.01")`. Note that Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.|
CurrencyCode|String|`withCondition("CurrencyCode = 'USD'")`. The three-letter ISO 4217-formatted currency code of the account.
DateTimeZone|String|`withCondition("DateTimeZone = 'PacificTimeUSCanadaTijuana'")`.
Impressions|long|`withCondition("Impressions != 0")`|
LabelNames|Array|`withCondition("LabelNames CONTAINS 'priority'")`|
ManagerCustomerId|Account ID|`withCondition("ManagerCustomerId IN ['123', '456', '789']")`. Used to select child accounts belonging to a specific submanager.|
Name|String|`withCondition("Name = 'Contoso'")`. The name used by the manager to refer to the client.
&nbsp;|&nbsp;|&nbsp;|

If a stats column is used in the condition, date range must also be specified using forDateRange.

### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that returns only accounts with the specified IDs. 
The resulting selector can be further filtered by applying additional conditions to it.  All conditions will be 'AND' concatenated including any other ID based conditions.  For example:

```javascript
BingAdsApp.campaigns()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

will only get the campaign with ID 33333 because it would be the only one satisfying both conditions.

The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[]|Array of customer IDs.<br />
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector restricted to the specified IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that limits the number of accounts it returns to the top *n* accounts that match the selection criteria.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|Number of results to return.
### Returns:
|Type|Description|
|-|-
[BingAdsAccountSelector](./BingAdsAccountSelector)|Selector with the limit applied.

