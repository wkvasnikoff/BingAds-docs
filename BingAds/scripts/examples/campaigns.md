# Campaigns

[!INCLUDE[preview-note](../includes/preview-note.md)]

## Get all campaigns
```javascript
function getAllCampaigns() {
  var campaignIterator = BingAdsApp.campaigns().get();
  Logger.log('Total campaigns found : ' +
      campaignIterator.totalNumEntities());
  while (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log(campaign.getName());
  }
}
```

## Get a campaign by name
```javascript
function getCampaignsByName() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log('Campaign Name: ' + campaign.getName());
    Logger.log('Enabled: ' + campaign.isEnabled());
    Logger.log('Bidding strategy: ' + campaign.getBiddingStrategyType());
  }
}
```

## Get a campaign's stats
```javascript
function getCampaignStats() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var stats = campaign.getStatsFor('LAST_MONTH');
    Logger.log(campaign.getName() + ', ' + stats.getClicks() + 'clicks, ' +
        stats.getImpressions() + ' impressions');
  }
}
```

## Pause a campaign
```javascript
function pauseCampaign() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    campaign.pause();
  }
}
```

## Get a campaign's device bid modifiers
```javascript
function getCampaignBidModifiers() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log('Campaign name: ' + campaign.getName());

    var platformIterator = campaign.targeting().platforms().get();
    while (platformIterator.hasNext()) {
      var platform = platformIterator.next();
      Logger.log(platform.getName() + ' bid modifier: ' +
          platform.getBidModifier());
    }
  }
```
