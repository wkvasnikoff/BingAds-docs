---
title: "Bing Ads Scripts Builders"
description: "Describes how builders work in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Builders

Creating an entity is a multi-step process. 

1. Get a builder object and use it to specify the entity’s properties. 
2. Call the build method to create an operation object. (The builder simply creates the entity’s definition.) 
3. Call any of the operation’s methods to create the entity. Typically, you call the getResult method but calling any of the methods creates the entity.

Using a builder you specify the properties of the entity to be built then invoke the `build()` method to return an operation object.  Using the operation object you can determine the outcome of the operation and take appropriate actions. 

The following example demonstrates how to create a keyword using a builder and the operation object.

```javascript
// Retrieve an ad group.
var adGroup = BingAdsApp.adGroups().get().next();

var keywordBuilder = adGroup.newKeywordBuilder()
    .withCpc(1.2)
    .withText("shirts")
    .withFinalUrl("https://www.contoso.com/shirts");

var keywordOperation = keywordBuilder.build();

// Examine the outcome. The call to isSuccessful()
// will block until the operation completes.
if (keywordOperation.isSuccessful()) {
  // Get the result.
  var keyword = keywordOperation.getResult();
} else {
  // Handle the errors.
  var errors = keywordOperation.getErrors();
}
```
See also:
- [AdGroupBuilder](../reference/AdGroupBuilder)
- [ExpandedTextAdBuilder](../reference/ExpandedTextAdBuilder)
- [KeywordBuilder](../reference/KeywordBuilder)
- [NegativeKeywordListBuilder](../reference/NegativeKeywordListBuilder)

### Next Steps

> [!div class="nextstepaction"]
> [Learn about preview mode](./preview-mode.md)