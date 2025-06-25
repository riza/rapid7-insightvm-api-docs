# Tag Endpoints

## Description
Resources and operations for managing tags.

This document contains 21 endpoints under the Tag tag.

---

## 1. Tags

# Tags

**Endpoint:** `GET /api/3/tags`

## Description
Returns all tags.

**Operation ID:** `getTags`

## Parameters

### Parameter 1
**Name:** `name`
**Location:** query
**Type:** string
**Required:** No
**Description:** name

### Parameter 2
**Name:** `type`
**Location:** query
**Type:** string
**Required:** No
**Description:** type

### Parameter 3
**Name:** `page`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The index of the page (zero-based) to retrieve.

### Parameter 4
**Name:** `size`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The number of records per page to retrieve.

### Parameter 5
**Name:** `sort`
**Location:** query
**Type:** array
**Required:** No
**Description:** The criteria to sort the records by, in the format: `property[,ASC|DESC]`. The default sort order is ascending. Multiple sort criteria can be specified using multiple sort query parameters.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«Tag»`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "page": {
    "number": 6,
    "size": 10,
    "totalPages": 13,
    "totalResources": 123
  },
  "resources": [
    {
      "color": "default",
      "created": "2017-10-07T23:50:01.205Z",
      "id": 6,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "My Custom Tag",
      "riskModifier": 2,
      "searchCriteria": {
        "filters": [
          {
            "field": "",
            "lower": {},
            "operator": "",
            "upper": {},
            "value": {},
            "values": [
              {}
            ]
          }
        ],
        "match": "all"
      },
      "source": "custom",
      "type": "custom"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 2. Tags

# Tags

**Endpoint:** `POST /api/3/tags`

## Description
Creates a new tag.

**Operation ID:** `createTag`

## Parameters

### Parameter 1
**Name:** `tag`
**Location:** body
**Type:** Tag
**Required:** No
**Description:** The details of the tag.
**JSON Example:**
```json
{
  "color": "default",
  "created": "2017-10-07T23:50:01.205Z",
  "id": 6,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "My Custom Tag",
  "riskModifier": 2,
  "searchCriteria": {
    "filters": [
      {
        "field": "",
        "lower": {},
        "operator": "",
        "upper": {},
        "value": {},
        "values": [
          {}
        ]
      }
    ],
    "match": "all"
  },
  "source": "custom",
  "type": "custom"
}
```

## Request Body
**Name:** `tag`
**Location:** body
**Type:** Tag
**Required:** No
**Description:** The details of the tag.
**JSON Example:**
```json
{
  "color": "default",
  "created": "2017-10-07T23:50:01.205Z",
  "id": 6,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "My Custom Tag",
  "riskModifier": 2,
  "searchCriteria": {
    "filters": [
      {
        "field": "",
        "lower": {},
        "operator": "",
        "upper": {},
        "value": {},
        "values": [
          {}
        ]
      }
    ],
    "match": "all"
  },
  "source": "custom",
  "type": "custom"
}
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«TagID,Link»`
**Example JSON Response:**
```json
{
  "id": "<id>",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 3. Tag

# Tag

**Endpoint:** `GET /api/3/tags/{id}`

## Description
Returns a tag.

**Operation ID:** `getTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `Tag`
**Example JSON Response:**
```json
{
  "color": "default",
  "created": "2017-10-07T23:50:01.205Z",
  "id": 6,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "My Custom Tag",
  "riskModifier": 2,
  "searchCriteria": {
    "filters": [
      {
        "field": "",
        "lower": {},
        "operator": "",
        "upper": {},
        "value": {},
        "values": [
          {}
        ]
      }
    ],
    "match": "all"
  },
  "source": "custom",
  "type": "custom"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 4. Tag

# Tag

**Endpoint:** `PUT /api/3/tags/{id}`

## Description
Updates the details of a tag. For more information about accepted fields for the tag search criteria see the PUT /search_criteria documentation.

**Operation ID:** `updateTag`

## Parameters

### Parameter 1
**Name:** `tag`
**Location:** body
**Type:** Tag
**Required:** No
**Description:** The details of the tag.
**JSON Example:**
```json
{
  "color": "default",
  "created": "2017-10-07T23:50:01.205Z",
  "id": 6,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "My Custom Tag",
  "riskModifier": 2,
  "searchCriteria": {
    "filters": [
      {
        "field": "",
        "lower": {},
        "operator": "",
        "upper": {},
        "value": {},
        "values": [
          {}
        ]
      }
    ],
    "match": "all"
  },
  "source": "custom",
  "type": "custom"
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Request Body
**Name:** `tag`
**Location:** body
**Type:** Tag
**Required:** No
**Description:** The details of the tag.
**JSON Example:**
```json
{
  "color": "default",
  "created": "2017-10-07T23:50:01.205Z",
  "id": 6,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "My Custom Tag",
  "riskModifier": 2,
  "searchCriteria": {
    "filters": [
      {
        "field": "",
        "lower": {},
        "operator": "",
        "upper": {},
        "value": {},
        "values": [
          {}
        ]
      }
    ],
    "match": "all"
  },
  "source": "custom",
  "type": "custom"
}
```

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 5. Tag

# Tag

**Endpoint:** `DELETE /api/3/tags/{id}`

## Description
Deletes the tag.

**Operation ID:** `deleteTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 6. Tag Asset Groups

# Tag Asset Groups

**Endpoint:** `GET /api/3/tags/{id}/asset_groups`

## Description
Returns the asset groups associated with the tag.

**Operation ID:** `getTagAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«AssetGroupID,Link»`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "resources": [
    42
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 7. Tag Asset Groups

# Tag Asset Groups

**Endpoint:** `PUT /api/3/tags/{id}/asset_groups`

## Description
Sets the asset groups associated with the tag.

**Operation ID:** `setTaggedAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `assetGroupIds`
**Location:** body
**Type:** array
**Required:** No
**Description:** The asset groups to add to the tag.
**JSON Example:**
```json
[
  42
]
```

## Request Body
**Name:** `assetGroupIds`
**Location:** body
**Type:** array
**Required:** No
**Description:** The asset groups to add to the tag.
**JSON Example:**
```json
[
  42
]
```

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 8. Tag Asset Groups

# Tag Asset Groups

**Endpoint:** `DELETE /api/3/tags/{id}/asset_groups`

## Description
Removes the associations between the tag and all asset groups.

**Operation ID:** `untagAllAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 9. Tag Asset Group

# Tag Asset Group

**Endpoint:** `PUT /api/3/tags/{id}/asset_groups/{assetGroupId}`

## Description
Adds an asset group to this tag.

**Operation ID:** `tagAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `assetGroupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The asset group identifier.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 10. Tag Asset Group

# Tag Asset Group

**Endpoint:** `DELETE /api/3/tags/{id}/asset_groups/{assetGroupId}`

## Description
Removes an asset group from this tag.

**Operation ID:** `untagAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `assetGroupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The asset group identifier.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 11. Tag Assets

# Tag Assets

**Endpoint:** `GET /api/3/tags/{id}/assets`

## Description
Returns the assets tagged with a tag.

**Operation ID:** `getTaggedAssets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `TaggedAssetReferences`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "resources": [
    {
      "id": 78,
      "sources": [
        "site"
      ]
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 12. Tag Asset

# Tag Asset

**Endpoint:** `PUT /api/3/tags/{id}/assets/{assetId}`

## Description
Adds an asset to the tag.

**Operation ID:** `tagAsset`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 13. Tag Asset

# Tag Asset

**Endpoint:** `DELETE /api/3/tags/{id}/assets/{assetId}`

## Description
Removes an asset from the tag. Note: The asset must be added through the asset or tag, if the asset is added using a site, asset group, or search criteria this will not remove the asset.

**Operation ID:** `untagAsset`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 14. Tag Search Criteria

# Tag Search Criteria

**Endpoint:** `GET /api/3/tags/{id}/search_criteria`

## Description
Returns the search criteria associated with the tag.

**Operation ID:** `getTagSearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `SearchCriteria`
**Example JSON Response:**
```json
{
  "filters": [
    {
      "field": "",
      "lower": {},
      "operator": "",
      "upper": {},
      "value": {},
      "values": [
        {}
      ]
    }
  ],
  "match": "all"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 15. Tag Search Criteria

# Tag Search Criteria

**Endpoint:** `PUT /api/3/tags/{id}/search_criteria`

## Description
Updates the search criteria associated with the tag. The following table outlines the search criteria fields and the available operators: | Field | Operators | | ---------- | ---------------- | | ip-address | is, is-not, in-range, not-in-range, is-like, not-like | | ip-address-type | in, not-in | | alternate-address-type | in | | host-name | is, is-not, starts-with, ends-with, contains, does-not-contain, is-empty, is-not-empty, is-like, not-like | | host-type | in, not-in | | operating-system | contains, does-not-contain, is-empty, is-not-empty | | software | contains, does-not-contain| | open-ports | is, is-not, in-range | | service-name | contains, does-not-contain | | risk-score | is, is-not, in-range, is-greater-than,is-less-than | | last-scan-date | is-on-or-before, is-on-or-after, is-between, is-earlier-than, is-within-the-last | | vulnerability-assessed | is-on-or-before, is-on-or-after, is-between, is-earlier-than, is-within-the-last | | vulnerability-category | is, is-not, starts-with, ends-with, contains, does-not-contain| | vulnerability-cvss-score | is, is-not, in-range, is-greater-than, is-less-than | | vulnerability-cvss-v3-score | is, is-not, in-range, is-greater-than, is-less-than | | vulnerability-exposures | includes, does not-include | | vulnerability-title | contains, does-not-contain, is, is-not, starts-with, ends-with | | cve | is, is-not, contains, does-not-contain | | cvss-access-complexity | is, is-not | | cvss-authentication-required | is, is-not | | cvss-access-vector | is, is-not | | cvss-availability-impact | is, is-not | | cvss-confidentiality-impact | is, is-not | | cvss-integrity-impact | is, is-not | | cvss-v3-confidentiality-impact | is, is-not | | cvss-v3-integrity-impact | is, is-not | | cvss-v3-availability-impact | is, is-not | | cvss-v3-attack-vector | is, is-not | | cvss-v3-attack-complexity | is, is-not | | cvss-v3-user-interaction | is, is-not | | cvss-v3-privileges-required | is, is-not | | mobile-device-last-sync | is-within-the-last, is-earlier-than | | pci-compliance | is | | site-id | in, not-in | | criticality-tag | is, is-not, is-greater-than, is-less-than, is-applied, is-not-applied | | custom-tag | is, is-not, starts-with, ends-with, contains, does-not-contain, is-applied, is-not-applied | | location-tag | is, is-not, starts-with, ends-with, contains, does-not-contain, is-applied, is-not-applied | | owner-tag | is, is-not, starts-with, ends-with, contains, does-not-contain, is-applied, is-not-applied | | vulnerability-validated-status | are | | vasset-cluster | is, is-not, contains, does-not-contain, starts-with | | vasset-datacenter | is, is-not | | vasset-host name | is, is-not, contains, does-not-contain, starts-with | | vasset-power state | in, not-in | | vasset-resource pool path | contains, does-not-contain | | container-image | is, is-not, starts-with, ends-with, contains, does-not-contain, is-like, not-like | | container-status | is, is-not | | containers | are | The following table outlines the operators and the values associated with them: | Operator | Values | | -------- | ------ | | are | A single string property named "value" | | is-between | A number property named "lower" and a number property named "upper" | | contains | A single string property named "value" | | does-not-contain | A single string property named "value" | | is-earlier-than | A single number property named "value" | | ends-with | A single string property named "value" | | is-greater-than | A single number property named "value" | | in | An array property named "values" | | not-in | An array property named "values" | | in-range | A number property named "lower" and a number property named "upper" | | includes | An array property named "values" | | is | A single string property named "value" | | is-not | A single string property named "value" | | is-applied | No value | | is-not-applied | No value | | is-empty | No value | | is-not-empty | No value | | is-less-than | A single number property named "value" | | is-like | A single string property named "value" | | does-not-contain | A single string property named "value" | | not-in-range | A number property named "lower" and a number property named "upper" | | not-like | A single string property named "value" | | is-on-or-after | A single string property named "value", which is the date in ISO8601 format (yyyy-MM-dd) | | is-on-or-before | A single string property named "value", which is the date in ISO8601 format (yyyy-MM-dd) | | starts-with | A single string property named "value" | | is-within-the-last | A single number property named "value" | The following fields have enumerated values: | Field | Acceptable Values | | ----- | ----------------- | | containers | 0=present, 1=not present | | vulnerability-validated-status | 0=present, 1=not present | | pci-compliance | 0=fail, 1=pass | | alternate-address-type | 0=IPv4, 1=IPv6 | | ip-address-type | 0=IPv4, 1=IPv6 | | host-type | 0=Unknown, 1=Guest, 2=Hypervisor, 3=Physical, 4=Mobile | | cvss-access-complexity | L=Low, M=Medium, H=High | | cvss-integrity-impact | N=None, P=Partial, C=Complete | | cvss-confidentiality-impact | N=None, P=Partial, C=Complete | | cvss-availability-impact | N=None, P=Partial, C=Complete | | cvss-access-vector | L=Local, A=Adjacent, N=Network | | cvss-authentication-required | N=None, S=Single, M=Multiple | | cvss-access-complexity | L=Low, M=Medium, H=High | | cvss-v3-confidentiality-impact | N=None, L=Low, H=High | | cvss-v3-integrity-impact | N=None, L=Low, H=High | | cvss-v3-availability-impact | N=None, L=Low, H=High | | cvss-v3-attack-vector | N=Network, A=Adjacent, L=Local, P=Physical | | cvss-v3-attack-complexity | L=Low, H=High | | cvss-v3-user-interaction | N=None, R=Required | | cvss-v3-privileges-required | N=None, L=Low, H=High | | container-status | created, running, paused, restarting, exited, dead, unknown |

**Operation ID:** `updateTagSearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `criterial`
**Location:** body
**Type:** SearchCriteria
**Required:** No
**Description:** The details of the search criteria.
**JSON Example:**
```json
{
  "filters": [
    {
      "field": "",
      "lower": {},
      "operator": "",
      "upper": {},
      "value": {},
      "values": [
        {}
      ]
    }
  ],
  "match": "all"
}
```

## Request Body
**Name:** `criterial`
**Location:** body
**Type:** SearchCriteria
**Required:** No
**Description:** The details of the search criteria.
**JSON Example:**
```json
{
  "filters": [
    {
      "field": "",
      "lower": {},
      "operator": "",
      "upper": {},
      "value": {},
      "values": [
        {}
      ]
    }
  ],
  "match": "all"
}
```

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 16. Tag Search Criteria

# Tag Search Criteria

**Endpoint:** `DELETE /api/3/tags/{id}/search_criteria`

## Description
Removes the search criteria associated with the tag.

**Operation ID:** `removeTagSearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 17. Tag Sites

# Tag Sites

**Endpoint:** `GET /api/3/tags/{id}/sites`

## Description
Returns the sites associated with the tag.

**Operation ID:** `getTaggedSites`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«SiteID,Link»`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "resources": [
    42
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 18. Tag Sites

# Tag Sites

**Endpoint:** `PUT /api/3/tags/{id}/sites`

## Description
Sets the sites associated with the tag.

**Operation ID:** `setTaggedSites`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `sites`
**Location:** body
**Type:** array
**Required:** No
**Description:** The sites to add to the tag.
**JSON Example:**
```json
[
  42
]
```

## Request Body
**Name:** `sites`
**Location:** body
**Type:** array
**Required:** No
**Description:** The sites to add to the tag.
**JSON Example:**
```json
[
  42
]
```

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 19. Tag Sites

# Tag Sites

**Endpoint:** `DELETE /api/3/tags/{id}/sites`

## Description
Removes the associations between the tag and the sites.

**Operation ID:** `removeTaggedSites`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 20. Tag Site

# Tag Site

**Endpoint:** `PUT /api/3/tags/{id}/sites/{siteId}`

## Description
Adds a site to this tag.

**Operation ID:** `tagSite`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `siteId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 400
**Description:** Bad Request
**Schema:** `BadRequestError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "400"
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 21. Tag Site

# Tag Site

**Endpoint:** `DELETE /api/3/tags/{id}/sites/{siteId}`

## Description
Removes a site from this tag.

**Operation ID:** `untagSite`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

### Parameter 2
**Name:** `siteId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Links`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 401
**Description:** Unauthorized
**Schema:** `UnauthorizedError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "401"
}
```

### 404
**Description:** Not Found
**Schema:** `NotFoundError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "404"
}
```

### 500
**Description:** Internal Server Error
**Schema:** `InternalServerError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "500"
}
```

### 503
**Description:** Service Unavailable
**Schema:** `ServiceUnavailableError`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "message": "An error has occurred.",
  "status": "503"
}
```

## Request Content-Type
- `application/json`

## Response Content-Type
- `application/json;charset=UTF-8`


---
