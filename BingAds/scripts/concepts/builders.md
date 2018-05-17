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

[!INCLUDE[preview-note](../includes/preview-note.md)]

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

## Performance Considerations

Bing Ads Scripts execute operations asynchronously, this allows scripts to group operations into batches enabling better performance. Calling Operation methods like `isSuccessful()` and `getResult()` causes Bing Ads Scripts to immediately execute pending operations and can lead to reduced performance. Instead, create an array to hold the operations, then iterate through that array to retrieve the results. 

### Poor Performance
``` javascript
for (var i = 0; i < keywords.length; i++)
  var keywordOperation = BingAdsApp.adGroups().get().next()
    .newKeywordBuilder()
    .withText(keywords[i])
    .build();

  // Bad: retrieving the result in the same
  // loop that creates the operation
  // leads to poor performance.
  var newKeyword =
      keywordOperation.getResult();
  newKeyword.applyLabel("New keywords”);
}
```

### Good Performance
``` javascript
// Create an array to hold the operations
var operations = [];

for (var i = 0; i < keywords.length; i++) {
  var keywordOperation = BingAdsApp.adGroups().get().next()
    .newKeywordBuilder()
    .withText(keywords[i])
    .build();
  operations.push(keywordOperation);
}

// Process the operations separately. Allows
// Bing Ads scripts to group operations into
// batches.
for (var i = 0; i < operations.length; i++) {
  var newKeyword = operations[i].getResult();
  newKeyword.applyLabel("New keywords”);
}
```

See also:
- [AdGroupBuilder](../reference/AdGroupBuilder)
- [ExpandedTextAdBuilder](../reference/ExpandedTextAdBuilder)
- [KeywordBuilder](../reference/KeywordBuilder)
- [NegativeKeywordListBuilder](../reference/NegativeKeywordListBuilder)

## Next Steps

> [!div class="nextstepaction"]
> [Learn about preview mode](./preview-mode.md)