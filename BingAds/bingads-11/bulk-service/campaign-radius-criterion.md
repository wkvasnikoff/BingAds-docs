---
title: "Campaign Radius Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign Radius Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Radius Criterion Record - Bulk
Defines a campaign radius criterion that can be uploaded and downloaded in a bulk file.

With radius criterions, you can choose to show ads to potential customers in, searching for, or viewing pages about a specified radius around a zip code, coordinates, landmark, or area.

Each radius criterion defines a radius, latitude, and longitude for the accompanying criterion bid adjustment. 

The maximum number of radius criterions that you can specify per campaign or ad group is 2,000.

> [!NOTE]
> You can only have one [Campaign Location Intent Criterion](campaign-location-intent-criterion.md) record per campaign to determine the location intent option that applies for all of the campaign's [Campaign Location Criterion](campaign-location-criterion.md) and [Campaign Radius Criterion](campaign-radius-criterion.md) records. When you create the campaign's first criterion, a [Campaign Location Intent Criterion](campaign-location-intent-criterion.md) record will also be added automatically with the default *Target* set to *PeopleInOrSearchingForOrViewingPages*. You can add or update a campaign's [Campaign Location Intent Criterion](campaign-location-intent-criterion.md), whether or not the campaign has any other criterions. You cannot delete a campaign's [Campaign Location Intent Criterion](campaign-location-intent-criterion.md), although it has no purpose without location or radius criterions. 

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Campaign Radius Criterion* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Bid Adjustment](#bidadjustment)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Latitude](#latitude)
- [Longitude](#longitude)
- [Modified Time](#modifiedtime)
- [Name](#name)
- [Parent Id](#parentid)
- [Radius](#radius)
- [Status](#status)
- [Unit](#unit)

You can download all fields of the *Campaign Radius Criterion* record by including the [DownloadEntity](downloadentity.md) value of *CampaignTargetCriterions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new campaign radius criterion if a valid campaign identifier (*Parent Id*) is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Bid Adjustment,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,5,,,,,,,,
Campaign Radius Criterion,Active,,-111,,,ClientIdGoesHere,,RadiusName,20,,10,Kilometers,,,,,10.5,40.5
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkCampaignRadiusCriterion* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCampaignRadiusCriterion
var bulkCampaignRadiusCriterion = new BulkCampaignRadiusCriterion
{
    // 'Campaign' column header in the Bulk file is read-only
    CampaignName = null,

    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // BiddableCampaignCriterion object of the Campaign Management service.

    CampaignCriterion = new BiddableCampaignCriterion
    {
        // 'Parent Id' column header in the Bulk file
        CampaignId = campaignIdKey,

        Criterion = new RadiusCriterion
        {
            // 'Latitude' column header in the Bulk file
            LatitudeDegrees = 10.5,

            // 'Longitude' column header in the Bulk file
            LongitudeDegrees = 40.5,

            // 'Name' column header in the Bulk file
            Name = "RadiusName",

            // 'Radius' column header in the Bulk file
            Radius = 10,

            // 'Unit' column header in the Bulk file
            RadiusUnit = DistanceUnit.Kilometers,
        },

        CriterionBid = new BidMultiplier
        {
            // 'Bid Adjustment' column header in the Bulk file
            Multiplier = 20,
        },

        // 'Id' column header in the Bulk file
        Id = null,

        // 'Status' column header in the Bulk file
        Status = CampaignCriterionStatus.Active,
    }
};

uploadEntities.Add(bulkCampaignRadiusCriterion);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkService.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

### <a name="bidadjustment"></a>Bid Adjustment
The percentage amount that you want to adjust the bid for the corresponding radius criterion. 

Supported values are negative ninety (-90) through positive nine hundred (900). 

**Add:** Optional. The bid adjustment will be set to the default of *0* if not included.  
**Update:** Required  
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign where this criterion is applied or removed.  

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Optional  

### <a name="id"></a>Id
The Bing Ads unique identifier of the criterion.

> [!NOTE] 
> Previously with Campaign Management API version 10 it was possible to associate one target identifier with multiple campaigns and ad groups using the AddTargetsToLibrary, SetTargetToCampaign, and SetTargetToAdGroup operations. After a campaign or ad group had been disassociated from the shared target, the criterion identifier would be set to *0* (zero) in the Bulk download or Bulk upload result file. 

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="latitude"></a>Latitude
The latitude, in degrees, of the location criterion.

The latitude must be greater than or equal to -85.0 and less than or equal to +85.0.

You specify the latitude and longitude as decimal values. For example, the latitude and longitude of One Redmond Way, Redmond, WA is 47.755367 and -122.091827, respectively. To get these values, you can enter the address of a geographical location into [Bing Maps](http://www.bing.com/maps/) and the coordinates will be displayed below the address.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

### <a name="longitude"></a>Longitude
The longitude, in degrees, of the location criterion.

The longitude must be greater than or equal to -180.0 and less than or equal to +180.0.

You specify the latitude and longitude as decimal values. For example, the latitude and longitude of One Redmond Way, Redmond, WA is 47.755367 and -122.091827, respectively. To get these values, you can enter the address of a geographical location into [Bing Maps](http://www.bing.com/maps/) and the coordinates will be displayed below the address.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="name"></a>Name
The name of the geographical location being targeted. 

The name can contain a maximum of 50 characters.

**Add:** Optional  
**Update:** Read-only  
**Delete:** Read-only 

### <a name="parentid"></a>Parent Id
The identifier of the campaign where this criterion is applied or removed.
	
This bulk field maps to the *Id* field of the [Campaign](campaign.md) record. 

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](campaign.md) record. This is recommended if you are adding new criterions to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="radius"></a>Radius
The radius that specifies the area surrounding the geographical location to target.

If the *Radius Unit* field is set to *Miles*, then positive integer values from 1 to 500 are accepted.

If the *Radius Unit* field is set to *Kilometers*, then positive integer values from 1 to 800 are accepted.

> [!NOTE]
> The data type is double and may be supported in a future release. Currently the service only accepts and returns integer values.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

### <a name="status"></a>Status
Represents the association status between the campaign and the criterion. If the criterion is applied to the campaign, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific location criterion bid, you must upload the *Status*, *Id*, and *Parent Id*.  

### <a name="unit"></a>Unit
The unit of measurement for the specified radius.

Supported values are *Miles* (default) and *Kilometers*.

**Add:** Optional. If not specified, the default value of *Miles* will be set.  
**Update:** Required  
**Delete:** Read-only  
