# Stats
Provides statistics related to the different entity types.


Example usage:
```javascript
 var campaign = BingAdsApp.campaigns().get().next();
 var stats = campaign.getStatsFor("LAST_MONTH");
 var impressions = stats.getImpressions();
 var clicks = stats.getClicks();
 // etc.
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getAverageCpc](#getaveragecpc)|double|Returns the average cost per click.
[getAverageCpm](#getaveragecpm)|double|Returns the average cost per thousand impressions of the associated entity.<br />
[getAveragePosition](#getaverageposition)|double|Returns the average position.
[getClickConversionRate](#getclickconversionrate)|double|Returns the conversion rate for clicks of the associated entity within the 0..1 range.<br />
[getClicks](#getclicks)|long|Returns the number of clicks.
[getConvertedClicks](#getconvertedclicks)|long|Returns the number of clicks that converted of the associated entity.<br />
[getCost](#getcost)|double|Returns the cost (spend) in the currency of the current account.
[getCtr](#getctr)|double|Returns the click through rate within the 0..1 range.
[getImpressions](#getimpressions)|long|Returns the number of impressions.

## <a name="getaveragecpc"></a>getAverageCpc
Returns the average cost per click.

### Returns:
|Type|Description|
|-|-
double|Average cost per click.

## <a name="getaveragecpm"></a>getAverageCpm
Returns the average cost per thousand impressions of the associated entity.


### Returns:
|Type|Description|
|-|-
double|The average cost per thousand impressions.

## <a name="getaverageposition"></a>getAveragePosition
Returns the average position.

### Returns:
|Type|Description|
|-|-
double|Average position.

## <a name="getclickconversionrate"></a>getClickConversionRate
Returns the conversion rate for clicks of the associated entity within the 0..1 range.


### Returns:
|Type|Description|
|-|-
double|

## <a name="getclicks"></a>getClicks
Returns the number of clicks.

### Returns:
|Type|Description|
|-|-
long|Number of clicks.

## <a name="getconvertedclicks"></a>getConvertedClicks
Returns the number of clicks that converted of the associated entity.


### Returns:
|Type|Description|
|-|-
long|

## <a name="getcost"></a>getCost
Returns the cost (spend) in the currency of the current account.

### Returns:
|Type|Description|
|-|-
double|Cost in the default currency of the account.

## <a name="getctr"></a>getCtr
Returns the click through rate within the 0..1 range.

### Returns:
|Type|Description|
|-|-
double|Click through rate.

## <a name="getimpressions"></a>getImpressions
Returns the number of impressions.

### Returns:
|Type|Description|
|-|-
long|Number of impressions.

