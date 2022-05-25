create time: 2022-04-22


# User API v0.5.1

## POST /v1.0/api/user/login

POST /v1.0/api/user/login

> Body request parameter


```json
{
  "username": "username",
  "password": "password",
  "service": "http://url.com"
}
```

### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| body | body | object | no | none |
| » username | body | string | yes | Username |
| » password | body | string | yes | Password |
| » service | body | string | yes | The address of the logon request |


> return example


### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


### return structure

## GET /v1.0/api/user/logout

GET /v1.0/api/user/logout

### request parameter
| name | location | type | description |
| --- | --- | --- | --- |
| email | query | string | Email |
| rzpj | header | string | Certificate |


> return example


### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


### return structure

## GET /v1.0/api/user

GET /v1.0/api/user

### request parameter
| name | location | type | description |
| --- | --- | --- | --- |
| rzpj | header | string | Certificate |


> return example


> success


```json
{
  "id": "f703a998-d0fc-45d7-8d49-f468ffd913de",
  "username": "apidocs",
  "email": "876012439@qq.com",
  "firstName": "Time",
  "lastName": "Deep",
  "status": "NORMAL",
  "createTime": 1650274106201,
  "updateTime": 1650274106201
}
```

### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » id | string | none | UID |
| » username | string | none | Username |
| » email | string | none | Email |
| » firstName | string | none | First name |
| » lastName | string | none | Last name |
| » status | string | none | Status |
| » createTime | integer | none | Created |
| » updateTime | integer | none | Update |


# Data Hub API v0.5.1

## DataAtom

### GET /v1.0/api/data-central/atom/{uid}

GET /v1.0/api/data-central/atom/{uid}

Query DataAtom by uid

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| uid | path | string | yes | DataAtom UID |
| rzpj | header | string | no | Certificate |


> return example


> http success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "id": 1,
    "uid": "7fd6e867-54a3-46f3-9869-290097de74ce",
    "name": "http_reconstruct_coastline",
    "dataType": "JSON",
    "atomType": "HTTP",
    "userId": "ADMIN",
    "privilege": "PUBLIC",
    "status": "HEALTHY",
    "isOfficial": 1,
    "browseGraph": "http://ip:port/static/reconstruct-coastlines.png",
    "keyword": "paleogeography",
    "description": "description",
    "taskId": null,
    "boundaryWKT": null,
    "coordinateReference": null,
    "projection": null,
    "space": {
      "type": null,
      "resolution": "500m",
      "elevation": null,
      "extent": {
        "minX": -180,
        "maxX": 180,
        "minY": -90,
        "maxY": 90
      },
      "geoIdentifier": null
    },
    "temporal": {
      "geologicTime": null,
      "geologicAge": null,
      "base": 760,
      "top": 0,
      "gtsVersion": null
    },
    "fields": [
      {
        "type": "FLOAT",
        "fieldName": "time",
        "description": "time"
      },
      {
        "type": "VARCHAR",
        "fieldName": "model",
        "description": "models of reconstruct: ['SCOTESE&WRIGHT2018', 'SETON2012', 'PEHRSSON2015', 'DOMEIER2014', 'MATTHEWS2016_pmag_ref', 'MATTHEWS2016_mantle_ref', 'MATTHEWS2016', 'VH_VDM', 'GOLONKA', 'RODINIA2013', 'PALEOMAP', 'MULLER2016']"
      }
    ],
    "intellectualProp": null,
    "license": null,
    "discipline": "/",
    "authorName": null,
    "authorMail": null,
    "doi": null,
    "associatedResource": null,
    "associatedResourceUrl": null,
    "createTime": 1648795083357,
    "updateTime": 1648795457805,
    "httpDpMeta": {
      "dpAddress": "14F3D2D7A4021000",
      "security": {
        "useTls": false
      },
      "transfer": {
        "endpoint": [
          "ip:port/reconstruct/coastlines"
        ],
        "protocol": "http"
      },
      "httpRoute": {
        "contentType": "application/json",
        "method": "GET"
      }
    }
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | http success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | DataAtom Information |
| »» id | integer | none | DataAtom ID |
| »» uid | string | none | DataAtom UID |
| »» name | string | none | Unit name |
| »» dataType | string | none | Data type,Value = FILE, TABLE, JSON, PICTURE.. |
| »» atomType | string | none | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| »» userId | string | none | none |
| »» privilege | string | none | AccessPermission,Value= public, private |
| »» status | string | none | Access Status,Value =  SETTING,HEALTHY, UNHEALTHY |
| »» isOfficial | integer | none | Is it official |
| »» browseGraph | string | none | Browse Graph |
| »» keyword | string | none | Keyword |
| »» description | string | none | Description |
| »» taskId | null | none | Taskid |
| »» boundaryWKT | null | none | The range of the query space, which is returned in WKT format. |
| »» coordinateReference | null | none | coordinate Reference |
| »» projection | null | none | Projection coordinate system |
| »» space | object | none | Spatial Information |
| »»» type | null | none | Type |
| »»» resolution | string | none | Spatial resolution |
| »»» elevation | null | none | Elevation |
| »»» extent | object | none | extent |
| »»»» minX | integer | none | Minimum x |
| »»»» maxX | integer | none | Maximum x |
| »»»» minY | integer | none | Minimum y |
| »»»» maxY | integer | none | Maximum y |
| »»» geoIdentifier | null | none | GeoIdentifier |
| »» temporal | object | none | Time |
| »»» geologicTime | null | none | Geologic time，e.g, Quaternary |
| »»» geologicAge | null | none | Geological age，e.g,1，100 to 200.2 |
| »»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»» top | integer | none | The latest possible time t，e.g,10.2 |
| »»» gtsVersion | null | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» fields | [object] | none | Field Information |
| »»» type | string | none | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »»» fieldName | string | none | Fieldname |
| »»» description | string | none | Description |
| »» intellectualProp | null | none | IntellectualProp |
| »» license | null | none | license |
| »» discipline | string | none | Discipline |
| »» authorName | null | none | Author name |
| »» authorMail | null | none | Author email |
| »» doi | null | none | The unique identifier of the data object |
| »» associatedResource | null | none | Associated resources |
| »» associatedResourceUrl | null | none | Link |
| »» createTime | integer | none | Created |
| »» updateTime | integer | none | Update Time |
| »» httpDpMeta | object | none | Data center information |
| »»» dpAddress | string | none | DpAddress |
| »»» security | object | none | Encrypted information |
| »»»» useTls | boolean | none | TLS encryption |
| »»» transfer | object | none | Transfer information |
| »»»» endpoint | [string] | none | Endpoint |
| »»»» protocol | string | none | Data source protocol |
| »»» httpRoute | object | none | HTTP Route |
| »»»» contentType | string | none | Content Type |
| »»»» method | string | none | Request Mode |

### POST /v1.0/api/data-central/atom/list/user

POST /v1.0/api/data-central/atom/list/user

Enter a field to obtain the list of DataAtom belonging to the user

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| page | query | string | no | In the previous page, if you want to display the first page, use 0 |
| pageSize | query | string | no | Number of Entries displayed per page |
| spatialWkt | query | string | no | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top | query | string | no | Maximum time range for querying data |
| base | query | string | no | Minimum time range for querying data |
| datasetId | query | string | no | Dataset ID |
| keyword | query | string | no | Keyword |
| startTimestamp | query | string | no | Start time |
| endTimestamp | query | string | no | End time |
| status | query | string | no | Access Status,Value = [SETTING, HEALTHY, UNHEALTHY, LAYERED] |
| atomType | query | string | no | Atom Type, Value = [BASE, JDBC, HTTP, LAYER_SERVICE, POSTGRESQL, MYSQL] |
| dataType | query | string | no | DataType，Value = FILE, TABLE, JSON, PICTURE, VECTOR, RASTER |
| rzpj | header | string | yes | Certificate |


> return example


> success


```json
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 1,
        "list": [
            {
                "uid": "cac31bc3-71ea-4fcd-a825-8ef291a37d9e",
                "name": "OneSediment Detrital Zicron Data",
                "dataType": "TABLE",
                "atomType": "JDBC",
                "privilege": "PRIVATE",
                "status": "HEALTHY",
                "isOfficial": 0,
                "browseGraph": "dde.jpg",
                "keyword": "Detrital Zicron, Sediment",
                "description": "Detrital Zicron Data From OneSediment",
                "coordinateReference": "WGS84",
                "projection": "Equirectangular",
                "authorName": "DDE",
                "authorMail": "DDE@dde.org",
                "doi": "",
                "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
                "associatedResourceURL": "http://hdl.handle.net/10919/27785",
                "space": {
                    "type": "TextTable",
                    "resolution": "",
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": 90,
                        "maxY": -90
                    }
                },
                "temporal": {
                    "geologicTime": "",
                    "geologicAge": "",
                    "gtsVersion": "International 2016 chart",
                    "base": 750,
                    "top": 0
                },
                "fields": [
                    {
                        "fieldName": "ref_no",
                        "type": "VARCHAR",
                        "description": "reference number of zicron detrital"
                    },
                    {
                        "fieldName": "lead_author",
                        "type": "VARCHAR",
                        "description": "lead author of reference paper"
                    }
                ],
                "httpDpMeta": {
                    "transfer": {
                        "protocol": "http",
                        "endpoint": [
                            "ip:port/reconstruct/coastlines"
                        ]
                    },
                    "security": {
                        "useTls": false
                    },
                    "httpRoute": {
                        "contentType": "application/json",
                        "method": "GET"
                    }
                }
            }
        ]
    }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | DataAtom Information |
| »» id | integer | none | DataAtom ID |
| »» uid | string | none | DataAtom UID |
| »» name | string | none | Unit name |
| »» dataType | string | none | Data type,Value = FILE, TABLE, JSON, PICTURE.. |
| »» atomType | string | none | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| »» userId | string | none | Userid |
| »» privilege | string | none | AccessPermission,Value= public, private |
| »» status | string | none | Access Status,Value =  SETTING,HEALTHY, UNHEALTHY |
| »» isOfficial | integer | none | Is it official |
| »» browseGraph | string | none | Browse Graph |
| »» keyword | string | none | Keyword |
| »» description | string | none | Description |
| »» taskId | null | none | Taskid |
| »» boundaryWKT | null | none | The range of the query space, which is returned in WKT format. |
| »» coordinateReference | null | none | coordinate Reference |
| »» projection | null | none | Projection coordinate system |
| »» space | object | none | Spatial Information |
| »»» type | null | none | Type |
| »»» resolution | string | none | Spatial resolution |
| »»» elevation | null | none | Elevation |
| »»» extent | object | none | extent |
| »»»» minX | integer | none | Minimum x |
| »»»» maxX | integer | none | Maximum x |
| »»»» minY | integer | none | Minimum y |
| »»»» maxY | integer | none | Maximum y |
| »»» geoIdentifier | null | none | GeoIdentifier |
| »» temporal | object | none | Time |
| »»» geologicTime | null | none | Geologic time，e.g, Quaternary |
| »»» geologicAge | null | none | Geological age，e.g,1，100 to 200.2 |
| »»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»» top | integer | none | The latest possible time t，e.g,10.2 |
| »»» gtsVersion | null | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» fields | [object] | none | Field Information |
| »»» type | string | none | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »»» fieldName | string | none | Fieldname |
| »»» description | string | none | Description |
| »» intellectualProp | null | none | IntellectualProp |
| »» license | null | none | license |
| »» discipline | string | none | Discipline |
| »» authorName | null | none | Author name |
| »» authorMail | null | none | Author email |
| »» doi | null | none | The unique identifier of the data object |
| »» associatedResource | null | none | Associated resources |
| »» associatedResourceUrl | null | none | Link |
| »» createTime | integer | none | Created |
| »» updateTime | integer | none | Update Time |
| »» httpDpMeta | object | none | Data center information |
| »»» dpAddress | string | none | DpAddress |
| »»» security | object | none | Encrypted information |
| »»»» useTls | boolean | none | TLS encryption |
| »»» transfer | object | none | Transfer information |
| »»»» endpoint | [string] | none | Endpoint |
| »»»» protocol | string | none | Data source protocol |
| »»» httpRoute | object | none | HTTP Route |
| »»»» contentType | string | none | Content Type |
| »»»» method | string | none | Request Mode |


### POST /v1.0/api/data-central/atom/list/public

POST /v1.0/api/data-central/atom/list/public

Obtains a list of public DataAtom

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| page | query | string | no | In the previous page, if you want to display the first page, use 0 |
| pageSize | query | string | no | Number of Entries displayed per page |
| spatialWkt | query | string | no | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top | query | string | no | Maximum time range for querying data |
| base | query | string | no | Minimum time range for querying data |
| datasetId | query | string | no | Dataset ID |
| keyword | query | string | no | Keyword |
| startTimestamp | query | string | no | Start time |
| endTimestamp | query | string | no | End time |
| status | query | string | no | [SETTING, HEALTHY, UNHEALTHY, LAYERED] |
| path | query | string | no | Directory path |
| atomType | query | string | no | Atom Type,Value= [BASE, JDBC, HTTP, LAYER_SERVICE, POSTGRESQL, MYSQL] |
| dataType | query | string | no | DataType，Value = FILE, TABLE, JSON, PICTURE, VECTOR, RASTER |
| rzpj | header | string | no | Certificate |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "content": {
    "total": 2,
    "dataAtoms": [
      {
        "id": 1,
        "uid": "77cc1c2f-2da2-464c-8aed-83c955dcf18f",
        "name": "layer",
        "dataType": "TABLE",
        "atomType": "LAYER_SERVICE",
        "userId": "ADMIN",
        "privilege": "PUBLIC",
        "status": "HEALTHY",
        "isOfficial": 1,
        "browseGraph": "dde.jpg",
        "keyword": "dde",
        "taskId": 0,
        "coordinateReference": null,
        "projection": null,
        "space": {
          "type": null,
          "resolution": "500m",
          "elevation": null,
          "extent": {
            "minX": 0,
            "maxX": 90,
            "minY": 0,
            "maxY": 50
          },
          "geoIdentifier": null
        },
        "temporal": {
          "geologicTime": "Neoproterozoic and Phanerozoic",
          "geologicAge": "None",
          "base": 150,
          "top": 10,
          "gtsVersion": "International 2016 chart"
        },
        "fields": [
          {
            "type": "VARCHAR",
            "fieldName": "name",
            "description": "null"
          }
        ],
        "createTime": 1646922764937,
        "updateTime": 1646922764937
      },
      {
        "id": 2,
        "uid": "65bf0a0d-a04a-466a-86a7-d70e391e82c3",
        "name": "jdbc",
        "dataType": "TABLE",
        "atomType": "JDBC",
        "userId": "ADMIN",
        "privilege": "PUBLIC",
        "status": "HEALTHY",
        "isOfficial": 1,
        "browseGraph": "dde.jpg",
        "keyword": "dde",
        "taskId": 0,
        "coordinateReference": null,
        "projection": null,
        "space": {
          "type": null,
          "resolution": "500m",
          "elevation": null,
          "extent": {
            "minX": 0,
            "maxX": 90,
            "minY": 0,
            "maxY": 50
          },
          "geoIdentifier": null
        },
        "temporal": {
          "geologicTime": "Neoproterozoic and Phanerozoic",
          "geologicAge": "None",
          "base": 150,
          "top": 10,
          "gtsVersion": "International 2016 chart"
        },
        "fields": [
          {
            "type": "VARCHAR",
            "fieldName": "name",
            "description": "null"
          }
        ],
        "createTime": 1646921724886,
        "updateTime": 1646922066159
      }
    ]
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » content | object | none | Data Content |
| »» total | integer | none | Data Records |
| »» dataAtoms | [object] | none | Metadata information |
| »»» id | integer | none | DataAtom ID |
| »»» uid | string | none | DataAtom UID |
| »»» name | string | none | Unit name |
| »»» dataType | string | none | Data type,Value = FILE, TABLE, JSON, PICTURE.. |
| »»» atomType | string | none | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| »»» userId | string | none | Userid |
| »»» privilege | string | none | AccessPermission,Value= public, private |
| »»» status | string | none | Access Status,Value =  SETTING,HEALTHY, UNHEALTHY |
| »»» isOfficial | integer | none | is it Official |
| »»» browseGraph | string | none | Browse Graph |
| »»» keyword | string | none | Keyword |
| »»» taskId | integer | none | TaskId |
| »»» coordinateReference | null | none | coordinate Reference |
| »»» projection | null | none | Projection coordinate system |
| »»» space | object | none | Spatial Information |
| »»»» type | null | none | Type |
| »»»» resolution | string | none | Spatial resolution |
| »»»» elevation | null | none | Elevation |
| »»»» extent | object | none | extent |
| »»»»» minX | integer | none | Minimum x |
| »»»»» maxX | integer | none | Maximum x |
| »»»»» minY | integer | none | Minimum y |
| »»»»» maxY | integer | none | Maximum y |
| »»»» geoIdentifier | null | none | GeoIdentifier |
| »»» temporal | object | none | Time |
| »»»» geologicTime | string | none | Geologic time，e.g, Quaternary |
| »»»» geologicAge | string | none | Geological age，e.g,1，100 to 200.2 |
| »»»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»»» top | integer | none | The latest possible time t，e.g,10.2 |
| »»»» gtsVersion | string | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »»» fields | [object] | none | Field Information |
| »»»» type | string | none | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »»»» fieldName | string | none | Fieldname |
| »»»» description | string | none | Description |
| »»» createTime | integer | none | Created |
| »»» updateTime | integer | none | Update time |


### POST /v1.0/api/data-central/atom/raster/layer

POST /v1.0/api/data-central/atom/raster/layer

Enter Fields to publish raster data with one click

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| path | query | string | yes | Data directory |
| atomName | query | string | no | Atom name |
| rzpj | header | string | yes | Certificate |
| keyword | query | string | no | Keyword |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "0ffda1a7-e984-4145-9b1b-981162982162"
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | DataAtom Information |
| »» uid | string | none | DataAtom UID |



### POST /v1.0/api/data-central/atom/http

POST /v1.0/api/data-central/atom/http

Enter a field to add an http DataAtom

> Body request parameter


```json
{
    "name": "Deep Marine Drilling Data",
    "dataType": "JSON",
    "atomType": "HTTP",
    "privilege": "PUBLIC",
    "status": "HEALTHY",
    "description": "Spatital Distribution of International Ocean Drilling Data",
    "browseGraph": "http://ip:port/static/reconstruct-coastlines.png",
    "keyword": "IODP, Drilling, Spatial Distribution",
    "space": {
        "extent": {
            "minX": -180.0,
            "maxX": 180.0,
            "minY": -90.0,
            "maxY": 90.0
        }
    },
    "temporal": {
        "base": 0.0,
        "top": 0.0
    },
    "fields": [
        {
            "fieldName": "time",
            "type": "FLOAT",
            "description": "time"
        },
        {
            "fieldName": "model",
            "type": "VARCHAR",
            "description": "models of reconstruct: ['SCOTESE&WRIGHT2018', 'SETON2012', 'PEHRSSON2015', 'DOMEIER2014', 'MATTHEWS2016_pmag_ref', 'MATTHEWS2016_mantle_ref', 'MATTHEWS2016', 'VH_VDM', 'GOLONKA', 'RODINIA2013', 'PALEOMAP', 'MULLER2016']"
        }
    ],
    "httpDpMeta": {
        "transfer": {
            "protocol": "http",
            "endpoint": [
                "ip/static/holes.json"
            ]
        },
        "security": {
            "useTls": false
        },
        "httpRoute": {
            "contentType": "application/json",
            "method": "GET"
        }
    }
}
```

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| rzpj | header | string | yes | Certificate |
| body | body | object | no | none |
| » name | body | string | yes | Unit name |
| » dataType | body | string | no | Data type,Value = FILE, TABLE, JSON, PICTURE.. |
| » atomType | body | string | yes | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| » userId | body | string | yes | UserId |
| » privilege | body | string | yes | AccessPermission,Value= public, private |
| » status | body | string | yes | Access Status,Value =  SETTING,HEALTHY, UNHEALTHY |
| » browseGraph | body | string | yes | Browse Graph |
| » keyword | body | string | yes | Keyword |
| » description | body | string | yes | Description |
| » taskId | body | null | yes | TaskId |
| » boundaryWKT | body | null | yes | The range of the query space, which is returned in WKT format |
| » coordinateReference | body | null | yes | Coordinate Reference |
| » projection | body | null | yes | Projection coordinate system |
| » space | body | object | yes | Spatial Information |
| »» type | body | null | yes | Type |
| »» resolution | body | string | yes | Spatial resolution |
| »» elevation | body | null | yes | Elevation |
| »» extent | body | object | yes | Extent |
| »»» minX | body | integer | yes | Minimum x |
| »»» maxX | body | integer | yes | Maximum x |
| »»» minY | body | integer | yes | Minimum y |
| »»» maxY | body | integer | yes | Maximum y |
| »» geoIdentifier | body | null | yes | GeoIdentifier |
| » temporal | body | object | yes | Time |
| »» geologicTime | body | null | yes | Geologic time，e.g, Quaternary |
| »» geologicAge | body | null | yes | Geological age，e.g,1，100 to 200.2 |
| »» base | body | integer | yes | The earliest possible time point，e.g,150.3 |
| »» top | body | integer | yes | The latest possible time point，e.g,10.2 |
| »» gtsVersion | body | null | yes | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| » fields | body | [object] | yes | Field Information |
| »» type | body | string | yes | Field type，Value = INT, FLOAT, DOUBLE, BOOLEAN, COLUMNNAME, GEOMETRY, VARCHAR |
| »» fieldName | body | string | yes | Fieldname |
| »» description | body | string | yes | Description |
| » intellectualProp | body | null | yes | IntellectualProp |
| » license | body | null | yes | license |
| » discipline | body | string | yes | Discipline |
| » authorName | body | null | yes | Author name |
| » authorMail | body | null | yes | Author email |
| » doi | body | null | yes | The unique identifier of the data object |
| » associatedResource | body | null | yes | Associated resources |
| » associatedResourceUrl | body | null | yes | Link |
| » createTime | body | integer | yes | Created |
| » updateTime | body | integer | yes | Update Time |
| » httpDpMeta | body | object | yes | Data center information |
| »» dpAddress | body | string | yes |  dpAddress |
| »» security | body | object | yes | Encrypted information |
| »»» useTls | body | boolean | yes | TLS encryption |
| »» transfer | body | object | yes | Transfer information |
| »»» endpoint | body | [string] | yes | Endpoint |
| »»» protocol | body | string | yes | Data source protocol |
| »» httpRoute | body | object | yes | HTTP Route |
| »»» contentType | body | string | yes | Content Type |
| »»» method | body | string | yes | Request Mode |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "c5e58d08-a5cf-4590-b26c-8cc0e1431d4a"
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | DataAtom Information |
| »» uid | string | none | DataAtom UID |


### POST /v1.0/api/data-central/atom/layer

POST /v1.0/api/data-central/atom/layer

Enter a field to add layerService DataAtom

> Body request parameter


```json
{
    "name": "OneSediment Detrital Zicron Data",
    "dataType": "TABLE",
    "atomType": "JDBC",
    "privilege": "PRIVATE",
    "status": "HEALTHY",
    "browseGraph": "dde.jpg",
    "keyword": "Detrital Zicron, Sediment",
    "description": "Detrital Zicron Data From OneSediment",
    "coordinateReference": "WGS84",
    "projection": "Equirectangular",
    "authorName": "DDE",
    "authorMail": "DDE@dde.com",
    "doi": "",
    "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
    "associatedResourceURL": "http://hdl.handle.net/10919/27785",
    "space": {
        "type": "TextTable",
        "resolution": "",
        "extent": {
            "minX": -180,
            "maxX": 180,
            "minY": 90,
            "maxY": -90
        }
    },
    "temporal": {
        "geologicTime": "",
        "geologicAge": "",
        "gtsVersion": "International",
        "base": 750,
        "top": 0
    },
    "fields": [
        {
            "fieldName": "ref_no",
            "type": "VARCHAR",
            "description": "reference number of zicron detrital"
        },
        {
            "fieldName": "lead_author",
            "type": "VARCHAR",
            "description": "lead author of reference paper"
        }
    ],
    "layerServiceInfo": {
        "type": "VECTOR",
        "method": "GEOJSON",
        "sourceLayer": "layer",
        "imageURL": "dde.jpg",
        "coordinateReference": "EPSG:4326",
        "url": "/geoserver/gwc/service/tms/1.0.0/ADMIN:fx_vector_hangzhou7@EPSG:4326@png/{z}/{x}/{reverseY}.png",
        "vectorLayerItem": {
            "geoJsonType": "POLYGON"
        }
    }
}
```

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| rzpj | header | string | yes | Certificate |
| body | body | object | no | none |
| » name | body | string | yes | Unit name |
| » dataType | body | string | yes | Data type,Value = FILE, TABLE, JSON, PICTURE. |
| » atomType | body | string | yes | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| » userId | body | string | yes | UserID |
| » privilege | body | string | yes | AccessPermission,Value= public, private |
| » status | body | string | yes | Access Status,Value =  SETTING,HEALTHY, UNHEALTHY |
| » isOfficial | body | integer | yes | Is it official |
| » browseGraph | body | null | yes | Browse Graph |
| » keyword | body | string | yes | Keyword |
| » description | body | null | yes | Description |
| » taskId | body | null | yes | TaskID |
| » boundaryWKT | body | null | yes | The range of the query space, which is returned in WKT format. |
| » coordinateReference | body | null | yes | coordinate Reference |
| » projection | body | null | yes | Projection coordinate system |
| » space | body | object | yes | Spatial Information |
| »» type | body | null | yes | Type |
| »» resolution | body | null | yes | Spatial resolution |
| »» elevation | body | null | yes | Elevation |
| »» extent | body | object | yes | extent |
| »»» minX | body | integer | yes | Minimum x |
| »»» maxX | body | integer | yes | Maximum x |
| »»» minY | body | integer | yes | Minimum y |
| »»» maxY | body | integer | yes | Maximum y |
| »» geoIdentifier | body | null | yes | GeoIdentifier |
| » temporal | body | object | yes | Time |
| »» geologicTime | body | null | yes | Geologic time，e.g, Quaternary |
| »» geologicAge | body | null | yes | Geological age，e.g,1，100 to 200.2 |
| »» base | body | integer | yes | The earliest possible time point，e.g,150.3 |
| »» top | body | integer | yes | The latest possible time point，e.g,10.2 |
| »» gtsVersion | body | string | yes | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| » fields | body | [string] | yes | Field Information |
| » intellectualProp | body | null | yes | IntellectualProp |
| » license | body | null | yes | license |
| » discipline | body | string | yes | Discipline |
| » authorName | body | null | yes | Author name |
| » authorMail | body | null | yes | Author email |
| » doi | body | null | yes | The unique identifier of the data object |
| » associatedResource | body | null | yes | Associated resources |
| » associatedResourceUrl | body | null | yes | Link |
| » createTime | body | integer | yes | Created |
| » updateTime | body | integer | yes | Update Time |
| » layerServiceInfo | body | object | yes | Layer Service information |
| »» type | body | string | yes | Layer type，Value  = VECTOR, TMS, TDTILES, NC, ELASTICSEARCH |
| »» method | body | string | yes | Layer Service，Value = COG, WMS, WMTS, ARCGIS, TMS, TDT, AMAP, GEOJSON, TDTILES, NC, PBF |
| »» renderOptions | body | null | yes | Rendering |
| »» sourceLayer | body | string | yes | The real layer name，Default value: name |
| »» imageURL | body | string | yes | BrowseGraph URL |
| »» url | body | string | yes | Layer access unified locator |
| »» tmsLegend | body | null | yes | For tms, you can select this field to record the legend type, color, and name |
| »» coordinateArr | body | null | yes | none |
| »» geoJsonType | body | null | yes | GeoJson Type, e.g, POINT,MULTIPOINT,LINESTRING,MULTILINESTRING,POLYGON,MULTIPOLYGON,GEOMETRYCOLLECTION |
| »» fields | body | null | yes | Fields |
| »» valueRange | body | null | yes | ValueRange |
| »» offset | body | null | yes | Offset |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "587c669d-5605-4ecb-af82-0ad2e6dcc869"
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | DataAtom Information |
| »» uid | string | none | DataAtom UID |


### POST /v1.0/api/data-central/atom/jdbc

POST /v1.0/api/data-central/atom/jdbc

Enter a field to add a JDBC DataAtom

> Body request parameter


```json
{
  "name": "OneSediment Detrital Zicron Data",
  "dataType": "TABLE",
  "atomType": "JDBC",
  "privilege": "PRIVATE",
  "status": "HEALTHY",
  "browseGraph": "dde.jpg",
  "keyword": "Detrital Zicron, Sediment",
  "description": "Detrital Zicron Data From OneSediment",
  "coordinateReference": "WGS84",
  "projection": "Equirectangular",
  "authorName": "DDE",
  "authorMail": "DDE@dde.com",
  "doi": "",
  "associatedResource": "The Global Detrital Zircon Database: Quantifying the Timing and Rate of Crustal Growth",
  "associatedResourceUrl": "http://hdl.handle.net/10919/27785",
  "space": {
    "type": "TextTable",
    "resolution": "",
    "extent": {
      "minX": -180,
      "maxX": 180,
      "minY": 90,
      "maxY": -90
    }
  },
  "temporal": {
    "geologicTime": "",
    "geologicAge": "",
    "gtsVersion": "International",
    "base": 750,
    "top": 0
  },
  "fields": [
    {
      "fieldName": "ref_no",
      "type": "VARCHAR",
      "description": "reference number of zicron detrital"
    },
    {
      "fieldName": "lead_author",
      "type": "VARCHAR",
      "description": "lead author of reference paper"
    }
  ],
  "jdbcDpMeta": {
    "transfer": {
      "endpoint": [
        "112.124.238.115:25432"
      ],
      "protocol": "database"
    },
    "security": {
      "useTls": false
    },
    "jdbcRoute": {
      "databaseKind": "postgresql",
      "databaseName": "OneSediment",
      "version": "12.0",
      "password": "OneSediment_admin",
      "username": "OneSediment_admin",
      "options": "characterEncoding=utf8&serverTimezone=UTC"
    }
  },
  "tableName": "test"
}
```

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| rzpj | header | string | yes | Certificate |
| body | body | object | no | none |
| » name | body | string | yes | Unit name |
| » dataType | body | string | yes | Data type,Value = FILE, TABLE, JSON, PICTURE |
| » vectorType | body | string | yes | Vector type，Value = POINT, MULTIPOINT, LINESTRING, MULTILINESTRING, POLYGON, MULTIPOLYGON, GEOMETRYCOLLECTION |
| » atomType | body | string | yes | Metadata type,Value = LAYER_SERVICE,HTTP,JDBC,MYSQL,POSTGRESQL |
| » privilege | body | string | yes | AccessPermission,Value= public, private |
| » status | body | string | yes | Access Status,Value =  SETTING,HEALTHY, UNHEALTHY |
| » isOfficial | body | integer | yes | Is it official |
| » browseGraph | body | string | yes | Browse Graph |
| » keyword | body | string | yes | Keyword |
| » description | body | string | yes | Description |
| » coordinateReference | body | string | yes | coordinate Reference |
| » projection | body | string | yes | Projection coordinate system |
| » authorName | body | string | yes | Author name |
| » authorMail | body | string | yes | Author email |
| » doi | body | string | yes | The unique identifier of the data object |
| » associatedResource | body | string | yes | Associated resources |
| » associatedResourceUrl | body | string | yes | Link |
| » space | body | object | yes | Spatial Information |
| »» type | body | string | yes | Type |
| »» resolution | body | string | yes | Spatial resolution |
| »» extent | body | object | yes | extent |
| »»» minX | body | integer | yes | Minimum x |
| »»» maxX | body | integer | yes | Maximum x |
| »»» minY | body | integer | yes | Minimum y |
| »»» maxY | body | integer | yes | Maximum y |
| » temporal | body | object | yes | Time |
| »» geologicTime | body | string | yes | Geologic time，e.g, Quaternary |
| »» geologicAge | body | string | yes | Geological age，e.g,1，100 to 200.2 |
| »» gtsVersion | body | string | yes | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» base | body | integer | yes | The earliest possible time point，e.g,150.3 |
| »» top | body | integer | yes | The latest possible time point，e.g,10.2 |
| » fields | body | [string] | yes | Field Information |
| » jdbcDpMeta | body | object | yes | JDBC protocol meta |
| »» transfer | body | object | yes | Transfer information |
| »»» endpoint | body | [string] | yes | Endpoint |
| »»» protocol | body | string | yes | Data source protocol |
| »» security | body | object | yes | Encrypted information |
| »»» useTls | body | boolean | yes | TLS encryption |
| »» jdbcRoute | body | object | yes | JDBC Route |
| »»» databaseKind | body | string | yes | Database type |
| »»» databaseName | body | string | yes | Database name |
| »»» version | body | string | yes | Version |
| »»» password | body | string | yes | Password |
| »»» username | body | string | yes | Username |
| »»» options | body | string | yes | Options, character encoding, and database server time zone |
| » tableName | body | string | yes | Database table name |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "2421200a-293e-4146-ad82-c1472cc43d10"
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | DataAtom Information |
| »» uid | string | none | DataAtom UID |


## Dataset

### GET /v1.0/api/data-central/dataset/

GET /v1.0/api/data-central/dataset/

Obtain a dataset based on its id or uid

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| uid | query | string | no | Dataset uid, which cannot be empty at the same time as the id |
| id | query | string | no | Dataset id, which cannot be empty at the same time as the uid |
| rzpj | header | string | yea | Certificate |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "id": 25,
    "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3",
    "name": "Scotese & Wright 2018Ver.2",
    "type": "RASTER",
    "userId": "7003c445-1f0b-4f23-82ff-72dd345383fc",
    "privilege": "PUBLIC",
    "isOfficial": 0,
    "browseGraph": "dde.jpg",
    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
    "author": {
      "metaDataStandardName": "None",
      "metaDataIdentifier": "None",
      "createTimestamp": 1426734778313,
      "authorName": "Christopher Scotese, Nicky Wright",
      "authorEmail": "3180101626@zju.edu.cn",
      "responsible": "None",
      "responsibleRegion": "US",
      "responsibleEmail": "3180101626@zju.edu.cn",
      "announcement": "None",
      "dataProtectionPeriod": "0",
      "license": "Creative Commons Attribution 4.0 International"
    },
    "description": {
      "title": "Paleogeographic maps by Scotese & Wright (2018)",
      "alias": "Paleogeographic maps by Scotese & Wright (2018)",
      "edition": "Version 2",
      "language": "English",
      "encoding": "UTF-8",
      "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
      "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
      "topicCategory": "/Paleogeography",
      "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
      "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
      "source": "None",
      "date": "2018-08-01",
      "dataUrl": "https://zenodo.org/record/5460860"
    },
    "temporal": {
      "geologicTime": "Neoproterozoic and Phanerozoic",
      "geologicAge": "None",
      "base": 750,
      "top": 0,
      "gtsVersion": "International"
    },
    "space": {
      "type": "None",
      "resolution": "0.1 degree",
      "elevation": "-11000~10500",
      "extent": {
        "minX": -180,
        "maxX": 180,
        "minY": -90,
        "maxY": 90
      },
      "geoIdentifier": "Global"
    },
    "boundaryWKT": null,
    "coordinateReference": "WGS84",
    "projection": "Equirectangular",
    "service": {
      "type": "None",
      "doi": "None",
      "accessPrivilege": "None",
      "usePrivilege": "None",
      "associatedResource": "None",
      "associatedResMeta": "None",
      "coupledResource": "None",
      "distributionFormat": "None",
      "onlineResource": "None",
      "associatedPaperDOI": "None"
    },
    "createTime": 1650369385151,
    "updateTime": 1650369385151
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | Dataset Information |
| »» id | integer | none | Dataset ID |
| »» uid | string | none | Dataset UID |
| »» name | string | none | Unit name |
| »» type | string | none | Dataset Type |
| »» userId | string | none | Userid |
| »» privilege | string | none | AccessPermission,Value= public, private |
| »» isOfficial | integer | none | Is it official ? |
| »» browseGraph | string | none | BrowseGraph |
| »» keyword | string | none | Keyword |
| »» author | object | none | Author |
| »»» metaDataStandardName | string | none | Standard metadata name |
| »»» metaDataIdentifier | string | none | Metadata definition |
| »»» createTimestamp | integer | none | Metadata create timestamp |
| »»» authorName | string | none | Author name |
| »»» authorEmail | string | none | Author email |
| »»» responsible | string | none | Responsible |
| »»» responsibleRegion | string | none | Responsibile region |
| »»» responsibleEmail | string | none | Responsible Email |
| »»» announcement | string | none | Declaration |
| »»» dataProtectionPeriod | string | none | Data protection cycle |
| »»» license | string | none | License |
| »» description | object | none | Description |
| »»» title | string | none | Title |
| »»» alias | string | none | Alias |
| »»» edition | string | none | Version |
| »»» language | string | none | Language |
| »»» encoding | string | none | Encoding |
| »»» keyword | string | none | Keyword |
| »»» abstractInfo | string | none | Abstract information |
| »»» topicCategory | string | none | Topic category |
| »»» additionalDoc | string | none | Additional documentation |
| »»» lineage | string | none | Data lineage |
| »»» source | string | none | Source |
| »»» date | string | none | Date |
| »»» dataUrl | string | none | Data address |
| »» temporal | object | none | Time |
| »»» geologicTime | string | none | Geologic time，e.g, Quaternary |
| »»» geologicAge | string | none | Geological age，e.g,1，100 to 200.2 |
| »»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»» top | integer | none | The latest possible time point，e.g,10.2 |
| »»» gtsVersion | string | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» space | object | none | Spatial Information |
| »»» type | string | none | Type |
| »»» resolution | string | none | Spatial resolution |
| »»» elevation | string | none | Elevation |
| »»» extent | object | none | extent |
| »»»» minX | integer | none | Minimum x |
| »»»» maxX | integer | none | Maximum x |
| »»»» minY | integer | none | Minimum y |
| »»»» maxY | integer | none | Maximum y |
| »»» geoIdentifier | string | none | GeoIdentifier |
| »» boundaryWKT | null | none | The range of the spatial region. The value is returned in wkt format |
| »» coordinateReference | string | none | coordinate Reference |
| »» projection | string | none | Projection coordinate system |
| »» service | object | none | Service |
| »»» type | string | none | Dataset type |
| »»» doi | string | none | The unique identifier of the data object |
| »»» accessPrivilege | string | none | Access permissions |
| »»» usePrivilege | string | none | Permission |
| »»» associatedResource | string | none | Associated resources |
| »»» associatedResMeta | string | none | Associated resource metadata |
| »»» coupledResource | string | none | Coupling resources |
| »»» distributionFormat | string | none | Format of data distribution |
| »»» onlineResource | string | none | Reference resources online |
| »»» associatedPaperDOI | string | none | Associated paper DOI |
| »» createTime | integer | none | Created |
| »» updateTime | integer | none | Update Time |


### POST /v1.0/api/data-central/dataset

POST /v1.0/api/data-central/dataset/

Add a dataset

> Body request parameter


```json
{
  "name": "Scotese & Wright 2018Ver.2",
  "type": "RASTER",
  "privilege": "0",
  "browseGraph": "dde.jpg",
  "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
  "author": {
    "createTimestamp": 1426734778313,
    "authorName": "Christopher Scotese, Nicky Wright",
    "authorEmail": "cscotese@gmail.com",
    "responsible": "None",
    "responsibleRegion": "US",
    "responsibleEmail": "None",
    "license": "Creative Commons Attribution 4.0 International",
    "dataProtectionPeriod": "0",
    "announcement": "None",
    "metaDataIdentifier": "None",
    "metaDataStandardName": "None"
  },
  "description": {
    "edition": "Version 2",
    "language": "English",
    "encoding": "UTF-8",
    "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
    "topicCategory": "/Paleogeography",
    "alias": "Paleogeographic maps by Scotese & Wright (2018)",
    "date": "2018-08-01",
    "dataUrl": "https://zenodo.org/record/5460860",
    "title": "Paleogeographic maps by Scotese & Wright (2018)",
    "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
    "source": "None",
    "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860"
  },
  "temporal": {
    "geologicTime": "Neoproterozoic and Phanerozoic",
    "base": 750,
    "top": 0,
    "gtsVersion": "International",
    "geologicAge": "None"
  },
  "space": {
    "resolution": "0.1 degree",
    "extent": {
      "minX": -180,
      "maxX": 180,
      "minY": -90,
      "maxY": 90
    },
    "elevation": "-11000~10500",
    "geoIdentifier": "Global",
    "type": "None"
  },
  "coordinateReference": "WGS84",
  "projection": "Equirectangular",
  "service": {
    "associatedResource": "None",
    "associatedPaperDOI": "None",
    "doi": "None",
    "distributionFormat": "None",
    "onlineResource": "None",
    "usePrivilege": "None",
    "associatedResMeta": "None",
    "coupledResource": "None",
    "type": "None",
    "accessPrivilege": "None"
  }
}
```

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| rzpj | header | string | yes | Certificate |
| body | body | object | no | none |
| » name | body | string | yes | Dataset name |
| » type | body | string | yes | Dataset type |
| » privilege | body | string | yes | AccessPermission,Value= public, private |
| » isOfficial | body | integer | yes | Is it official ? |
| » browseGraph | body | string | yes | BrowseGraph |
| » keyword | body | string | yes | Keyword |
| » author | body | object | yes | Author |
| »» createTimestamp | body | integer | yes | Metadata create timestamp |
| »» authorName | body | string | yes | Author name |
| »» authorEmail | body | string | yes | Author email |
| »» responsible | body | string | yes | Responsible |
| »» responsibleRegion | body | string | yes | Responsibile region |
| »» responsibleEmail | body | string | yes | Responsible Email |
| »» license | body | string | yes | License |
| »» dataProtectionPeriod | body | string | yes | Data protection cycle |
| »» announcement | body | string | yes | Announcement |
| »» metaDataIdentifier | body | string | yes | Metadata definition |
| »» metaDataStandardName | body | string | yes | Standard metadata name |
| » description | body | object | yes | Description |
| »» edition | body | string | yes | Version |
| »» language | body | string | yes | Language |
| »» encoding | body | string | yes | Encoding |
| »» abstractInfo | body | string | yes | Abstract information |
| »» topicCategory | body | string | yes | Topic category |
| »» alias | body | string | yes | Alias |
| »» date | body | string | yes | Date |
| »» dataUrl | body | string | yes | Data address |
| »» title | body | string | yes | Title |
| »» lineage | body | string | yes | Data lineage |
| »» keyword | body | string | yes | Keyword |
| »» source | body | string | yes | Source |
| »» additionalDoc | body | string | yes | Additional documentation |
| » temporal | body | object | yes | Time |
| »» geologicTime | body | string | yes | Geologic time，e.g, Quaternary |
| »» base | body | integer | yes | The earliest possible time point，e.g,150.3 |
| »» top | body | integer | yes | The latest possible time point，e.g,10.2 |
| »» gtsVersion | body | string | yes | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» geologicAge | body | string | yes | Geological age，e.g,1，100 to 200.2 |
| » space | body | object | yes | Spatial Information |
| »» resolution | body | string | yes | Spatial resolution |
| »» extent | body | object | yes | extent |
| »»» minX | body | integer | yes | Minimum x |
| »»» maxX | body | integer | yes | Maximum x |
| »»» minY | body | integer | yes | Minimum y |
| »»» maxY | body | integer | yes | Maximum y |
| »» elevation | body | string | yes | Elevation |
| »» geoIdentifier | body | string | yes | GeoIdentifier |
| »» type | body | string | yes | Type |
| » coordinateReference | body | string | yes | coordinate Reference |
| » projection | body | string | yes | Projection coordinate system |
| » service | body | object | yes | Service |
| »» associatedResource | body | string | yes | Associated resources |
| »» associatedPaperDOI | body | string | yes | Associated paper DOI |
| »» doi | body | string | yes | The unique identifier of the data object |
| »» distributionFormat | body | string | yes | Format of data distribution |
| »» onlineResource | body | string | yes | Reference resources online |
| »» usePrivilege | body | string | yes | Permission |
| »» associatedResMeta | body | string | yes | Associated resource metadata |
| »» coupledResource | body | string | yes | Coupling resources |
| »» type | body | string | yes | Dataset type |
| »» accessPrivilege | body | string | yes | Access permissions |


> return example


> success


```json
{
  "code": 200,
  "message": "success",
  "data": {
    "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3"
  }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Message |
| » data | object | none | Dataset information |
| »» uid | string | none | Dataset UID |


### GET /v1.0/api/data-central/dataset/{datasetName}

GET /v1.0/api/data-central/dataset/{datasetName}

Obtain a dataset based on its name

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| datasetName | path | string | yes | Dataset Name |
| rzpj | header | string | yes | Certificate |


> return example


> success


```json
{
    "code": 200,
    "message": "success",
    "data": {
        "id": 25,
        "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3",
        "name": "Scotese & Wright 2018Ver.2",
        "type": "RASTER",
        "userId": "7003c445-1f0b-4f23-82ff-72dd345383fc",
        "privilege": "PUBLIC",
        "isOfficial": 0,
        "browseGraph": "wlq.jpg",
        "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
        "author": {
            "metaDataStandardName": "None",
            "metaDataIdentifier": "None",
            "createTimestamp": 1426734778313,
            "authorName": "Christopher Scotese, Nicky Wright",
            "authorEmail": "3180101626@zju.edu.cn",
            "responsible": "None",
            "responsibleRegion": "US",
            "responsibleEmail": "3180101626@zju.edu.cn",
            "announcement": "None",
            "dataProtectionPeriod": "0",
            "license": "Creative Commons Attribution 4.0 International"
        },
        "description": {
            "title": "Paleogeographic maps by Scotese & Wright (2018)",
            "alias": "Paleogeographic maps by Scotese & Wright (2018)",
            "edition": "Version 2",
            "language": "English",
            "encoding": "UTF-8",
            "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
            "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
            "topicCategory": "/Paleogeography",
            "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
            "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
            "source": "None",
            "date": "2018-08-01",
            "dataUrl": "https://zenodo.org/record/5460860"
        },
        "temporal": {
            "geologicTime": "Neoproterozoic and Phanerozoic",
            "geologicAge": "None",
            "base": 750,
            "top": 0,
            "gtsVersion": "International"
        },
        "space": {
            "type": "None",
            "resolution": "0.1 degree",
            "elevation": "-11000~10500",
            "extent": {
                "minX": -180,
                "maxX": 180,
                "minY": -90,
                "maxY": 90
            },
            "geoIdentifier": "Global"
        },
        "boundaryWKT": null,
        "coordinateReference": "WGS84",
        "projection": "Equirectangular",
        "service": {
            "type": "None",
            "doi": "None",
            "accessPrivilege": "None",
            "usePrivilege": "None",
            "associatedResource": "None",
            "associatedResMeta": "None",
            "coupledResource": "None",
            "distributionFormat": "None",
            "onlineResource": "None",
            "associatedPaperDOI": "None"
        },
        "createTime": 1650369385151,
        "updateTime": 1650369385151
    }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | Dataset Information |
| »» id | integer | none | Dataset ID |
| »» uid | string | none | Dataset UID |
| »» name | string | none | Unit name |
| »» type | string | none | Dataset Type |
| »» userId | string | none | Userid |
| »» privilege | string | none | AccessPermission,Value= public, private |
| »» isOfficial | integer | none | Is it official ? |
| »» browseGraph | string | none | BrowseGraph |
| »» keyword | string | none | Keyword |
| »» author | object | none | Author |
| »»» metaDataStandardName | string | none | Standard metadata name |
| »»» metaDataIdentifier | string | none | Metadata definition |
| »»» createTimestamp | integer | none | Metadata create timestamp |
| »»» authorName | string | none | Author name |
| »»» authorEmail | string | none | Author email |
| »»» responsible | string | none | Responsible |
| »»» responsibleRegion | string | none | Responsibile region |
| »»» responsibleEmail | string | none | Responsible Email |
| »»» announcement | string | none | Declaration |
| »»» dataProtectionPeriod | string | none | Data protection cycle |
| »»» license | string | none | License |
| »» description | object | none | Description |
| »»» title | string | none | Title |
| »»» alias | string | none | Alias |
| »»» edition | string | none | Version |
| »»» language | string | none | Language |
| »»» encoding | string | none | Encoding |
| »»» keyword | string | none | Keyword |
| »»» abstractInfo | string | none | Abstract information |
| »»» topicCategory | string | none | Topic category |
| »»» additionalDoc | string | none | Additional documentation |
| »»» lineage | string | none | Data lineage |
| »»» source | string | none | Source |
| »»» date | string | none | Date |
| »»» dataUrl | string | none | Data address |
| »» temporal | object | none | Time |
| »»» geologicTime | string | none | Geologic time，e.g, Quaternary |
| »»» geologicAge | string | none | Geological age，e.g,1，100 to 200.2 |
| »»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»» top | integer | none | The latest possible time point，e.g,10.2 |
| »»» gtsVersion | string | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» space | object | none | Spatial Information |
| »»» type | string | none | Type |
| »»» resolution | string | none | Spatial resolution |
| »»» elevation | string | none | Elevation |
| »»» extent | object | none | extent |
| »»»» minX | integer | none | Minimum x |
| »»»» maxX | integer | none | Maximum x |
| »»»» minY | integer | none | Minimum y |
| »»»» maxY | integer | none | Maximum y |
| »»» geoIdentifier | string | none | GeoIdentifier |
| »» boundaryWKT | null | none | The range of the spatial region. The value is returned in wkt format |
| »» coordinateReference | string | none | coordinate Reference |
| »» projection | string | none | Projection coordinate system |
| »» service | object | none | Service |
| »»» type | string | none | Dataset type |
| »»» doi | string | none | The unique identifier of the data object |
| »»» accessPrivilege | string | none | Access permissions |
| »»» usePrivilege | string | none | Permission |
| »»» associatedResource | string | none | Associated resources |
| »»» associatedResMeta | string | none | Associated resource metadata |
| »»» coupledResource | string | none | Coupling resources |
| »»» distributionFormat | string | none | Format of data distribution |
| »»» onlineResource | string | none | Reference resources online |
| »»» associatedPaperDOI | string | none | Associated paper DOI |
| »» createTime | integer | none | Created |
| »» updateTime | integer | none | Update Time |


### POST /v1.0/api/data-central/dataset/{datasetId}/atoms/uid

POST /v1.0/api/data-central/dataset/{datasetUid}/atoms/uid

Add an atom to a dataset

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| datasetUid | path | string | yes | Dataset UID |
| atomUids | query | string | yes | The Uid set of data atom |
| rzpj | header | string | yes | Certificate |


> return example


> success


```json
{
    "code": 200,
    "message": "success",
    "data": {
        "id": 25,
        "uid": "9c9798c6-c6e1-44d4-8083-8595bc15a0d3",
        "name": "Scotese & Wright 2018Ver.2",
        "type": "RASTER",
        "userId": "7003c445-1f0b-4f23-82ff-72dd345383fc",
        "privilege": "PUBLIC",
        "isOfficial": 0,
        "browseGraph": "dde.jpg",
        "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
        "author": {
            "metaDataStandardName": "None",
            "metaDataIdentifier": "None",
            "createTimestamp": 1426734778313,
            "authorName": "Christopher Scotese, Nicky Wright",
            "authorEmail": "3180101626@zju.edu.cn",
            "responsible": "None",
            "responsibleRegion": "US",
            "responsibleEmail": "3180101626@zju.edu.cn",
            "announcement": "None",
            "dataProtectionPeriod": "0",
            "license": "Creative Commons Attribution 4.0 International"
        },
        "description": {
            "title": "Paleogeographic maps by Scotese & Wright (2018)",
            "alias": "Paleogeographic maps by Scotese & Wright (2018)",
            "edition": "Version 2",
            "language": "English",
            "encoding": "UTF-8",
            "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
            "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
            "topicCategory": "/Paleogeography",
            "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
            "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
            "source": "None",
            "date": "2018-08-01",
            "dataUrl": "https://zenodo.org/record/5460860"
        },
        "temporal": {
            "geologicTime": "Neoproterozoic and Phanerozoic",
            "geologicAge": "None",
            "base": 750,
            "top": 0,
            "gtsVersion": "International"
        },
        "space": {
            "type": "None",
            "resolution": "0.1 degree",
            "elevation": "-11000~10500",
            "extent": {
                "minX": -180,
                "maxX": 180,
                "minY": -90,
                "maxY": 90
            },
            "geoIdentifier": "Global"
        },
        "boundaryWKT": null,
        "coordinateReference": "WGS84",
        "projection": "Equirectangular",
        "service": {
            "type": "None",
            "doi": "None",
            "accessPrivilege": "None",
            "usePrivilege": "None",
            "associatedResource": "None",
            "associatedResMeta": "None",
            "coupledResource": "None",
            "distributionFormat": "None",
            "onlineResource": "None",
            "associatedPaperDOI": "None"
        },
        "createTime": 1650369385151,
        "updateTime": 1650369385151
    }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | Dataset Information |
| »» id | integer | none | Dataset ID |
| »» uid | string | none | Dataset UID |
| »» name | string | none | Unit name |
| »» type | string | none | Dataset Type |
| »» userId | string | none | Userid |
| »» privilege | string | none | AccessPermission,Value= public, private |
| »» isOfficial | integer | none | Is it official ? |
| »» browseGraph | string | none | BrowseGraph |
| »» keyword | string | none | Keyword |
| »» author | object | none | Author |
| »»» metaDataStandardName | string | none | Standard metadata name |
| »»» metaDataIdentifier | string | none | Metadata definition |
| »»» createTimestamp | integer | none | Metadata create timestamp |
| »»» authorName | string | none | Author name |
| »»» authorEmail | string | none | Author email |
| »»» responsible | string | none | Responsible |
| »»» responsibleRegion | string | none | Responsibile region |
| »»» responsibleEmail | string | none | Responsible Email |
| »»» announcement | string | none | Declaration |
| »»» dataProtectionPeriod | string | none | Data protection cycle |
| »»» license | string | none | License |
| »» description | object | none | Description |
| »»» title | string | none | Title |
| »»» alias | string | none | Alias |
| »»» edition | string | none | Version |
| »»» language | string | none | Language |
| »»» encoding | string | none | Encoding |
| »»» keyword | string | none | Keyword |
| »»» abstractInfo | string | none | Abstract information |
| »»» topicCategory | string | none | Topic category |
| »»» additionalDoc | string | none | Additional documentation |
| »»» lineage | string | none | Data lineage |
| »»» source | string | none | Source |
| »»» date | string | none | Date |
| »»» dataUrl | string | none | Data address |
| »» temporal | object | none | Time |
| »»» geologicTime | string | none | Geologic time，e.g, Quaternary |
| »»» geologicAge | string | none | Geological age，e.g,1，100 to 200.2 |
| »»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»» top | integer | none | The latest possible time point，e.g,10.2 |
| »»» gtsVersion | string | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »» space | object | none | Spatial Information |
| »»» type | string | none | Type |
| »»» resolution | string | none | Spatial resolution |
| »»» elevation | string | none | Elevation |
| »»» extent | object | none | extent |
| »»»» minX | integer | none | Minimum x |
| »»»» maxX | integer | none | Maximum x |
| »»»» minY | integer | none | Minimum y |
| »»»» maxY | integer | none | Maximum y |
| »»» geoIdentifier | string | none | GeoIdentifier |
| »» boundaryWKT | null | none | The range of the spatial region. The value is returned in wkt format |
| »» coordinateReference | string | none | coordinate Reference |
| »» projection | string | none | Projection coordinate system |
| »» service | object | none | Service |
| »»» type | string | none | Dataset type |
| »»» doi | string | none | The unique identifier of the data object |
| »»» accessPrivilege | string | none | Access permissions |
| »»» usePrivilege | string | none | Permission |
| »»» associatedResource | string | none | Associated resources |
| »»» associatedResMeta | string | none | Associated resource metadata |
| »»» coupledResource | string | none | Coupling resources |
| »»» distributionFormat | string | none | Format of data distribution |
| »»» onlineResource | string | none | Reference resources online |
| »»» associatedPaperDOI | string | none | Associated paper DOI |
| »» createTime | integer | none | Created |
| »» updateTime | integer | none | Update Time |


### GET /v1.0/api/data-central/dataset/list/user

GET /v1.0/api/data-central/dataset/list/user

Obtain the list of DataSet belonging to the user

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| page | query | string | no | In the previous page, if you want to display the first page, use 0 |
| pageSize | query | string | no | Number of Entries displayed per page |
| spatialWkt | query | string | no | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top | query | string | no | Maximum time range for querying data |
| base | query | string | no | Minimum time range for querying data |
| keyword | query | string | no | Keyword |
| startTimestamp | query | string | no | Start time |
| endTimestamp | query | string | no | End time |
| rzpj | header | string | yes | Certificate |


> return example


> success


```json
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 2,
        "list": [
            {
                "id": 24,
                "uid": "5fd7fd2c-8140-42d5-b5bd-55f2061b3c3b",
                "name": "Paleogeographic maps by Scotese & Wright (2018)",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "Christopher Scotese, Nicky Wright",
                    "authorEmail": "cscotese@gmail.com",
                    "responsible": null,
                    "responsibleRegion": "US",
                    "responsibleEmail": null,
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": "Creative Commons Attribution 4.0 International"
                },
                "description": {
                    "title": "Paleogeographic maps by Scotese & Wright (2018)",
                    "alias": "Paleogeographic maps by Scotese & Wright (2018)",
                    "edition": "Version 2",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                    "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
                    "topicCategory": "/Paleogeography",
                    "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
                    "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
                    "source": null,
                    "date": "2018-08-01",
                    "dataUrl": "https://zenodo.org/record/5460860"
                },
                "temporal": {
                    "geologicTime": "Neoproterozoic and Phanerozoic",
                    "geologicAge": null,
                    "base": 750,
                    "top": 0,
                    "gtsVersion": "International"
                },
                "space": {
                    "type": null,
                    "resolution": "0.1 degree",
                    "elevation": "-11000~10500",
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": null,
                "createTime": 1648455648429,
                "updateTime": 1648455648429
            },
            {
                "id": 23,
                "uid": "bd215cf0-6d65-4b42-829d-3fdcacb55191",
                "name": "Hu et al. (2021) paleo-precipitation modeling",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "paleoclimate modeling, Phanerozoic, precipitation",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "Yongyun Hu",
                    "authorEmail": "yyhu@pku.edu.cn",
                    "responsible": "Yongyun Hu",
                    "responsibleRegion": "CN",
                    "responsibleEmail": "yyhu@pku.edu.cn",
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": null
                },
                "description": {
                    "title": "A high-resolution climate simulation dataset for the past 540 million years",
                    "alias": "A high-resolution climate simulation dataset for the past 540 million years",
                    "edition": "Version1.0 2022/4/30",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": null,
                    "abstractInfo": "Here we perform 55 snapshot simulations for the past 540 million years, with a 10-million-year interval, using the Community Earth System Model version 1.2.2 (CESM1.2.2). The climate simulation dataset includes global distributions of monthly surface temperatures and precipitation, with a nominal 1° horizontal resolution of 0.9375° × 1.25° in latitude and longitude. This open access climate dataset is useful for multidisciplinary research, such as paleoclimate, geology, geochemistry, and paleontology.",
                    "topicCategory": "/Surficial Geochemistry/Paleoclimate",
                    "additionalDoc": "Li, X., Y. Hu*, et al., 2022: A high-resolution climate simulation dataset for the past 540 million years, in review",
                    "lineage": null,
                    "source": null,
                    "date": null,
                    "dataUrl": null
                },
                "temporal": {
                    "geologicTime": "Phanerozoic",
                    "geologicAge": null,
                    "base": 540,
                    "top": 0,
                    "gtsVersion": "INTERNATIONAL"
                },
                "space": {
                    "type": null,
                    "resolution": "0.9375° × 1.25° in latitude and longitude",
                    "elevation": null,
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": {
                    "type": null,
                    "doi": null,
                    "accessPrivilege": null,
                    "usePrivilege": null,
                    "associatedResource": null,
                    "associatedResMeta": null,
                    "coupledResource": null,
                    "distributionFormat": null,
                    "onlineResource": null,
                    "associatedPaperDOI": null
                },
                "createTime": 1648452964288,
                "updateTime": 1648452964288
            }
        ]
    }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | Dataset Information |
| »» total | integer | none | The number of data records |
| »» list | [object] | none | Dataset list |
| »»» id | integer | none | Dataset ID |
| »»» uid | string | none | Dataset UID |
| »»» name | string | none | Unit name |
| »»» type | string | none | Dataset Type |
| »»» userId | string | none | Userid |
| »»» privilege | string | none | AccessPermission,Value= public, private |
| »»» isOfficial | integer | none | Is it official ? |
| »»» browseGraph | null | none | BrowseGraph |
| »»» keyword | string | none | Keyword |
| »»» author | object | none | Author |
| »»»» metaDataStandardName | null | none | Standard metadata name |
| »»»» metaDataIdentifier | null | none | Metadata definition |
| »»»» createTimestamp | integer | none | Metadata create timestamp |
| »»»» authorName | string | none | Author name |
| »»»» authorEmail | string | none | Author email |
| »»»» responsible | null | none | Responsible |
| »»»» responsibleRegion | string | none | Responsibile region |
| »»»» responsibleEmail | null | none | Responsible Email |
| »»»» announcement | null | none | Declaration |
| »»»» dataProtectionPeriod | null | none | Data protection cycle |
| »»»» license | string¦null | none | License |
| »»» description | object | none | Description |
| »»»» title | string | none | Title |
| »»»» alias | string | none | Alias |
| »»»» edition | string | none | Version |
| »»»» language | string | none | Language |
| »»»» encoding | string | none | Encoding |
| »»»» keyword | string¦null | none | Keyword |
| »»»» abstractInfo | string | none | Abstract information |
| »»»» topicCategory | string | none | Topic category |
| »»»» additionalDoc | string | none | Additional documentation |
| »»»» lineage | string¦null | none | Data lineage |
| »»»» source | null | none | Source |
| »»»» date | string¦null | none | Date |
| »»»» dataUrl | string¦null | none | Data address |
| »»» temporal | object | none | Time |
| »»»» geologicTime | string | none | Geologic time，e.g, Quaternary |
| »»»» geologicAge | null | none | Geological age，e.g,1，100 to 200.2 |
| »»»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»»» top | integer | none | The latest possible time point，e.g,10.2 |
| »»»» gtsVersion | string | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »»» space | object | none | Spatial Information |
| »»»» type | null | none | Type |
| »»»» resolution | string | none | Spatial resolution |
| »»»» elevation | string¦null | none | Elevation |
| »»»» extent | object | none | extent |
| »»»»» minX | integer | none | Minimum x |
| »»»»» maxX | integer | none | Maximum x |
| »»»»» minY | integer | none | Minimum y |
| »»»»» maxY | integer | none | Maximum y |
| »»»» geoIdentifier | string | none | GeoIdentifier |
| »»» boundaryWKT | string | none | The range of the spatial region. The value is returned in wkt format |
| »»» coordinateReference | string | none | coordinate Reference |
| »»» projection | string | none | Projection coordinate system |
| »»» service | object | none | Service |
| »»»» type | null | none | Dataset type |
| »»»» doi | null | none | The unique identifier of the data object |
| »»»» accessPrivilege | null | none | Access permissions |
| »»»» usePrivilege | null | none | Permission |
| »»»» associatedResource | null | none | Associated resources |
| »»»» associatedResMeta | null | none | Associated resource metadata |
| »»»» coupledResource | null | none | Coupling resources |
| »»»» distributionFormat | null | none | Format of data distribution |
| »»»» onlineResource | null | none | Reference resources online |
| »»»» associatedPaperDOI | null | none | Associated paper DOI |
| »»» createTime | integer | none | Created |
| »»» updateTime | integer | none | Update Time |


### GET /v1.0/api/data-central/dataset/list/public

GET /v1.0/api/data-central/dataset/list/public

Obtains a list of public DataAtom

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| page | query | string | no | In the previous page, if you want to display the first page, use 0 |
| pageSize | query | string | no | Number of Entries displayed per page |
| official | query | string | no | Is it official |
| spatialWkt | query | string | no | Enter wkt as the spatial query and return the boundaryWKT. If you do not specify this parameter, you will not be added to the spatial query. |
| top | query | string | no | Maximum time range for querying data |
| base | query | string | no | Minimum time range for querying data |
| keyword | query | string | no | Keyword |


> return example


> success


```json
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 2,
        "list": [
            {
                "id": 24,
                "uid": "5fd7fd2c-8140-42d5-b5bd-55f2061b3c3b",
                "name": "Paleogeographic maps by Scotese & Wright (2018)",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "Christopher Scotese, Nicky Wright",
                    "authorEmail": "cscotese@gmail.com",
                    "responsible": null,
                    "responsibleRegion": "US",
                    "responsibleEmail": null,
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": "Creative Commons Attribution 4.0 International"
                },
                "description": {
                    "title": "Paleogeographic maps by Scotese & Wright (2018)",
                    "alias": "Paleogeographic maps by Scotese & Wright (2018)",
                    "edition": "Version 2",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": "Paleogeography,Paleogeographic maps,Scotese & Wright",
                    "abstractInfo": "A series of paleogeographic maps ranging from 750 Ma to present",
                    "topicCategory": "/Paleogeography",
                    "additionalDoc": "Scotese, C. R., & Wright, N. M. (2018). PALEOMAP Paleodigital Elevation Models (PaleoDEMS) for the Phanerozoic [Map]. Zenodo. https://doi.org/10.5281/zenodo.5460860",
                    "lineage": "The maps are created and published by Scotese & Wright in 2018 under the Creative Commons licence.",
                    "source": null,
                    "date": "2018-08-01",
                    "dataUrl": "https://zenodo.org/record/5460860"
                },
                "temporal": {
                    "geologicTime": "Neoproterozoic and Phanerozoic",
                    "geologicAge": null,
                    "base": 750,
                    "top": 0,
                    "gtsVersion": "International"
                },
                "space": {
                    "type": null,
                    "resolution": "0.1 degree",
                    "elevation": "-11000~10500",
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": null,
                "createTime": 1648455648429,
                "updateTime": 1648455648429
            },
            {
                "id": 23,
                "uid": "bd215cf0-6d65-4b42-829d-3fdcacb55191",
                "name": "Hu et al. (2021) paleo-precipitation modeling",
                "type": "RASTER",
                "userId": "ADMIN",
                "privilege": "PUBLIC",
                "isOfficial": 1,
                "browseGraph": null,
                "keyword": "paleoclimate modeling, Phanerozoic, precipitation",
                "author": {
                    "metaDataStandardName": null,
                    "metaDataIdentifier": null,
                    "createTimestamp": 0,
                    "authorName": "author",
                    "authorEmail": "dde@dde.com",
                    "responsible": "dde",
                    "responsibleRegion": "CN",
                    "responsibleEmail": "dde@dde.com",
                    "announcement": null,
                    "dataProtectionPeriod": null,
                    "license": null
                },
                "description": {
                    "title": "A high-resolution climate simulation dataset for the past 540 million years",
                    "alias": "A high-resolution climate simulation dataset for the past 540 million years",
                    "edition": "Version1.0 2022/4/30",
                    "language": "English",
                    "encoding": "UTF-8",
                    "keyword": null,
                    "abstractInfo": "Here we perform 55 snapshot simulations for the past 540 million years, with a 10-million-year interval, using the Community Earth System Model version 1.2.2 (CESM1.2.2). The climate simulation dataset includes global distributions of monthly surface temperatures and precipitation, with a nominal 1° horizontal resolution of 0.9375° × 1.25° in latitude and longitude. This open access climate dataset is useful for multidisciplinary research, such as paleoclimate, geology, geochemistry, and paleontology.",
                    "topicCategory": "/Surficial Geochemistry/Paleoclimate",
                    "additionalDoc": "Li, X., Y. Hu*, et al., 2022: A high-resolution climate simulation dataset for the past 540 million years, in review",
                    "lineage": null,
                    "source": null,
                    "date": null,
                    "dataUrl": null
                },
                "temporal": {
                    "geologicTime": "Phanerozoic",
                    "geologicAge": null,
                    "base": 540,
                    "top": 0,
                    "gtsVersion": "INTERNATIONAL"
                },
                "space": {
                    "type": null,
                    "resolution": "0.9375° × 1.25° in latitude and longitude",
                    "elevation": null,
                    "extent": {
                        "minX": -180,
                        "maxX": 180,
                        "minY": -90,
                        "maxY": 90
                    },
                    "geoIdentifier": "Global"
                },
                "boundaryWKT": "POLYGON((-180 -90,-180 90,180 90,180 -90,-180 -90))",
                "coordinateReference": "WGS 84",
                "projection": "Equirectangular",
                "service": {
                    "type": null,
                    "doi": null,
                    "accessPrivilege": null,
                    "usePrivilege": null,
                    "associatedResource": null,
                    "associatedResMeta": null,
                    "coupledResource": null,
                    "distributionFormat": null,
                    "onlineResource": null,
                    "associatedPaperDOI": null
                },
                "createTime": 1648452964288,
                "updateTime": 1648452964288
            }
        ]
    }
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status Code |
| » message | string | none | Status Information |
| » data | object | none | Dataset Information |
| »» total | integer | none | The number of data records |
| »» list | [object] | none | Dataset list |
| »»» id | integer | none | Dataset ID |
| »»» uid | string | none | Dataset UID |
| »»» name | string | none | Unit name |
| »»» type | string | none | Dataset Type |
| »»» userId | string | none | Userid |
| »»» privilege | string | none | AccessPermission,Value= public, private |
| »»» isOfficial | integer | none | Is it official |
| »»» browseGraph | null | none | BrowseGraph |
| »»» keyword | string | none | Keyword |
| »»» author | object | none | Author |
| »»»» metaDataStandardName | null | none | Standard metadata name |
| »»»» metaDataIdentifier | null | none | Metadata definition |
| »»»» createTimestamp | integer | none | Metadata create timestamp |
| »»»» authorName | string | none | Author name |
| »»»» authorEmail | string | none | Author email |
| »»»» responsible | null | none | Responsible |
| »»»» responsibleRegion | string | none | Responsibile region |
| »»»» responsibleEmail | null | none | Responsible Email |
| »»»» announcement | null | none | Declaration |
| »»»» dataProtectionPeriod | null | none | Data protection cycle |
| »»»» license | string¦null | none | License |
| »»» description | object | none | Description |
| »»»» title | string | none | Title |
| »»»» alias | string | none | Alias |
| »»»» edition | string | none | Version |
| »»»» language | string | none | Language |
| »»»» encoding | string | none | Encoding |
| »»»» keyword | string¦null | none | Keyword |
| »»»» abstractInfo | string | none | Abstract information |
| »»»» topicCategory | string | none | Topic category |
| »»»» additionalDoc | string | none | Additional documentation |
| »»»» lineage | string¦null | none | Data lineage |
| »»»» source | null | none | Source |
| »»»» date | string¦null | none | Date |
| »»»» dataUrl | string¦null | none | Data address |
| »»» temporal | object | none | Time |
| »»»» geologicTime | string | none | Geologic time，e.g, Quaternary |
| »»»» geologicAge | null | none | Geological age，e.g,1，100 to 200.2 |
| »»»» base | integer | none | The earliest possible time point，e.g,150.3 |
| »»»» top | integer | none | The latest possible time point，e.g,10.2 |
| »»»» gtsVersion | string | none | Geological Age version，e.g,INTERNATIONAL CHRONOSTRATIGRAPHIC CHART v2021/05 |
| »»» space | object | none | Spatial Information |
| »»»» type | null | none | Type |
| »»»» resolution | string | none | Spatial resolution |
| »»»» elevation | string¦null | none | Elevation |
| »»»» extent | object | none | extent |
| »»»»» minX | integer | none | Minimum x |
| »»»»» maxX | integer | none | Maximum x |
| »»»»» minY | integer | none | Minimum y |
| »»»»» maxY | integer | none | Maximum y |
| »»»» geoIdentifier | string | none | GeoIdentifier |
| »»» boundaryWKT | string | none | The range of the spatial region. The value is returned in wkt format |
| »»» coordinateReference | string | none | coordinate Reference |
| »»» projection | string | none | Projection coordinate system |
| »»» service | object | none | Service |
| »»»» type | null | none | Dataset type |
| »»»» doi | null | none | The unique identifier of the data object |
| »»»» accessPrivilege | null | none | Access permissions |
| »»»» usePrivilege | null | none | Permission |
| »»»» associatedResource | null | none | Associated resources |
| »»»» associatedResMeta | null | none | Associated resource metadata |
| »»»» coupledResource | null | none | Coupling resources |
| »»»» distributionFormat | null | none | Format of data distribution |
| »»»» onlineResource | null | none | Reference resources online |
| »»»» associatedPaperDOI | null | none | Associated paper DOI |
| »»» createTime | integer | none | Created |
| »»» updateTime | integer | none | Update Time |


# Computation Hub API v0.5.1
## Job

### POST /v1.0/api/job

POST /v1.0/api/job  Create a job

> Body


```json
{
  "jobName": "New Interface Test - Task",
  "description": "New Interface Test - Task",
  "task": [
    {
      "taskId": "t0",
      "taskName": "fuxi-polygon feature to point",
      "toolId": "06be3ead-1f65-4765-b6ea-73fac365baaa",
      "args": [
        {
          "paramName": "polyShapefile",
          "value": "fuxi://shapefile/USA_states_adm1.shp"
        },
        {
          "paramName": "pointShapefile",
          "value": "fuxi://shapefile/USA_states_adm1_topoint.shp"
        }
      ],
      "upstream": []
    }
  ]
}
```

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| AccessKey | header | string | no | AccessKey |
| SecretKey | header | string | no | SecretKey |
| UserID | header | string | no | UserID |
| rzpj | header | string | no | Certificate |
| body | body | object | no | none |


> return example


#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

## Jupyter

### GET /v1.0/api/jupyter/user

GET /v1.0/api/jupyter/user

#### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| page | query | string | yes | In the previous page, if you want to display the first page, use 0 |
| pageSize | query | string | yes | Number of Entries displayed per page |
| rzpj | header | string | yes | Certificate |


> return example


> success


```json
{
    "jupyters": [
        {
            "userId": "DDE",
            "notebookName": "notebook1",
            "imageName": "zjugis/jupyterlab:0.31",
            "deploymentName": "notebook1",
            "serviceName": "jupyterlab-da36d413-d35e-4bfc-9562-33f2d69f54c8",
            "port": 30018,
            "resourceCPU": 600,
            "kernelCPU": 0.6,
            "resourceGPU": 600,
            "kernelGPU": 0.6,
            "resourceMemory": 1262,
            "startTime": 1649680748007,
            "endTime": 1649695148007,
            "status": "PAUSE",
            "url": "http://47.98.212.54:30018/notebook/lab"
        },
        {
            "userId": "DDE",
            "notebookName": "notebook1",
            "imageName": "zjugis/jupyterlab:0.31",
            "deploymentName": "notebook2",
            "serviceName": "jupyterlab-da36d413-d35e-4bfc-9562-33f2d69f54c8",
            "port": 30018,
            "resourceCPU": 600,
            "kernelCPU": 0.6,
            "resourceGPU": 600,
            "kernelGPU": 0.6,
            "resourceMemory": 1262,
            "startTime": 1649680748007,
            "endTime": 1649695148007,
            "status": "PAUSE",
            "url": "http://47.98.212.54:30018/notebook/lab"
        }
    ],
    "totalCount": 2
}
```

#### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


#### return structure

status code **200**

| name | type | constraint | description |
| --- | --- | --- | --- |
| » jupyters | [object] | none | Jupyter information |
| »» userId | string | none | Userid |
| »» notebookName | string | none | Notebook name |
| »» imageName | string | none | Image name |
| »» deploymentName | string | none | Deployment name |
| »» serviceName | string | none | Service name |
| »» port | integer | none | Port |
| »» resourceCPU | integer | none | Resource CPU |
| »» kernelCPU | number | none | Kernel CPU |
| »» resourceGPU | integer | none | Resource GPU |
| »» kernelGPU | number | none | Kernel GPU |
| »» resourceMemory | integer | none | Resource memory |
| »» startTime | integer | none | Start time |
| »» endTime | integer | none | End time |
| »» status | string | none | Status |
| »» url | string | none | URL |
| » field1 | string | none | Field |
| » totalCount | integer | none | Number of Users |


# Knowledge Hub API v0.5.1
## GET /geoopenkg/api/search/compound

Search based on specified search criteria

### request parameter
| name | location | type | necessary | description |
| --- | --- | --- | --- | --- |
| keyword | query | string | no | Search keywords |
| isPrecise | query | string | no | Is it an exact query |
| containInstance | query | string | no | Whether the instance is included |
| source | query | string | no | SOURCE，Value = BO4GK、GAKG、GPKG，Separate multiple values with commas (,) |
| discipline | query | string | no | discipline，Separate different disciplines with commas (,) |
| pageNum | query | string | no | The number of pages. Default value: 1 |
| pageSize | query | string | no | The number of entries to return on each page. Default value: 10 |


> return example

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 99,
        "GPKG": {
            "total": 77,
            "rows": [
                {
                    "name": "Spatial Scale",
                    "description": "The spatial scale depends on the cause of the chemostratigraphic index/marker being local, regional, basinal, and global, based on which, the chemozone recognized could be correlated at an appropriate scale.",
                    "source": "GPKG",
                    "id": 1262,
                    "discipline": 1,
                    "label": "Class",
                    "uri": "Spatial Scale"
                },
                {
                    "name": "Spatial resolution_1",
                    "description": "The beam size of focused primary beam.",
                    "source": "GPKG",
                    "id": 28911,
                    "discipline": 3,
                    "label": "Class",
                    "uri": "Spatial resolution_1"
                },
                {
                    "name": "Caprock spatial area",
                    "description": "The spatial area of caprock.Cover distribution range",
                    "source": "GPKG",
                    "id": 31958,
                    "discipline": 16,
                    "label": "Class",
                    "uri": "Caprock spatial area"
                },
                {
                    "name": "Spatial filters",
                    "description": "The spatial filtering is a method of image filtering by convolution operation based on the spatial relationship between pixels and surrounding neighborhood pixels.",
                    "source": "GPKG",
                    "id": 32283,
                    "discipline": 12,
                    "label": "Class",
                    "uri": "Spatial filters"
                },
                {
                    "name": "Gravity spatial variation",
                    "description": " The gravity varies from the equator to the poles of rotation by about 0.5%, changing by slightly more than 5 Gal from approximately 978 Gal at the equator to 983 Gal at the poles. First, one more important factor which accounts for more than 3 of the 5 Gal, is the change in the centrifugal force over the Earth’s surface caused by the Earth’s rotation around its axis. The second factor of the planetary change in gravity (about 6Gal) over the Earth’ s surface is the variation in the radius from the equator to the poles. Finally, the subsurface mass with density contrast will cause several hundred mGal.",
                    "source": "GPKG",
                    "id": 32351,
                    "discipline": 12,
                    "label": "Class",
                    "uri": "Gravity spatial variation"
                },
                {
                    "name": "Classified by spatial distribution characteristics",
                    "description": "According to the characteristics of spatial distribution, map symbols are divided into point symbols, linear symbols and Planar symbols.",
                    "source": "GPKG",
                    "id": 39544,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Classified by spatial distribution characteristics"
                },
                {
                    "name": "Spatial oblique Mercator projection",
                    "description": "An oblique pseudo-cylindrical projection in which the central axis of a cylinder is perpendicular to the plane of the satellite orbit. It is suitable for cartography of narrow areas extending along the direction of satellite orbit.",
                    "source": "GPKG",
                    "id": 39664,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial oblique Mercator projection"
                },
                {
                    "name": "Spatial data reference information",
                    "description": "Spatial Reference Information -- the description of the reference frame for, and the means to encode, coordinates in the data set.",
                    "source": "GPKG",
                    "id": 40091,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial data reference information"
                },
                {
                    "name": "Spatial database",
                    "description": "A spatial database is a database that is optimized for storing and querying data that represents objects defined in a geometric space. ",
                    "source": "GPKG",
                    "id": 40117,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial database"
                },
                {
                    "name": "Spatial data type",
                    "description": "The most general shape is represented by the geometry described by the spatial representation system, which is a coordinate system similar to longitude and latitude or other accepted frames.",
                    "source": "GPKG",
                    "id": 40118,
                    "discipline": 13,
                    "label": "Class",
                    "uri": "Spatial data type"
                }
            ]
        },
        "GAKG": {
            "total": 3,
            "rows": [
                {
                    "name": "paper",
                    "lable": "Class",
                    "description": "Papers are often used to refer to articles that conduct research in various academic fields and describe academic research results.",
                    "id": "1",
                    "source": "GAKG",
                    "discipline": "GeoScience",
                    "uri": "https://www.acekg.cn/concept#paper"
                },
                {
                    "name": "journal",
                    "lable": "ObjectProperty",
                    "description": "A relationship between the paper and the author.",
                    "id": "3",
                    "source": "GAKG",
                    "discipline": "GeoScience",
                    "uri": "https://www.acekg.cn/relation#is_written_by"
                },
                {
                    "lable": "Class",
                    "description": "A peer-reviewed journal in which articles published in academic journals usually involve specific disciplines.",
                    "source": "GAKG",
                    "discipline": "GeoScience",
                    "uri": "https://www.acekg.cn/concept#journal"
                }
            ]
        },
        "time": 175,
        "BO4GK": {
            "total": 22,
            "rows": [
                {
                    "id": "graph3_16440",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#geometry_op",
                    "name": "geometry_op",
                    "description": "object properties for geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_16448",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/uso#geometry_type",
                    "name": "geometry_type",
                    "description": "describing the geometry type of spatial object",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_28736",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/uso#location",
                    "name": "location",
                    "description": "class showing where is a spatial object.",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_4224",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#geometry_dp",
                    "name": "geometry_dp",
                    "description": "data properties for geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph5_45168",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/crs#extent",
                    "name": "extent",
                    "description": "applicable spatial extent of a coordinate reference system",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_8248",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_geometry_form",
                    "name": "has_geometry_form",
                    "description": "form of representing the geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_20536",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_geometry_members",
                    "name": "has_geometry_members",
                    "description": "members of the combine geometry of spatial objects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_24640",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_geometry_type",
                    "name": "has_geometry_type",
                    "description": "describing type of geometric representations of spatial objects.",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_8352",
                    "source": "BO4GK",
                    "label": "Class",
                    "uri": "http://bo4gk.org/uso#location_type",
                    "name": "location_type",
                    "description": "the type showing the location of spatial ojects",
                    "discipline": "Spatial Ontology"
                },
                {
                    "id": "graph3_20640",
                    "source": "BO4GK",
                    "label": "ObjectProperty",
                    "uri": "http://bo4gk.org/uso#has_location_value",
                    "name": "has_location_value",
                    "description": "the value of location of a spatial object",
                    "discipline": "Spatial Ontology"
                }
            ]
        }
    }
}
```

### return result
| status code | status code message | description | data mode |
| --- | --- | --- | --- |
| 200 | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | success | Inline |


### return structure
| name | type | constraint | description |
| --- | --- | --- | --- |
| » code | integer | none | Status code |
| » message | string | none | Status message |
| » data | [string] | none | Data |

