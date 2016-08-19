---
title: Tag Engine API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Tag Engine API! You can use our API to access Tag Engine API endpoints, which can get information on various tags in our database.

# Tags

## Get All Tags (by module)


```shell
curl "http://tags.bms.bz/tags/?module=music"
```

> The above command returns JSON structured like this:

```json
{
  "count" : 2,
  "tags"  : [
    {
      "_id" : "salmankhan",
      "name" : "Salman Khan",
      "modules" : [{
            "source(iedb)" : [ "Primay keys here can be multiple" ],
            "music" : [ "Primay keys here can be multiple" ]
      }],
      "status" : "A/U",
      "type" : "[Refer the document below (ID goes here)]",
      "creationSoruceId" : "[Refer the document below (ID goes here)]",
      "referenceCount" : 120,
      "relatedTags" : ["music", "dance"],
      "createdAt" : "2016-02-08T13:14:52.986Z",
      "createdBy" : "BO / BMS User Id",
      "lastModAt" : "2016-02-08T13:14:52.986Z",
      "lastModBy" : "BO / BMS User Id",
      "approvedAt" : "2016-02-08T13:14:52.986Z",
      "approvedBy" : "BO / BMS User Id"
    }
  ]
}
```

This endpoint retrieves all tags for a specified module.

### HTTP Request

`GET http://tags.bms.bz/tags/?module=music`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
module | true | Module for which tags are requested

## Get a Specific Tag

```shell
curl "http://tags.bms.bz/tags/:tag"
```

> The above command returns JSON structured like this:

```json
{
  "_id" : "salmankhan",
  "name" : "Salman Khan",
  "modules" : [{
        "source(iedb)" : [ "Primay keys here can be multiple" ],
        "music" : [ "Primay keys here can be multiple" ]
  }],
  "status" : "A/U",
  "type" : "[Refer the document below (ID goes here)]",
  "creationSoruceId" : "[Refer the document below (ID goes here)]",
  "referenceCount" : 120,
  "relatedTags" : ["music", "dance"],
  "createdAt" : "2016-02-08T13:14:52.986Z",
  "createdBy" : "BO / BMS User Id",
  "lastModAt" : "2016-02-08T13:14:52.986Z",
  "lastModBy" : "BO / BMS User Id",
  "approvedAt" : "2016-02-08T13:14:52.986Z",
  "approvedBy" : "BO / BMS User Id"
}
```

This endpoint retrieves a specific tag.


### HTTP Request

`GET http://tags.bms.bz/tags/:tag`

### URL Parameters

Parameter | Description
--------- | -----------
tag | The name of tag to retrive

