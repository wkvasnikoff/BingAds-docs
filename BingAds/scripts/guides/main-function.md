---
title: "Bing Ads Scripts Script Structure"
description: "Describes how scripts should be structured in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Main Function

Unlike JavaScript that executes in a browser, Bing Ads Scripts must define a `main()` function that contains the program logic you want to execute. You may also define custom functions but the main function is the scripts entry point where execution begins.  For example, the following script defines a main function that calls a custom function named getAllCampaigns.

```javascript
function main() {
    getAllCampaigns();
}

function getAllCampaigns() {
  var campaigns = BingAdsApp.campaigns().get();
    while(campaigns.hasNext()){
        var campaign = campaigns.next();
        Logger.log(`Campaign: ${campaign.getName()}`);
    }
}
```

