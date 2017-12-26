---
title: "Bing Ads Scripts Changes and Text Logs"
description: "Describes how logging works in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Change and Text Logs
Bing Ads Scripts provides two types of logs: change logs and text logs.

## Change Log
The Change log lists all changes that a script makes to Bing Ads entities. Details include Changed Item, Type of change, Current value, New value, and Status. To view the Change log, click *Changes* below the script editor.

## Text Log
To write text to the text log, call the `Logger.log` method. Writing text to the text log is useful for debugging scripts or to just capture script activity. For example, the following code prints all campaign names and progress messages to the text log.

```javascript
var campaigns = BingAdsApp.campaigns().get();
Logger.log('retrieved ' + campaigns.totalNumEntities() + ' campaigns');
while (campaigns.hasNext()) {
    var campaign = campaigns.next();
    Logger.log('Campaign: ' + campaign.getName());
}
Logger.log('script complete');
```

In addition to output from `Logger.log`, [errors and warnings](./errors-and-warnings) are automatically output to the text log. To view the text log, click *Logs* below the script editor.

To view the Change and Text logs for scripts that run on a schedule or were running when you logged out, click *View details* on the scripts home page.