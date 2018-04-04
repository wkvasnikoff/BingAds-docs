# KeywordIterator
Provides methods to iterate through a list of keywords. For information about Iterators, see [Iterators](../concepts/iterators).

Example usage:
```javascript
 var keywordSelector = BingAdsApp.keywords();
 var keywordIterator = keywordSelector.get();
 while (keywordIterator.hasNext()) {
   var keyword = keywordIterator.next();
 }
```

See also:

- [KeywordSelector.get()](./KeywordSelector#get)
- [Keyword](./Keyword)


# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that indicates if this iterator has more elements.
[next](#next)|[Keyword](./Keyword)|Advances the iterator and returns the next keyword.
[totalNumEntities](#totalnumentities)|int|Returns the number of keywords matched by the selector which generated this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that indicates if this iterator has more elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more elements.

## <a name="next"></a>next
Advances the iterator and returns the next keyword.

### Returns:
|Type|Description|
|-|-
[Keyword](./Keyword)|Next keyword in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of keywords matched by the selector which generated this iterator. [!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns:
|Type|Description|
|-|-
int|Number of keywords matched by the selector which generated this iterator.

