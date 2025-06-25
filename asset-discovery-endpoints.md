# Asset Discovery Endpoints

## Description
Resources for managing and viewing the mechanisms used to automatically discover assets.

This document contains 10 endpoints under the Asset Discovery tag.

---

## 1. Discovery Connections

# Discovery Connections

**Endpoint:** `GET /api/3/discovery_connections`

## Description
Returns all discovery connections.

**Operation ID:** `getDiscoveryConnections`

## Parameters

### Parameter 1
**Name:** `page`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The index of the page (zero-based) to retrieve.

### Parameter 2
**Name:** `size`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The number of records per page to retrieve.

### Parameter 3
**Name:** `sort`
**Location:** query
**Type:** array
**Required:** No
**Description:** The criteria to sort the records by, in the format: `property[,ASC|DESC]`. The default sort order is ascending. Multiple sort criteria can be specified using multiple sort query parameters.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«DiscoveryConnection»`
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
      "accessKeyId": "",
      "address": "",
      "arn": "",
      "awsSessionName": "",
      "connectionType": "",
      "eventSource": "",
      "exchangeServerHostname": "",
      "exchangeUser": "",
      "folderPath": "",
      "id": "",
      "ldapServer": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "Connection 1",
      "port": "",
      "protocol": "",
      "region": "",
      "scanEngineIsInsideAWS": false,
      "secretAccessKey": "",
      "status": "",
      "username": "",
      "winRMServer": ""
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

## 2. Discovery Connection

# Discovery Connection

**Endpoint:** `GET /api/3/discovery_connections/{id}`

## Description
Returns a discovery connection.

**Operation ID:** `getDiscoveryConnection`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the discovery connection.

## Responses

### 200
**Description:** OK
**Schema:** `DiscoveryConnection`
**Example JSON Response:**
```json
{
  "accessKeyId": "",
  "address": "",
  "arn": "",
  "awsSessionName": "",
  "connectionType": "",
  "eventSource": "",
  "exchangeServerHostname": "",
  "exchangeUser": "",
  "folderPath": "",
  "id": "",
  "ldapServer": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Connection 1",
  "port": "",
  "protocol": "",
  "region": "",
  "scanEngineIsInsideAWS": false,
  "secretAccessKey": "",
  "status": "",
  "username": "",
  "winRMServer": ""
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

## 3. Discovery Connection Reconnect

# Discovery Connection Reconnect

**Endpoint:** `POST /api/3/discovery_connections/{id}/connect`

## Description
Attempts to reconnect the discovery connection.

**Operation ID:** `reconnectDiscoveryConnection`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the discovery connection.

## Responses

### 200
**Description:** OK

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

## 4. Sonar Queries

# Sonar Queries

**Endpoint:** `GET /api/3/sonar_queries`

## Description
Returns all sonar queries.

**Operation ID:** `getSonarQueries`

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SonarQuery»`
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
      "criteria": {
        "filters": [
          {
            "days": "",
            "domain": "acme.com",
            "lower": "",
            "type": "domain-contains",
            "upper": ""
          }
        ]
      },
      "id": 14,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "Assets in Domain"
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

## 5. Sonar Queries

# Sonar Queries

**Endpoint:** `POST /api/3/sonar_queries`

## Description
Creates a sonar query.

**Operation ID:** `createSonarQuery`

## Parameters

### Parameter 1
**Name:** `query`
**Location:** body
**Type:** SonarQuery
**Required:** No
**Description:** The criteria for a Sonar query.
**JSON Example:**
```json
{
  "criteria": {
    "filters": [
      {
        "days": "",
        "domain": "acme.com",
        "lower": "",
        "type": "domain-contains",
        "upper": ""
      }
    ]
  },
  "id": 14,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Assets in Domain"
}
```

## Request Body
**Name:** `query`
**Location:** body
**Type:** SonarQuery
**Required:** No
**Description:** The criteria for a Sonar query.
**JSON Example:**
```json
{
  "criteria": {
    "filters": [
      {
        "days": "",
        "domain": "acme.com",
        "lower": "",
        "type": "domain-contains",
        "upper": ""
      }
    ]
  },
  "id": 14,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Assets in Domain"
}
```

## Responses

### 200
**Description:** OK
**Schema:** `CreatedReference«DiscoveryQueryID,Link»`
**Example JSON Response:**
```json
{
  "id": 1,
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

## 6. Sonar Query Search

# Sonar Query Search

**Endpoint:** `POST /api/3/sonar_queries/search`

## Description
Executes a Sonar query to discover assets with the given search criteria.

**Operation ID:** `sonarQuerySearch`

## Parameters

### Parameter 1
**Name:** `query`
**Location:** body
**Type:** SonarCriteria
**Required:** No
**Description:** The criteria for a Sonar query.
**JSON Example:**
```json
{
  "filters": [
    {
      "days": "",
      "domain": "acme.com",
      "lower": "",
      "type": "domain-contains",
      "upper": ""
    }
  ]
}
```

## Request Body
**Name:** `query`
**Location:** body
**Type:** SonarCriteria
**Required:** No
**Description:** The criteria for a Sonar query.
**JSON Example:**
```json
{
  "filters": [
    {
      "days": "",
      "domain": "acme.com",
      "lower": "",
      "type": "domain-contains",
      "upper": ""
    }
  ]
}
```

## Responses

### 200
**Description:** OK
**Example JSON Response:**
```json
[
  {
    "address": "12.83.99.203",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "desktop-27.acme.com"
  }
]
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

## 7. Sonar Query

# Sonar Query

**Endpoint:** `GET /api/3/sonar_queries/{id}`

## Description
Returns a sonar query.

**Operation ID:** `getSonarQuery`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the Sonar query.

## Responses

### 200
**Description:** OK
**Schema:** `SonarQuery`
**Example JSON Response:**
```json
{
  "criteria": {
    "filters": [
      {
        "days": "",
        "domain": "acme.com",
        "lower": "",
        "type": "domain-contains",
        "upper": ""
      }
    ]
  },
  "id": 14,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Assets in Domain"
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

## 8. Sonar Query

# Sonar Query

**Endpoint:** `PUT /api/3/sonar_queries/{id}`

## Description
Updates a sonar query.

**Operation ID:** `updateSonarQuery`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the Sonar query.

### Parameter 2
**Name:** `query`
**Location:** body
**Type:** SonarQuery
**Required:** No
**Description:** The criteria for a Sonar query.
**JSON Example:**
```json
{
  "criteria": {
    "filters": [
      {
        "days": "",
        "domain": "acme.com",
        "lower": "",
        "type": "domain-contains",
        "upper": ""
      }
    ]
  },
  "id": 14,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Assets in Domain"
}
```

## Request Body
**Name:** `query`
**Location:** body
**Type:** SonarQuery
**Required:** No
**Description:** The criteria for a Sonar query.
**JSON Example:**
```json
{
  "criteria": {
    "filters": [
      {
        "days": "",
        "domain": "acme.com",
        "lower": "",
        "type": "domain-contains",
        "upper": ""
      }
    ]
  },
  "id": 14,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Assets in Domain"
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

## 9. Sonar Query

# Sonar Query

**Endpoint:** `DELETE /api/3/sonar_queries/{id}`

## Description
Removes a sonar query.

**Operation ID:** `deleteSonarQuery`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the Sonar query.

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

## 10. Sonar Query Assets

# Sonar Query Assets

**Endpoint:** `GET /api/3/sonar_queries/{id}/assets`

## Description
Returns the assets that are discovered by a Sonar query.

**Operation ID:** `getSonarQueryAssets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the Sonar query.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«DiscoveryAsset»`
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
      "address": "12.83.99.203",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "desktop-27.acme.com"
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
