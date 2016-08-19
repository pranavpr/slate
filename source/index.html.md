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

## Create a new Tag


```shell
curl -H "Content-Type: application/json" 
     -X POST 
     -d '{"tag" : "Leonardo Di Caprio", "module" : "music", "moduleKey" : "PK12345"}' 
     http://tags.bms.bz/tags/
```

> The above command returns JSON structured like this:

```json
{
  "tag" : "Leonardo Di Caprio",
  "module" : ["Object"]
}
```

This endpoint creates a new tag.

### HTTP Request

`POST http://tags.bms.bz/tags/`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
tag | true | Name of tag to be created
module | true | Module to which tag belongs to
moduleKey | true | Primary key of Module

## Get a Specific Tag

```shell
curl "http://tags.bms.bz/tags/salmankhan"
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


## Update a Tag


```shell
curl -H "Content-Type: application/json" 
     -X PUT 
     -d '{"tag" : "Leonardo Di Caprio", "module" : "music", "moduleKey" : "PK99999"}' 
     http://tags.bms.bz/tags/
```

> The above command returns JSON structured like this:

```json
{
  "tag" : "Leonardo Di Caprio",
  "module" : ["Object"]
}
```

This endpoint updates an existing tag.

### HTTP Request

`PUT http://tags.bms.bz/tags/`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
tag | true | Name of tag to be updated
module | true | Module to which tag belongs to
moduleKey | true | Primary key of Module

# DB documents

Sample documents present in database

> Tag Document 

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

> Soruce Document 

```json
{
  "_id" : "music",
  "name" : "Music"
}
```

> Type Document 

```json
{
  "_id" : "actor",
  "name" : "Actor"
}
```
