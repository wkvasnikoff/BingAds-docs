# Keywords

## Add a keyword to an existing ad group
```javascript
function addKeyword(adGroupName) {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();

    adGroup.newKeywordBuilder()
        .withText('Hello world')
        .withCpc(1.25)                          // Optional
        .withFinalUrl('http://www.contoso.com') // Optional
        .build();
  }
}
```

## Pause an existing keyword in an ad group
```javascript
function pauseKeywordInAdGroup(adGroupName, keywords) {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var keywordIterator = adGroup.keywords()
        .withCondition('Text="' + keywords + '"').get();
    while (keywordIterator.hasNext()) {
      var keyword = keywordIterator.next();
      keyword.pause();
    }
  }
}
```

## Get all keywords in an ad group
```javascript
function getKeywordsInAdGroup(adGroupName) {
  var keywordIterator = BingAdsApp.keywords()
      .withCondition('AdGroupName = "' + adGroupName + '"')
      .get();
  while (keywordIterator.hasNext()) {
    var keyword = keywordIterator.next();
    Logger.log(formatKeyword(keyword));
  }
}

function formatKeyword(keyword) {
  return 'Text : ' + keyword.getText() + '\n' +
      'Match type : ' + keyword.getMatchType() + '\n' +
      'CPC : ' + keyword.bidding().getCpc() + '\n' +
      'Final URL : ' + keyword.urls().getFinalUrl() + '\n' +
      'Approval Status : ' + keyword.getApprovalStatus() + '\n' +
      'Enabled : ' + keyword.isEnabled() + '\n';
}
```

## Get stats for all keywords in an ad group
```javascript

function getKeywordStats(adGroupName) {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var keywordIterator = adGroup.keywords().get();
    while (keywordIterator.hasNext()) {
      var keyword = keywordIterator.next();
      var stats = keyword.getStatsFor('LAST_MONTH');
      Logger.log(adGroup.getName() + ', ' + keyword.getText() + ', ' +
          stats.getClicks() + ', ' + stats.getImpressions());
    }
  }
}
```