---
title: "Bing Ads Scripts Iterators"
description: "Describes how iterators work in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Iterators

Iterators are used to enumerate items in a list such as a list of keywords or campaigns. Iterators are similar to arrays but because the list size is not known it is not possible to use an index to directly access an item. Iterators also help reduce memory pressure by loading only a single item at a time rather than the entire set of items.  Methods defined on iterators are as follows:

- <code>boolean hasNext()</code> &mdash; Returns true if the current position is not the last element in the list.
- <code>Object next()</code> &mdash; Advances the current position and returns the object at the new position in the list.
- <code>totalNumEntities()</code> &mdash; Returns the number of items the iterator would retrieve.

The following code demonstrates the usage of an iterator over all campaigns in your account:

```javascript
var campaignIterator = BingAdsApp.campaigns().get();

while (campaignIterator.hasNext()) {
  var campaign = campaignIterator.next();
  Logger.log(campaign.getName() +
      "; active? " + campaign.isEnabled() +
      "; budget=" + campaign.getBudget());
}
```

See also:
- [AdGroupIterator](../reference/AdGroupIterator)
- [CampaignIterator](../reference/CampaignIterator)
- [KeywordIterator](../reference/KeywordIterator)
- [NegativeKeywordListIterator](../reference/NegativeKeywordListIterator)

### Next Steps

> [!div class="nextstepaction"]
> [Learn about builders](./builders.md)