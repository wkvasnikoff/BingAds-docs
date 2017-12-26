---
title: "Bing Ads Scripts Preview Mode"
description: "Describes how preview mode works in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Preview Mode

Preview mode lets you test your script without it making changes to the actual campaign data. Instead, you’re shown the results as if the script were executed. This can reduce the amount of time spent setting up test cases. When you're satisfied with the script's output, you can run the script or schedule it to run later.

Preview mode is specific to Bing Ads components. Calls to other services will execute as normal. For example, if a script sends an email it is sent whether or not the script is executed in preview mode. Likewise, spreadsheet updates are made whether the script is executed in preview mode or not. 

To determine if a script is executing in preview mode, see [ExecutionInfo](../reference/ExecutionInfo).

Because objects are not created, deleted or modified during preview mode not all code will execute the same during live execution. The following code will not behave as expected in preview mode.

```javascript
// Assume the adgroup has no keywords.
var adGroup = findAnEmptyAdGroup();

// Create a keyword.
adGroup.createKeyword("test");

// Retrieve all keywords in the ad group.
var keywords = adGroup.keywords().get();

// This will log "false" in preview mode because the keyword was not actually created.
// This will log "true" during real execution.
Logger.log("Does the ad group have keywords? " + keywords.hasNext());
```

### Next Steps

> [!div class="nextstepaction"]
> [Learn how authorization works](./authorization.md)