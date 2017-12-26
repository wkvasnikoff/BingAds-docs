# Get Started With Bing Ads Scripts

[!INCLUDE[preview-note](./includes/preview-note.md)]

Follow these instructions to create your first Bing Ads script.

1. Sign in to [Bing Ads](https://secure.bingads.microsoft.com/) or [Bing Ads Sandbox](https://sandbox.bingads.microsoft.com/).
2. Expand **Bulk Operations** (see the left navigation panel).
3. Click **Scripts**.
4. Click **Create script**.
5. Copy and paste the following code into the code editor. This script will find 10 keywords with most impressions yesterday, but won't make any changes to your campaigns.

    ```javascript
    function main() {
        var keywords = BingAdsApp.keywords()
            .orderBy("Impressions DESC")
            .forDateRange("YESTERDAY")
            .withLimit(10)
            .get();
    
        Logger.log("10 keywords with most impressions yesterday");
        while (keywords.hasNext()) {
            var keyword = keywords.next();
            Logger.log(keyword.getText() + ": " +
                keyword.getStatsFor("YESTERDAY").getImpressions());
        }
    }
    ```

6. To execute the script in [preview mode](./concepts/preview-mode), click **Preview**.

### Next Steps

> [!div class="nextstepaction"]
> [Learn about selectors](./concepts/selectors.md)