# NegativeKeywordListBuilder
Provides methods for defining and building a negative keywords list. For information about Builders, see [Builders](../concepts/builders).

Example usage:
```javascript
 var negativeKeywordListBuilder = BingAdsApp.newNegativeKeywordListBuilder()
         .withName("NegativeKeywordList");

 var negativeKeywordListOperation = negativeKeywordListBuilder.build();

 var negativeKeywordList = negativeKeywordListOperation.getResult();
```



# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[NegativeKeywordListOperation](./NegativeKeywordListOperation)|Returns a negative keyword list operation which represents the negative keyword list to create.
[withName(String name)](#withname~string-name~)|[NegativeKeywordListBuilder](./NegativeKeywordListBuilder)|Returns a negative keyword list builder with the name set to the specified value.

## <a name="build"></a>build
Returns a negative keyword list operation which represents the negative keyword list to create.

### Returns:
|Type|Description|
|-|-
[NegativeKeywordListOperation](./NegativeKeywordListOperation)|Negative keyword list operation which represents the negative keyword list to create.

## <a name="withname~string-name~"></a>withName(String name)
Returns a negative keyword list builder with the name set to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Name of the negative keyword list.
### Returns:
|Type|Description|
|-|-
[NegativeKeywordListBuilder](./NegativeKeywordListBuilder)|Negative keyword list builder with the name set to the specified value.

