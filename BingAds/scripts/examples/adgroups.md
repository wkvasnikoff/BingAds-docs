# Ad Groups

[!INCLUDE[preview-note](../includes/preview-note.md)]

## Add an ad group
```javascript
function addAdGroup() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var adGroupName = 'YOUR AD GROUP NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var adGroupOperation = campaign.newAdGroupBuilder()
        .withName(adGroupName)
        .withCpc(1.2)
        .build();
    var adGroup = adGroupOperation.getResult();
  }
}
```

## Get all ad groups
```javascript
function getAllAdGroups() {
  var adGroupIterator = BingAdsApp.adGroups().get();
  Logger.log('Total adGroups found : ' + adGroupIterator.totalNumEntities());
  while (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    Logger.log('AdGroup Name: ' + adGroup.getName());
  }
}
```

## Get an ad group by name
```javascript
function getAdGroupByName() {
  var adGroupName = 'YOUR AD GROUP NAME';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    Logger.log('AdGroup Name: ' + adGroup.getName());
    Logger.log('Enabled: ' + adGroup.isEnabled());
  }
}
```

## Get an ad group's stats
```javascript
function getAdGroupStats() {
  var adGroupName = 'YOUR AD GROUP NAME';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var stats = adGroup.getStatsFor('LAST_MONTH');
    Logger.log(adGroup.getName() + ', ' + stats.getClicks() + ', ' +
        stats.getImpressions());
  }
}
```

## Pause an ad group
```javascript
function pauseAdGroup() {
  var adGroupName = 'YOUR AD GROUP NAME';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    adGroup.pause();
    Logger.log('AdGroup with name = ' + adGroup.getName() +
        ' has paused status : ' + adGroup.isPaused());
  }
}
```

## Enable an ad group
```javascript
function enableAdGroup() {
  var adGroupName = 'YOUR AD GROUP NAME';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    adGroup.enable();
  }
}
```
