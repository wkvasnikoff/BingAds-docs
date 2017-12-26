# AdGroupIterator
Provides methods to iterate through a list of ad groups. For information about Iterators, see [Iterators](../concepts/iterators).

Example usage:
```javascript
var adGroupSelector = BingAdsApp.adGroups();
var adGroupIterator = adGroupSelector.get();
while (adGroupIterator.hasNext()) {
  var adGroup = adGroupIterator.next();
}
```

See also:
- [AdGroupSelector.get()](./AdGroupSelector#get)
- [AdGroup](./AdGroup)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that determines if this iterator has more elements.
[next](#next)|[AdGroup](./AdGroup)|Advances to the next ad group in this iterator and returns it.
[totalNumEntities](#totalnumentities)|int|Returns the number of ad groups matched by the selector which generated this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that determines if this iterator has more elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more elements.

## <a name="next"></a>next
Advances to the next ad group in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|Next ad group in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of ad groups matched by the selector which generated this iterator. [!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns:
|Type|Description|
|-|-
int|Number of ad groups matched by the selector which generated this iterator.

