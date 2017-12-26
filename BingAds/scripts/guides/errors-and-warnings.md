---
title: "Bing Ads Scripts Errors and Warnings"
description: "Describes how errors and warnings are handled in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Errors and Warnings

When you update an entity’s properties and the update fails, a warning message is written to the [Change Log](./change-and-text-logs#change-log). Because exceptions are not thrown in this case, you should test each set operation as shown in the example. The example attempts to set the campaign’s budget. Because the amount is not valid, the call fails and a warning message is written to the Change Log.

```javascript
function main() {
    var campaign = BingAdsApp.campaigns().get().next();
    campaign.getBudget().setAmount(-5);
    
    if (campaign.getBudget() != -5) {
        // The budget amount doesn't match what we 
        // attempted to set it to, so the change must 
        // have failed.
    }
}
```

Other errors such as runtime errors or entity retrieval failures cause script execution to stop. When this happens, the error message is written to the [Text Log](./change-and-text-logs#text-log). The following code attempts to call the `doSomething` function but because the function is not defined the script terminates execution. 

```javascript
function main() {
    doSomething(); // ReferenceError: 'doSomething' is undefined
    Logger.log('Will not reach this line');
}
```

You should carefully review all messages logged to the [Changes and Text logs](./changes-and-text-logs).