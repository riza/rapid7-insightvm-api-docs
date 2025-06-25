# Asset Group Endpoints

## Description
Resources and operations for managing asset groups.

This document contains 22 endpoints under the Asset Group tag.

---

## 1. Agents

# Agents

**Endpoint:** `GET /api/3/agents`

## Description
Returns the details for all agents.

**Operation ID:** `getAgents`

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
**Schema:** `PageOf«Agent»`
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
      "addresses": [
        {
          "ip": "123.245.34.235",
          "mac": "12:34:56:78:90:AB"
        }
      ],
      "agentId": "fe1708451f8c78c3a20a8a79818878e1",
      "assessedForPolicies": false,
      "assessedForVulnerabilities": true,
      "configurations": [
        {
          "name": "<name>",
          "value": "<value>"
        }
      ],
      "databases": [
        {
          "description": "Microsoft SQL Server",
          "id": 13,
          "name": "MSSQL"
        }
      ],
      "files": [
        {
          "attributes": [
            {
              "name": "<name>",
              "value": "<value>"
            }
          ],
          "name": "ADMIN$",
          "size": -1,
          "type": "directory"
        }
      ],
      "history": [
        {
          "date": "2018-04-09T06:23:49Z",
          "description": "",
          "scanId": 12,
          "type": "SCAN",
          "user": "",
          "version": 8,
          "vulnerabilityExceptionId": ""
        }
      ],
      "hostName": "corporate-workstation-1102DC.acme.com",
      "hostNames": [
        {
          "name": "corporate-workstation-1102DC.acme.com",
          "source": "DNS"
        }
      ],
      "id": 282,
      "ids": [
        {
          "id": "c56b2c59-4e9b-4b89-85e2-13f8146eb071",
          "source": "WQL"
        }
      ],
      "ip": "182.34.74.202",
      "lastAssessedForVulnerabilities": "2019-09-11T10:39:51.288Z",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "mac": "AB:12:CD:34:EF:56",
      "os": "Microsoft Windows Server 2008 Enterprise Edition SP1",
      "osCertainty": "0.75",
      "osFingerprint": {
        "architecture": "x86",
        "configurations": [
          {
            "name": "<name>",
            "value": "<value>"
          }
        ],
        "cpe": {
          "edition": "enterprise",
          "language": "",
          "other": "",
          "part": "o",
          "product": "windows_server_2008",
          "swEdition": "",
          "targetHW": "",
          "targetSW": "",
          "update": "sp1",
          "v2.2": "cpe:/o:microsoft:windows_server_2008:-:sp1:enterprise",
          "v2.3": "cpe:2.3:o:microsoft:windows_server_2008:-:sp1:enterprise:*:*:*:*:*",
          "vendor": "microsoft",
          "version": "-"
        },
        "description": "Microsoft Windows Server 2008 Enterprise Edition SP1",
        "family": "Windows",
        "id": 35,
        "product": "Windows Server 2008 Enterprise Edition",
        "systemName": "Microsoft Windows",
        "type": "Workstation",
        "vendor": "Microsoft",
        "version": "SP1"
      },
      "rawRiskScore": 31214.3,
      "riskScore": 37457.16,
      "services": [
        {
          "configurations": [
            {
              "name": "<name>",
              "value": "<value>"
            }
          ],
          "databases": [
            {
              "description": "Microsoft SQL Server",
              "id": 13,
              "name": "MSSQL"
            }
          ],
          "family": "",
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ],
          "name": "CIFS Name Service",
          "port": 139,
          "product": "Samba",
          "protocol": "tcp",
          "userGroups": [
            {
              "id": 972,
              "name": "Administrators"
            }
          ],
          "users": [
            {
              "fullName": "Smith, John",
              "id": 8952,
              "name": "john_smith"
            }
          ],
          "vendor": "",
          "version": "3.5.11",
          "webApplications": [
            {
              "id": 30712,
              "pages": [
                {
                  "linkType": "html-ref",
                  "path": "/docs/config/index.html",
                  "response": 200
                }
              ],
              "root": "/",
              "virtualHost": "102.89.22.253"
            }
          ]
        }
      ],
      "software": [
        {
          "configurations": [
            {
              "name": "<name>",
              "value": "<value>"
            }
          ],
          "cpe": {
            "edition": "enterprise",
            "language": "",
            "other": "",
            "part": "o",
            "product": "windows_server_2008",
            "swEdition": "",
            "targetHW": "",
            "targetSW": "",
            "update": "sp1",
            "v2.2": "cpe:/o:microsoft:windows_server_2008:-:sp1:enterprise",
            "v2.3": "cpe:2.3:o:microsoft:windows_server_2008:-:sp1:enterprise:*:*:*:*:*",
            "vendor": "microsoft",
            "version": "-"
          },
          "description": "Microsoft Outlook 2013 15.0.4867.1000",
          "family": "Office 2013",
          "id": 42,
          "product": "Outlook 2013",
          "type": "Productivity",
          "vendor": "Microsoft",
          "version": "15.0.4867.1000"
        }
      ],
      "type": "",
      "userGroups": [
        {
          "id": 972,
          "name": "Administrators"
        }
      ],
      "users": [
        {
          "fullName": "Smith, John",
          "id": 8952,
          "name": "john_smith"
        }
      ],
      "vulnerabilities": {
        "critical": 16,
        "exploits": 4,
        "malwareKits": 0,
        "moderate": 3,
        "severe": 76,
        "total": 95
      }
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

## 2. Asset Groups

# Asset Groups

**Endpoint:** `GET /api/3/asset_groups`

## Description
Returns all asset groups.

**Operation ID:** `getAssetGroups`

## Parameters

### Parameter 1
**Name:** `type`
**Location:** query
**Type:** string
**Required:** No
**Description:** The type of asset group.

### Parameter 2
**Name:** `name`
**Location:** query
**Type:** string
**Required:** No
**Description:** A search pattern for the name of the asset group. Searches are case-insensitive contains.

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
**Schema:** `PageOf«AssetGroup»`
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
      "assets": 768,
      "description": "Assets with unacceptable high risk required immediate remediation.",
      "id": 61,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "High Risk Assets",
      "riskScore": 4457823.78,
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
      "type": "dynamic",
      "vulnerabilities": {
        "critical": 16,
        "moderate": 3,
        "severe": 76,
        "total": 95
      }
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

## 3. Asset Groups

# Asset Groups

**Endpoint:** `POST /api/3/asset_groups`

## Description
Creates a new asset group. The `searchCriteria` field can be passed no matter what the type of the asset group is. The asset group `type` changes when the assets are refreshed. Dynamic asset groups constantly refreshed their membership as assets are scanned whereas static asset groups do not change membership automatically. See the Search Criteria for more information on using dynamic criteria.

**Operation ID:** `createAssetGroup`

## Parameters

### Parameter 1
**Name:** `assetGroup`
**Location:** body
**Type:** AssetGroup
**Required:** No
**Description:** The details of the asset group.
**JSON Example:**
```json
{
  "assets": 768,
  "description": "Assets with unacceptable high risk required immediate remediation.",
  "id": 61,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "High Risk Assets",
  "riskScore": 4457823.78,
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
  "type": "dynamic",
  "vulnerabilities": {
    "critical": 16,
    "moderate": 3,
    "severe": 76,
    "total": 95
  }
}
```

## Request Body
**Name:** `assetGroup`
**Location:** body
**Type:** AssetGroup
**Required:** No
**Description:** The details of the asset group.
**JSON Example:**
```json
{
  "assets": 768,
  "description": "Assets with unacceptable high risk required immediate remediation.",
  "id": 61,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "High Risk Assets",
  "riskScore": 4457823.78,
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
  "type": "dynamic",
  "vulnerabilities": {
    "critical": 16,
    "moderate": 3,
    "severe": 76,
    "total": 95
  }
}
```

## Responses

### 201
**Description:** Created
**Schema:** `CreatedReference«AssetGroupID,Link»`
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

## 4. Asset Group

# Asset Group

**Endpoint:** `GET /api/3/asset_groups/{id}`

## Description
Returns an asset group.

**Operation ID:** `getAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

## Responses

### 200
**Description:** OK
**Schema:** `AssetGroup`
**Example JSON Response:**
```json
{
  "assets": 768,
  "description": "Assets with unacceptable high risk required immediate remediation.",
  "id": 61,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "High Risk Assets",
  "riskScore": 4457823.78,
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
  "type": "dynamic",
  "vulnerabilities": {
    "critical": 16,
    "moderate": 3,
    "severe": 76,
    "total": 95
  }
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

## 5. Asset Group

# Asset Group

**Endpoint:** `PUT /api/3/asset_groups/{id}`

## Description
Updates the details of an asset group. See the search criteria endpoint (/search_criteria) for more information about building the search criteria and examples.

**Operation ID:** `updateAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `assetGroup`
**Location:** body
**Type:** AssetGroup
**Required:** No
**Description:** The details of the asset group.
**JSON Example:**
```json
{
  "assets": 768,
  "description": "Assets with unacceptable high risk required immediate remediation.",
  "id": 61,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "High Risk Assets",
  "riskScore": 4457823.78,
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
  "type": "dynamic",
  "vulnerabilities": {
    "critical": 16,
    "moderate": 3,
    "severe": 76,
    "total": 95
  }
}
```

## Request Body
**Name:** `assetGroup`
**Location:** body
**Type:** AssetGroup
**Required:** No
**Description:** The details of the asset group.
**JSON Example:**
```json
{
  "assets": 768,
  "description": "Assets with unacceptable high risk required immediate remediation.",
  "id": 61,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "High Risk Assets",
  "riskScore": 4457823.78,
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
  "type": "dynamic",
  "vulnerabilities": {
    "critical": 16,
    "moderate": 3,
    "severe": 76,
    "total": 95
  }
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

## 6. Asset Group

# Asset Group

**Endpoint:** `DELETE /api/3/asset_groups/{id}`

## Description
Deletes the asset group.

**Operation ID:** `deleteAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

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

## 7. Asset Group Assets

# Asset Group Assets

**Endpoint:** `GET /api/3/asset_groups/{id}/assets`

## Description
Returns hypermedia links for the assets that belong to an asset group.

**Operation ID:** `getAssetGroupAssets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«AssetID,Link»`
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

## 8. Asset Group Assets

# Asset Group Assets

**Endpoint:** `PUT /api/3/asset_groups/{id}/assets`

## Description
Updates all the assets that belong to a static asset group.

**Operation ID:** `updateAssetGroupAssets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `assets`
**Location:** body
**Type:** array
**Required:** No
**Description:** The assets to place in the asset group.
**JSON Example:**
```json
[
  42
]
```

## Request Body
**Name:** `assets`
**Location:** body
**Type:** array
**Required:** No
**Description:** The assets to place in the asset group.
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

## 9. Asset Group Assets

# Asset Group Assets

**Endpoint:** `DELETE /api/3/asset_groups/{id}/assets`

## Description
Removes the assets from the given static asset group.

**Operation ID:** `removeAllAssetsFromAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

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

## 10. Asset Group Asset

# Asset Group Asset

**Endpoint:** `PUT /api/3/asset_groups/{id}/assets/{assetId}`

## Description
Adds an asset to a static asset group.

**Operation ID:** `addAssetToAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

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

## 11. Asset Group Asset

# Asset Group Asset

**Endpoint:** `DELETE /api/3/asset_groups/{id}/assets/{assetId}`

## Description
Removes an asset from an asset group.

**Operation ID:** `removeAssetFromAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

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

## 12. Asset Group Search Criteria

# Asset Group Search Criteria

**Endpoint:** `GET /api/3/asset_groups/{id}/search_criteria`

## Description
Returns the search criteria of a dynamic asset group.For a reference of valid search criteria input see the Asset Search resource.

**Operation ID:** `getAssetGroupSearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

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

## 13. Asset Group Search Criteria

# Asset Group Search Criteria

**Endpoint:** `PUT /api/3/asset_groups/{id}/search_criteria`

## Description
Updates the search criteria of a dynamic asset group. For a reference of valid search criteria input see the Asset Search resource.

**Operation ID:** `setAssetGroupSearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `criteria`
**Location:** body
**Type:** SearchCriteria
**Required:** No
**Description:** The search criteria specification.
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
**Name:** `criteria`
**Location:** body
**Type:** SearchCriteria
**Required:** No
**Description:** The search criteria specification.
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

## 14. Asset Group Tags

# Asset Group Tags

**Endpoint:** `GET /api/3/asset_groups/{id}/tags`

## Description
Returns the tags assigned to an asset group.

**Operation ID:** `getAssetGroupTags`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«TagID,Link»`
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

## 15. Asset Group Tags

# Asset Group Tags

**Endpoint:** `PUT /api/3/asset_groups/{id}/tags`

## Description
Updates the tags of an asset group.

**Operation ID:** `setAssetGroupTags`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `tags`
**Location:** body
**Type:** array
**Required:** No
**Description:** The tags to associate to the asset group.
**JSON Example:**
```json
[
  42
]
```

## Request Body
**Name:** `tags`
**Location:** body
**Type:** array
**Required:** No
**Description:** The tags to associate to the asset group.
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

## 16. Asset Group Tags

# Asset Group Tags

**Endpoint:** `DELETE /api/3/asset_groups/{id}/tags`

## Description
Removes all tag associations from the asset group.

**Operation ID:** `removeAllAssetGroupTags`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

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

## 17. Resources and operations for managing asset groups.

# Resources and operations for managing asset groups.

**Endpoint:** `PUT /api/3/asset_groups/{id}/tags/{tagId}`

## Description
Adds a tag to an asset group.

**Operation ID:** `addAssetGroupTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `tagId`
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

## 18. Resources and operations for managing asset groups.

# Resources and operations for managing asset groups.

**Endpoint:** `DELETE /api/3/asset_groups/{id}/tags/{tagId}`

## Description
Removes a tag from an asset group.

**Operation ID:** `removeAssetGroupTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `tagId`
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

## 19. Asset Group Users

# Asset Group Users

**Endpoint:** `GET /api/3/asset_groups/{id}/users`

## Description
Returns hypermedia links for the users with access to this asset group.

**Operation ID:** `getAssetGroupUsers`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«UserID,Link»`
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

## 20. Asset Group Users

# Asset Group Users

**Endpoint:** `PUT /api/3/asset_groups/{id}/users`

## Description
Grants users with sufficient privileges access to an asset group.

**Operation ID:** `setAssetGroupUsers`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `users`
**Location:** body
**Type:** array
**Required:** No
**Description:** The users to grant access to the asset group.
**JSON Example:**
```json
[
  42
]
```

## Request Body
**Name:** `users`
**Location:** body
**Type:** array
**Required:** No
**Description:** The users to grant access to the asset group.
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

## 21. Asset Group User

# Asset Group User

**Endpoint:** `PUT /api/3/asset_groups/{id}/users/{userId}`

## Description
Grants a user with sufficient privileges access to the asset group.

**Operation ID:** `addAssetGroupUser`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `userId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the user.

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

## 22. Asset Group User

# Asset Group User

**Endpoint:** `DELETE /api/3/asset_groups/{id}/users/{userId}`

## Description
Removes a user's access from an asset group.

**Operation ID:** `removeAssetGroupUser`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset group.

### Parameter 2
**Name:** `userId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the user.

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
