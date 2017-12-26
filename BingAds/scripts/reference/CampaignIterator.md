# CampaignIterator
Provides methods to iterate through a list of campaigns. For information about Iterators, see [Iterators](../concepts/iterators).

Example usage:
```javascript
var campaignSelector = BingAdsApp.campaigns();
var campaignIterator = campaignSelector.get();
while (campaignIterator.hasNext()) {
  var campaign = campaignIterator.next();
}
```

See also:
- [CampaignSelector.get()](./CampaignSelector#get)
- [Campaign](./Campaign)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that determines if this iterator has more elements.
[next](#next)|[Campaign](./Campaign)|Advances to the next campaign in this iterator and returns it.
[totalNumEntities](#totalnumentities)|int|Returns the number of campaigns matched by the selector which generated this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that determines if this iterator has more elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more elements.

## <a name="next"></a>next
Advances to the next campaign in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[Campaign](./Campaign)|Next campaign in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the number of campaigns matched by the selector which generated this iterator. [!INCLUDE[reads-limit](../includes/reads-limit.md)]

### Returns:
|Type|Description|
|-|-
int|Number of campaigns matched by the selector which generated this iterator.

