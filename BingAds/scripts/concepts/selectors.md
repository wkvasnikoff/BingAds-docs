---
title: "Bing Ads Scripts Selectors"
description: "Describes how selectors work in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Selectors

Selectors allow you to specify filter and sort criteria when retrieving Bing Ads entities such as keywords and campaigns.  Selectors provide functionality roughly equivalent to SQL `WHERE` and `ORDER BY` clauses. The selector class supports the following methods.

- <code>withCondition()</code> &mdash; analogous to a SQL `WHERE` clause. Use to specify conditions that entities must meet to be selected. If multiple conditions are used, the selector returns only entities that match all of the specified conditions.<br />Example:<br />
    &nbsp;&nbsp;&nbsp;`withCondition('Name STARTS_WITH "Contoso"')`<br /><br />
- <code>withIds()</code> &mdash; analogous to a SQL `IN` clause. Use to specify the IDs of entities to select.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`withIds([1,2,3,4])`<br /><br />
- <code>forDateRange()</code> &mdash; Use to return entities matching a specified date range. If a condition specifies a metric column, you must include forDateRange in the selector's chain.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`forDateRange("LAST_14_DAYS")`<br /><br />
- <code>orderBy()</code> &mdash; analogous to a SQL `ORDER BY` clause. Use to order the returned entities by a specified field.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`orderBy("Clicks DESC")`<br /><br />
- <code>withLimit()</code> &mdash; analogous to a SQL `TOP` clause. Use to return only the specified number of entities.<br />&nbsp;Example:<br />
    &nbsp;&nbsp;&nbsp;`withLimit(50)`<br /><br />

Because each method returns the selector with the filter criteria applied, you may chain together (using dot notation) multiple conditions to refine the filter criteria. For example:

```javascript
var campaignSelector = BingAdsApp.campaigns()
    .withCondition("Clicks > 10")
    .withCondition("Impressions > 100")
    .orderBy("Impressions DESC")
    .forDateRange("YESTERDAY");
```

To improve script performance, use specific filter conditions to ensure that you retrieve only the entities you want. After getting the selector, call the `get` method to retrieve an iterator that you use to iterate through the list of entities.

See also:
- [AdGroupSelector](../reference/AdGroupSelector)
- [CampaignSelector](../reference/CampaignSelector)
- [KeywordSelector](../reference/KeywordSelector)
- [NegativeKeywordListSelector](../reference/NegativeKeywordListSelector)

### Next Steps

> [!div class="nextstepaction"]
> [Learn about iterators](./iterators.md)
