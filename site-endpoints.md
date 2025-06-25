# Site Endpoints

## Description
Resources and operations for managing sites.

This document contains 84 endpoints under the Site tag.

---

## 1. Site Assets

# Site Assets

**Endpoint:** `GET /api/3/sites/{id}/assets`

## Description
Retrieves a paged resource of assets linked with the specified site.

**Operation ID:** `getSiteAssets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `page`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The index of the page (zero-based) to retrieve.

### Parameter 3
**Name:** `size`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The number of records per page to retrieve.

### Parameter 4
**Name:** `sort`
**Location:** query
**Type:** array
**Required:** No
**Description:** The criteria to sort the records by, in the format: `property[,ASC|DESC]`. The default sort order is ascending. Multiple sort criteria can be specified using multiple sort query parameters.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«Asset»`
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

## 2. Site Assets

# Site Assets

**Endpoint:** `DELETE /api/3/sites/{id}/assets`

## Description
Removes all assets from the specified site. Assets will be deleted entirely from the Security Console if either Asset Linking is disabled or if Asset Linking is enabled and the asset only existed in this site.

**Operation ID:** `removeSiteAssets`

## Parameters

### Parameter 1
**Name:** `id`
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

## 3. Sites

# Sites

**Endpoint:** `GET /api/3/sites`

## Description
Retrieves a paged resource of accessible sites.

**Operation ID:** `getSites`

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
**Schema:** `PageOf«Site»`
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
      "connectionType": "",
      "description": "",
      "id": "",
      "importance": "",
      "lastScanTime": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "riskScore": 4457823.78,
      "scanEngine": "",
      "scanTemplate": "",
      "type": "",
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

## 4. Sites

# Sites

**Endpoint:** `POST /api/3/sites`

## Description
Creates a new site with the specified configuration.

**Operation ID:** `createSite`

## Parameters

### Parameter 1
**Name:** `site`
**Location:** body
**Type:** SiteCreateResource
**Required:** No
**Description:** Resource for creating a site configuration.
**JSON Example:**
```json
{
  "description": "",
  "engineId": "",
  "importance": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "scan": {
    "assets": {
      "excludedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "excludedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      }
    },
    "connection": {
      "id": ""
    }
  },
  "scanTemplateId": ""
}
```

## Request Body
**Name:** `site`
**Location:** body
**Type:** SiteCreateResource
**Required:** No
**Description:** Resource for creating a site configuration.
**JSON Example:**
```json
{
  "description": "",
  "engineId": "",
  "importance": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "scan": {
    "assets": {
      "excludedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "excludedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      }
    },
    "connection": {
      "id": ""
    }
  },
  "scanTemplateId": ""
}
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«SiteID,Link»`
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

## 5. Site

# Site

**Endpoint:** `GET /api/3/sites/{id}`

## Description
Retrieves the site with the specified identifier.

**Operation ID:** `getSite`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Site`
**Example JSON Response:**
```json
{
  "assets": 768,
  "connectionType": "",
  "description": "",
  "id": "",
  "importance": "",
  "lastScanTime": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "riskScore": 4457823.78,
  "scanEngine": "",
  "scanTemplate": "",
  "type": "",
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

## 6. Site

# Site

**Endpoint:** `PUT /api/3/sites/{id}`

## Description
Updates the configuration of the site with the specified identifier.

**Operation ID:** `updateSite`

## Parameters

### Parameter 1
**Name:** `site`
**Location:** body
**Type:** SiteUpdateResource
**Required:** No
**Description:** Resource for updating a site configuration.
**JSON Example:**
```json
{
  "description": "",
  "engineId": "",
  "importance": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "scanTemplateId": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `site`
**Location:** body
**Type:** SiteUpdateResource
**Required:** No
**Description:** Resource for updating a site configuration.
**JSON Example:**
```json
{
  "description": "",
  "engineId": "",
  "importance": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "scanTemplateId": ""
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

## 7. Site

# Site

**Endpoint:** `DELETE /api/3/sites/{id}`

## Description
Deletes the site with the specified identifier.

**Operation ID:** `deleteSite`

## Parameters

### Parameter 1
**Name:** `id`
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

## 8. Site Alerts

# Site Alerts

**Endpoint:** `GET /api/3/sites/{id}/alerts`

## Description
Retrieve all alerts defined in the site.

**Operation ID:** `getSiteAlerts`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«Alert»`
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
      "enabled": false,
      "enabledScanEvents": {
        "failed": false,
        "paused": false,
        "resumed": false,
        "started": false,
        "stopped": false
      },
      "enabledVulnerabilityEvents": {
        "confirmedVulnerabilities": false,
        "potentialVulnerabilities": false,
        "unconfirmedVulnerabilities": false,
        "vulnerabilitySeverity": ""
      },
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "maximumAlerts": "",
      "name": "",
      "notification": ""
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

## 9. Site Alerts

# Site Alerts

**Endpoint:** `DELETE /api/3/sites/{id}/alerts`

## Description
Deletes all alerts from the site.

**Operation ID:** `deleteAllSiteAlerts`

## Parameters

### Parameter 1
**Name:** `id`
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

## 10. Site SMTP Alerts

# Site SMTP Alerts

**Endpoint:** `GET /api/3/sites/{id}/alerts/smtp`

## Description
Retrieves all SMTP alerts defined in the site.

**Operation ID:** `getSiteSmtpAlerts`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SmtpAlert»`
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
      "enabled": false,
      "enabledScanEvents": {
        "failed": false,
        "paused": false,
        "resumed": false,
        "started": false,
        "stopped": false
      },
      "enabledVulnerabilityEvents": {
        "confirmedVulnerabilities": false,
        "potentialVulnerabilities": false,
        "unconfirmedVulnerabilities": false,
        "vulnerabilitySeverity": ""
      },
      "id": "",
      "limitAlertText": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "maximumAlerts": "",
      "name": "",
      "notification": "",
      "recipients": [
        "string"
      ],
      "relayServer": "",
      "senderEmailAddress": ""
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

## 11. Site SMTP Alerts

# Site SMTP Alerts

**Endpoint:** `POST /api/3/sites/{id}/alerts/smtp`

## Description
Creates a new SMTP alert for the specified site.

**Operation ID:** `createSiteSmtpAlert`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** SmtpAlert
**Required:** No
**Description:** Resource for creating a new SMTP alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "limitAlertText": false,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "recipients": [
    "string"
  ],
  "relayServer": "",
  "senderEmailAddress": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** SmtpAlert
**Required:** No
**Description:** Resource for creating a new SMTP alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "limitAlertText": false,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "recipients": [
    "string"
  ],
  "relayServer": "",
  "senderEmailAddress": ""
}
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«AlertID,Link»`
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

## 12. Site SMTP Alerts

# Site SMTP Alerts

**Endpoint:** `PUT /api/3/sites/{id}/alerts/smtp`

## Description
Updates all SMTP alerts for the specified site in a single request using the array of resources defined in the request body.

**Operation ID:** `setSiteSmtpAlerts`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all SMTP alerts defined in the site. Alerts defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "enabled": false,
    "enabledScanEvents": {
      "failed": false,
      "paused": false,
      "resumed": false,
      "started": false,
      "stopped": false
    },
    "enabledVulnerabilityEvents": {
      "confirmedVulnerabilities": false,
      "potentialVulnerabilities": false,
      "unconfirmedVulnerabilities": false,
      "vulnerabilitySeverity": ""
    },
    "id": "",
    "limitAlertText": false,
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "maximumAlerts": "",
    "name": "",
    "notification": "",
    "recipients": [
      "string"
    ],
    "relayServer": "",
    "senderEmailAddress": ""
  }
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all SMTP alerts defined in the site. Alerts defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "enabled": false,
    "enabledScanEvents": {
      "failed": false,
      "paused": false,
      "resumed": false,
      "started": false,
      "stopped": false
    },
    "enabledVulnerabilityEvents": {
      "confirmedVulnerabilities": false,
      "potentialVulnerabilities": false,
      "unconfirmedVulnerabilities": false,
      "vulnerabilitySeverity": ""
    },
    "id": "",
    "limitAlertText": false,
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "maximumAlerts": "",
    "name": "",
    "notification": "",
    "recipients": [
      "string"
    ],
    "relayServer": "",
    "senderEmailAddress": ""
  }
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

## 13. Site SMTP Alerts

# Site SMTP Alerts

**Endpoint:** `DELETE /api/3/sites/{id}/alerts/smtp`

## Description
Deletes all SMTP alerts from the site.

**Operation ID:** `deleteAllSiteSmtpAlerts`

## Parameters

### Parameter 1
**Name:** `id`
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

## 14. Site SMTP Alert

# Site SMTP Alert

**Endpoint:** `GET /api/3/sites/{id}/alerts/smtp/{alertId}`

## Description
Retrieves the specified SMTP alert.

**Operation ID:** `getSiteSmtpAlert`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

## Responses

### 200
**Description:** OK
**Schema:** `SmtpAlert`
**Example JSON Response:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "limitAlertText": false,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "recipients": [
    "string"
  ],
  "relayServer": "",
  "senderEmailAddress": ""
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

## 15. Site SMTP Alert

# Site SMTP Alert

**Endpoint:** `PUT /api/3/sites/{id}/alerts/smtp/{alertId}`

## Description
Updates the specified SMTP alert.

**Operation ID:** `updateSiteSmtpAlert`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** SmtpAlert
**Required:** No
**Description:** Resource for updating the specified SMTP alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "limitAlertText": false,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "recipients": [
    "string"
  ],
  "relayServer": "",
  "senderEmailAddress": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 3
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** SmtpAlert
**Required:** No
**Description:** Resource for updating the specified SMTP alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "limitAlertText": false,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "recipients": [
    "string"
  ],
  "relayServer": "",
  "senderEmailAddress": ""
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

## 16. Site SMTP Alert

# Site SMTP Alert

**Endpoint:** `DELETE /api/3/sites/{id}/alerts/smtp/{alertId}`

## Description
Deletes the specified SMTP alert from the site.

**Operation ID:** `deleteSiteSmtpAlert`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

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

## 17. Site SNMP Alerts

# Site SNMP Alerts

**Endpoint:** `GET /api/3/sites/{id}/alerts/snmp`

## Description
Retrieves all SNMP alerts defined in the site.

**Operation ID:** `getSiteSnmpAlerts`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SnmpAlert»`
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
      "community": "",
      "enabled": false,
      "enabledScanEvents": {
        "failed": false,
        "paused": false,
        "resumed": false,
        "started": false,
        "stopped": false
      },
      "enabledVulnerabilityEvents": {
        "confirmedVulnerabilities": false,
        "potentialVulnerabilities": false,
        "unconfirmedVulnerabilities": false,
        "vulnerabilitySeverity": ""
      },
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "maximumAlerts": "",
      "name": "",
      "notification": "",
      "server": ""
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

## 18. Site SNMP Alerts

# Site SNMP Alerts

**Endpoint:** `POST /api/3/sites/{id}/alerts/snmp`

## Description
Creates a new SNMP alert for the specified site.

**Operation ID:** `createSiteSnmpAlert`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** SnmpAlert
**Required:** No
**Description:** Resource for creating a new SNMP alert.
**JSON Example:**
```json
{
  "community": "",
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** SnmpAlert
**Required:** No
**Description:** Resource for creating a new SNMP alert.
**JSON Example:**
```json
{
  "community": "",
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
}
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«AlertID,Link»`
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

## 19. Site SNMP Alerts

# Site SNMP Alerts

**Endpoint:** `PUT /api/3/sites/{id}/alerts/snmp`

## Description
Updates all SNMP alerts for the specified site in a single request using the array of resources defined in the request body.

**Operation ID:** `setSiteSnmpAlerts`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all SNMP alerts defined in the site. Alerts defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "community": "",
    "enabled": false,
    "enabledScanEvents": {
      "failed": false,
      "paused": false,
      "resumed": false,
      "started": false,
      "stopped": false
    },
    "enabledVulnerabilityEvents": {
      "confirmedVulnerabilities": false,
      "potentialVulnerabilities": false,
      "unconfirmedVulnerabilities": false,
      "vulnerabilitySeverity": ""
    },
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "maximumAlerts": "",
    "name": "",
    "notification": "",
    "server": ""
  }
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all SNMP alerts defined in the site. Alerts defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "community": "",
    "enabled": false,
    "enabledScanEvents": {
      "failed": false,
      "paused": false,
      "resumed": false,
      "started": false,
      "stopped": false
    },
    "enabledVulnerabilityEvents": {
      "confirmedVulnerabilities": false,
      "potentialVulnerabilities": false,
      "unconfirmedVulnerabilities": false,
      "vulnerabilitySeverity": ""
    },
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "maximumAlerts": "",
    "name": "",
    "notification": "",
    "server": ""
  }
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

## 20. Site SNMP Alerts

# Site SNMP Alerts

**Endpoint:** `DELETE /api/3/sites/{id}/alerts/snmp`

## Description
Deletes all SNMP alerts from the site.

**Operation ID:** `deleteAllSiteSnmpAlerts`

## Parameters

### Parameter 1
**Name:** `id`
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

## 21. Site SNMP Alert

# Site SNMP Alert

**Endpoint:** `GET /api/3/sites/{id}/alerts/snmp/{alertId}`

## Description
Retrieves the specified SNMP alert.

**Operation ID:** `getSiteSnmpAlert`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

## Responses

### 200
**Description:** OK
**Schema:** `SnmpAlert`
**Example JSON Response:**
```json
{
  "community": "",
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
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

## 22. Site SNMP Alert

# Site SNMP Alert

**Endpoint:** `PUT /api/3/sites/{id}/alerts/snmp/{alertId}`

## Description
Updates the specified SNMP alert.

**Operation ID:** `updateSiteSnmpAlert`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** SnmpAlert
**Required:** No
**Description:** Resource for updating the specified SNMP alert.
**JSON Example:**
```json
{
  "community": "",
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 3
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** SnmpAlert
**Required:** No
**Description:** Resource for updating the specified SNMP alert.
**JSON Example:**
```json
{
  "community": "",
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
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

## 23. Site SNMP Alert

# Site SNMP Alert

**Endpoint:** `DELETE /api/3/sites/{id}/alerts/snmp/{alertId}`

## Description
Deletes the specified SNMP alert from the site.

**Operation ID:** `deleteSiteSnmpAlert`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

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

## 24. Site Syslog Alerts

# Site Syslog Alerts

**Endpoint:** `GET /api/3/sites/{id}/alerts/syslog`

## Description
Retrieves all Syslog alerts defined in the site.

**Operation ID:** `getSiteSyslogAlerts`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SyslogAlert»`
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
      "enabled": false,
      "enabledScanEvents": {
        "failed": false,
        "paused": false,
        "resumed": false,
        "started": false,
        "stopped": false
      },
      "enabledVulnerabilityEvents": {
        "confirmedVulnerabilities": false,
        "potentialVulnerabilities": false,
        "unconfirmedVulnerabilities": false,
        "vulnerabilitySeverity": ""
      },
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "maximumAlerts": "",
      "name": "",
      "notification": "",
      "server": ""
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

## 25. Site Syslog Alerts

# Site Syslog Alerts

**Endpoint:** `POST /api/3/sites/{id}/alerts/syslog`

## Description
Creates a new Syslog alert for the specified site.

**Operation ID:** `createSiteSyslogAlert`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** SyslogAlert
**Required:** No
**Description:** Resource for creating a new Syslog alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** SyslogAlert
**Required:** No
**Description:** Resource for creating a new Syslog alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
}
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«AlertID,Link»`
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

## 26. Site Syslog Alerts

# Site Syslog Alerts

**Endpoint:** `PUT /api/3/sites/{id}/alerts/syslog`

## Description
Updates all Syslog alerts for the specified site in a single request using the array of resources defined in the request body.

**Operation ID:** `setSiteSyslogAlerts`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all Syslog alerts defined in the site. Alerts defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "enabled": false,
    "enabledScanEvents": {
      "failed": false,
      "paused": false,
      "resumed": false,
      "started": false,
      "stopped": false
    },
    "enabledVulnerabilityEvents": {
      "confirmedVulnerabilities": false,
      "potentialVulnerabilities": false,
      "unconfirmedVulnerabilities": false,
      "vulnerabilitySeverity": ""
    },
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "maximumAlerts": "",
    "name": "",
    "notification": "",
    "server": ""
  }
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all Syslog alerts defined in the site. Alerts defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "enabled": false,
    "enabledScanEvents": {
      "failed": false,
      "paused": false,
      "resumed": false,
      "started": false,
      "stopped": false
    },
    "enabledVulnerabilityEvents": {
      "confirmedVulnerabilities": false,
      "potentialVulnerabilities": false,
      "unconfirmedVulnerabilities": false,
      "vulnerabilitySeverity": ""
    },
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "maximumAlerts": "",
    "name": "",
    "notification": "",
    "server": ""
  }
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

## 27. Site Syslog Alerts

# Site Syslog Alerts

**Endpoint:** `DELETE /api/3/sites/{id}/alerts/syslog`

## Description
Deletes all Syslog alerts from the site.

**Operation ID:** `deleteAllSiteSyslogAlerts`

## Parameters

### Parameter 1
**Name:** `id`
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

## 28. Site Syslog Alert

# Site Syslog Alert

**Endpoint:** `GET /api/3/sites/{id}/alerts/syslog/{alertId}`

## Description
Retrieves the specified Syslog alert.

**Operation ID:** `getSiteSyslogAlert`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

## Responses

### 200
**Description:** OK
**Schema:** `SyslogAlert`
**Example JSON Response:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
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

## 29. Site Syslog Alert

# Site Syslog Alert

**Endpoint:** `PUT /api/3/sites/{id}/alerts/syslog/{alertId}`

## Description
Updates the specified Syslog alert.

**Operation ID:** `updateSiteSyslogAlert`

## Parameters

### Parameter 1
**Name:** `alert`
**Location:** body
**Type:** SyslogAlert
**Required:** No
**Description:** Resource for updating the specified Syslog alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 3
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

## Request Body
**Name:** `alert`
**Location:** body
**Type:** SyslogAlert
**Required:** No
**Description:** Resource for updating the specified Syslog alert.
**JSON Example:**
```json
{
  "enabled": false,
  "enabledScanEvents": {
    "failed": false,
    "paused": false,
    "resumed": false,
    "started": false,
    "stopped": false
  },
  "enabledVulnerabilityEvents": {
    "confirmedVulnerabilities": false,
    "potentialVulnerabilities": false,
    "unconfirmedVulnerabilities": false,
    "vulnerabilitySeverity": ""
  },
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maximumAlerts": "",
  "name": "",
  "notification": "",
  "server": ""
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

## 30. Site Syslog Alert

# Site Syslog Alert

**Endpoint:** `DELETE /api/3/sites/{id}/alerts/syslog/{alertId}`

## Description
Deletes the specified Syslog alert from the site.

**Operation ID:** `deleteSiteSyslogAlert`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `alertId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the alert.

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

## 31. Site Asset

# Site Asset

**Endpoint:** `DELETE /api/3/sites/{id}/assets/{assetId}`

## Description
Removes an asset from a site. The asset will only be deleted if it belongs to no other sites.

**Operation ID:** `removeAssetFromSite`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

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

## 32. Site Discovery Connection

# Site Discovery Connection

**Endpoint:** `GET /api/3/sites/{id}/discovery_connection`

## Description
Retrieves the discovery connection assigned to the site.

**Operation ID:** `getSiteDiscoveryConnection`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `SiteDiscoveryConnection`
**Example JSON Response:**
```json
{
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "type": ""
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

## 33. Site Discovery Connection

# Site Discovery Connection

**Endpoint:** `PUT /api/3/sites/{id}/discovery_connection`

## Description
Updates the discovery connection assigned to the site.

**Operation ID:** `setSiteDiscoveryConnection`

## Parameters

### Parameter 1
**Name:** `connectionId`
**Location:** body
**Type:** integer
**Required:** No
**Description:** The identifier of the discovery connection.
**JSON Example:**
```json
42
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `connectionId`
**Location:** body
**Type:** integer
**Required:** No
**Description:** The identifier of the discovery connection.
**JSON Example:**
```json
42
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

## 34. Site Discovery Search Criteria

# Site Discovery Search Criteria

**Endpoint:** `GET /api/3/sites/{id}/discovery_search_criteria`

## Description
Retrieve the search criteria of the dynamic site.

**Operation ID:** `getSiteDiscoverySearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `DiscoverySearchCriteria`
**Example JSON Response:**
```json
{
  "connectionType": "",
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

## 35. Site Discovery Search Criteria

# Site Discovery Search Criteria

**Endpoint:** `PUT /api/3/sites/{id}/discovery_search_criteria`

## Description
Update the search criteria of the dynamic site.

**Operation ID:** `setSiteDiscoverySearchCriteria`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `param1`
**Location:** body
**Type:** DiscoverySearchCriteria
**Required:** Yes
**Description:** param1
**JSON Example:**
```json
{
  "connectionType": "",
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
**Name:** `param1`
**Location:** body
**Type:** DiscoverySearchCriteria
**Required:** Yes
**Description:** param1
**JSON Example:**
```json
{
  "connectionType": "",
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

## 36. Site Excluded Asset Groups

# Site Excluded Asset Groups

**Endpoint:** `GET /api/3/sites/{id}/excluded_asset_groups`

## Description
Retrieves the excluded asset groups in a static site.

**Operation ID:** `getExcludedAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«AssetGroup»`
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

## 37. Site Excluded Asset Groups

# Site Excluded Asset Groups

**Endpoint:** `PUT /api/3/sites/{id}/excluded_asset_groups`

## Description
Updates the excluded asset groups in a static site.

**Operation ID:** `updateExcludedAssetGroups`

## Parameters

### Parameter 1
**Name:** `assetGroupIds`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of asset group identifiers.
**JSON Example:**
```json
[
  42
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `assetGroupIds`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of asset group identifiers.
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

## 38. Site Excluded Asset Groups

# Site Excluded Asset Groups

**Endpoint:** `DELETE /api/3/sites/{id}/excluded_asset_groups`

## Description
Removes all excluded asset groups from the specified static site.

**Operation ID:** `removeAllExcludedAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
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

## 39. Site Excluded Asset Group

# Site Excluded Asset Group

**Endpoint:** `DELETE /api/3/sites/{id}/excluded_asset_groups/{assetGroupId}`

## Description
Removes the specified asset group from the excluded asset groups configured in the static site.

**Operation ID:** `removeExcludedAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `assetGroupId`
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

## 40. Site Excluded Targets

# Site Excluded Targets

**Endpoint:** `GET /api/3/sites/{id}/excluded_targets`

## Description
Retrieves the excluded targets in a static site.

**Operation ID:** `getExcludedTargets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `ScanTargetsResource`
**Example JSON Response:**
```json
{
  "addresses": [
    "string"
  ],
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

## 41. Site Excluded Targets

# Site Excluded Targets

**Endpoint:** `POST /api/3/sites/{id}/excluded_targets`

## Description
Adds one or more addresses to the site's list of excluded scan targets.

**Operation ID:** `addExcludedTargets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `scanTargetsToAdd`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to add to the site's excluded scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

## Request Body
**Name:** `scanTargetsToAdd`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to add to the site's excluded scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«SiteID,Link»`
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

## 42. Site Excluded Targets

# Site Excluded Targets

**Endpoint:** `PUT /api/3/sites/{id}/excluded_targets`

## Description
Updates the excluded targets in a static site.

**Operation ID:** `updateExcludedTargets`

## Parameters

### Parameter 1
**Name:** `scanTargets`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to be the site's new excluded scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `scanTargets`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to be the site's new excluded scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
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

## 43. Site Excluded Targets

# Site Excluded Targets

**Endpoint:** `DELETE /api/3/sites/{id}/excluded_targets`

## Description
Removes one or more addresses from the site's list of excluded scan targets.

**Operation ID:** `removeExcludedTargets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `scanTargetsToRemove`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of address to remove from the sites excluded scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

## Request Body
**Name:** `scanTargetsToRemove`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of address to remove from the sites excluded scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
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

## 44. Site Included Asset Groups

# Site Included Asset Groups

**Endpoint:** `GET /api/3/sites/{id}/included_asset_groups`

## Description
Retrieves the included asset groups in a static site.

**Operation ID:** `getIncludedAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«AssetGroup»`
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

## 45. Site Included Asset Groups

# Site Included Asset Groups

**Endpoint:** `PUT /api/3/sites/{id}/included_asset_groups`

## Description
Updates the included asset groups in a static site.

**Operation ID:** `updateIncludedAssetGroups`

## Parameters

### Parameter 1
**Name:** `assetGroupIds`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of asset group identifiers.
**JSON Example:**
```json
[
  42
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `assetGroupIds`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of asset group identifiers.
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

## 46. Site Included Asset Groups

# Site Included Asset Groups

**Endpoint:** `DELETE /api/3/sites/{id}/included_asset_groups`

## Description
Removes all included asset groups from the specified static site.

**Operation ID:** `removeAllIncludedAssetGroups`

## Parameters

### Parameter 1
**Name:** `id`
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

## 47. Site Included Asset Group

# Site Included Asset Group

**Endpoint:** `DELETE /api/3/sites/{id}/included_asset_groups/{assetGroupId}`

## Description
Removes the specified asset group from the included asset groups configured in the static site.

**Operation ID:** `removeIncludedAssetGroup`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `assetGroupId`
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

## 48. Site Included Targets

# Site Included Targets

**Endpoint:** `GET /api/3/sites/{id}/included_targets`

## Description
Retrieves the included targets in a static site.

**Operation ID:** `getIncludedTargets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `ScanTargetsResource`
**Example JSON Response:**
```json
{
  "addresses": [
    "string"
  ],
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

## 49. Site Included Targets

# Site Included Targets

**Endpoint:** `POST /api/3/sites/{id}/included_targets`

## Description
Adds one or more addresses to the site's list of included scan targets.

**Operation ID:** `addIncludedTargets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `scanTargetsToAdd`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to add to the site's included scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

## Request Body
**Name:** `scanTargetsToAdd`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to add to the site's included scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«SiteID,Link»`
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

## 50. Site Included Targets

# Site Included Targets

**Endpoint:** `PUT /api/3/sites/{id}/included_targets`

## Description
Updates the included targets in a static site.

**Operation ID:** `updateIncludedTargets`

## Parameters

### Parameter 1
**Name:** `scanTargets`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to be the site's new included scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `scanTargets`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of addresses to be the site's new included scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
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

## 51. Site Included Targets

# Site Included Targets

**Endpoint:** `DELETE /api/3/sites/{id}/included_targets`

## Description
Removes one or more addresses from the site's list of included scan targets.

**Operation ID:** `removeIncludedTargets`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `scanTargetsToRemove`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of address to remove from the sites included scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
]
```

## Request Body
**Name:** `scanTargetsToRemove`
**Location:** body
**Type:** array
**Required:** No
**Description:** List of address to remove from the sites included scan targets. Each address is a string that can represent either a hostname, ipv4 address, ipv4 address range, ipv6 address, or CIDR notation.
**JSON Example:**
```json
[
  "string"
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

## 52. Site Organization Information

# Site Organization Information

**Endpoint:** `GET /api/3/sites/{id}/organization`

## Description
Retrieves the site organization information.

**Operation ID:** `getSiteOrganization`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `SiteOrganization`
**Example JSON Response:**
```json
{
  "address": "",
  "city": "",
  "contact": "",
  "country": "",
  "email": "",
  "jobTitle": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "phone": "",
  "state": "",
  "url": "",
  "zipCode": ""
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

## 53. Site Organization Information

# Site Organization Information

**Endpoint:** `PUT /api/3/sites/{id}/organization`

## Description
Updates the site organization information.

**Operation ID:** `updateSiteOrganization`

## Parameters

### Parameter 1
**Name:** `siteOrganization`
**Location:** body
**Type:** SiteOrganization
**Required:** No
**Description:** Resource for updating the specified site's organization information.
**JSON Example:**
```json
{
  "address": "",
  "city": "",
  "contact": "",
  "country": "",
  "email": "",
  "jobTitle": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "phone": "",
  "state": "",
  "url": "",
  "zipCode": ""
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `siteOrganization`
**Location:** body
**Type:** SiteOrganization
**Required:** No
**Description:** Resource for updating the specified site's organization information.
**JSON Example:**
```json
{
  "address": "",
  "city": "",
  "contact": "",
  "country": "",
  "email": "",
  "jobTitle": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "phone": "",
  "state": "",
  "url": "",
  "zipCode": ""
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

## 54. Site Scan Engine

# Site Scan Engine

**Endpoint:** `GET /api/3/sites/{id}/scan_engine`

## Description
Retrieves the resource of the scan engine assigned to the site.

**Operation ID:** `getSiteScanEngine`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `ScanEngine`
**Example JSON Response:**
```json
{
  "address": "corporate-scan-engine-001.acme.com",
  "contentVersion": "",
  "id": 6,
  "isAWSPreAuthEngine": false,
  "lastRefreshedDate": "",
  "lastUpdatedDate": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Corporate Scan Engine 001",
  "port": 40894,
  "productVersion": "",
  "serialNumber": "",
  "sites": [
    42
  ],
  "status": ""
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

## 55. Site Scan Engine

# Site Scan Engine

**Endpoint:** `PUT /api/3/sites/{id}/scan_engine`

## Description
Updates the assigned scan engine to the site.

**Operation ID:** `setSiteScanEngine`

## Parameters

### Parameter 1
**Name:** `scanEngineId`
**Location:** body
**Type:** integer
**Required:** No
**Description:** The identifier of the scan engine.
**JSON Example:**
```json
42
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `scanEngineId`
**Location:** body
**Type:** integer
**Required:** No
**Description:** The identifier of the scan engine.
**JSON Example:**
```json
42
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

## 56. Site Scan Schedules

# Site Scan Schedules

**Endpoint:** `GET /api/3/sites/{id}/scan_schedules`

## Description
Returns all scan schedules for the site.

**Operation ID:** `getSiteScanSchedules`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«ScanSchedule»`
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
      "assets": {
        "excludedAssetGroups": {
          "assetGroupIDs": [
            42
          ],
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ]
        },
        "excludedTargets": {
          "addresses": [
            "string"
          ],
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ]
        },
        "includedAssetGroups": {
          "assetGroupIDs": [
            42
          ],
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ]
        },
        "includedTargets": {
          "addresses": [
            "string"
          ],
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ]
        }
      },
      "duration": "",
      "enabled": false,
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "nextRuntimes": [
        "string"
      ],
      "onScanRepeat": "",
      "repeat": {
        "dayOfWeek": "",
        "every": "date-of-month",
        "interval": 1,
        "lastDayOfMonth": false,
        "weekOfMonth": ""
      },
      "scanEngineId": "",
      "scanName": "",
      "scanTemplateId": "",
      "start": "2018-03-01T04:31:56Z"
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

## 57. Site Scan Schedules

# Site Scan Schedules

**Endpoint:** `POST /api/3/sites/{id}/scan_schedules`

## Description
Creates a new scan schedule for the specified site.

**Operation ID:** `createSiteScanSchedule`

## Parameters

### Parameter 1
**Name:** `scanSchedule`
**Location:** body
**Type:** ScanSchedule
**Required:** No
**Description:** Resource for a scan schedule.
**JSON Example:**
```json
{
  "assets": {
    "excludedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "excludedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    }
  },
  "duration": "",
  "enabled": false,
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "nextRuntimes": [
    "string"
  ],
  "onScanRepeat": "",
  "repeat": {
    "dayOfWeek": "",
    "every": "date-of-month",
    "interval": 1,
    "lastDayOfMonth": false,
    "weekOfMonth": ""
  },
  "scanEngineId": "",
  "scanName": "",
  "scanTemplateId": "",
  "start": "2018-03-01T04:31:56Z"
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `scanSchedule`
**Location:** body
**Type:** ScanSchedule
**Required:** No
**Description:** Resource for a scan schedule.
**JSON Example:**
```json
{
  "assets": {
    "excludedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "excludedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    }
  },
  "duration": "",
  "enabled": false,
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "nextRuntimes": [
    "string"
  ],
  "onScanRepeat": "",
  "repeat": {
    "dayOfWeek": "",
    "every": "date-of-month",
    "interval": 1,
    "lastDayOfMonth": false,
    "weekOfMonth": ""
  },
  "scanEngineId": "",
  "scanName": "",
  "scanTemplateId": "",
  "start": "2018-03-01T04:31:56Z"
}
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«ScanScheduleID,Link»`
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

## 58. Site Scan Schedules

# Site Scan Schedules

**Endpoint:** `PUT /api/3/sites/{id}/scan_schedules`

## Description
Updates all scan schedules for the specified site in a single request using the array of resources defined in the request body.

**Operation ID:** `setSiteScanSchedules`

## Parameters

### Parameter 1
**Name:** `scanSchedules`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all scan schedules defined in the site. Scan schedules defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "assets": {
      "excludedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "excludedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      }
    },
    "duration": "",
    "enabled": false,
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "nextRuntimes": [
      "string"
    ],
    "onScanRepeat": "",
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "lastDayOfMonth": false,
      "weekOfMonth": ""
    },
    "scanEngineId": "",
    "scanName": "",
    "scanTemplateId": "",
    "start": "2018-03-01T04:31:56Z"
  }
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `scanSchedules`
**Location:** body
**Type:** array
**Required:** No
**Description:** Array of resources for updating all scan schedules defined in the site. Scan schedules defined in the site that are omitted from this request will be deleted from the site.
**JSON Example:**
```json
[
  {
    "assets": {
      "excludedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "excludedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedAssetGroups": {
        "assetGroupIDs": [
          42
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      },
      "includedTargets": {
        "addresses": [
          "string"
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ]
      }
    },
    "duration": "",
    "enabled": false,
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "nextRuntimes": [
      "string"
    ],
    "onScanRepeat": "",
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "lastDayOfMonth": false,
      "weekOfMonth": ""
    },
    "scanEngineId": "",
    "scanName": "",
    "scanTemplateId": "",
    "start": "2018-03-01T04:31:56Z"
  }
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

## 59. Site Scan Schedules

# Site Scan Schedules

**Endpoint:** `DELETE /api/3/sites/{id}/scan_schedules`

## Description
Deletes all scan schedules from the site.

**Operation ID:** `deleteAllSiteScanSchedules`

## Parameters

### Parameter 1
**Name:** `id`
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

## 60. Site Scan Schedule

# Site Scan Schedule

**Endpoint:** `GET /api/3/sites/{id}/scan_schedules/{scheduleId}`

## Description
Retrieves the specified scan schedule.

**Operation ID:** `getSiteScanSchedule`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `scheduleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the scan schedule.

## Responses

### 200
**Description:** OK
**Schema:** `ScanSchedule`
**Example JSON Response:**
```json
{
  "assets": {
    "excludedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "excludedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    }
  },
  "duration": "",
  "enabled": false,
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "nextRuntimes": [
    "string"
  ],
  "onScanRepeat": "",
  "repeat": {
    "dayOfWeek": "",
    "every": "date-of-month",
    "interval": 1,
    "lastDayOfMonth": false,
    "weekOfMonth": ""
  },
  "scanEngineId": "",
  "scanName": "",
  "scanTemplateId": "",
  "start": "2018-03-01T04:31:56Z"
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

## 61. Site Scan Schedule

# Site Scan Schedule

**Endpoint:** `PUT /api/3/sites/{id}/scan_schedules/{scheduleId}`

## Description
Updates the specified scan schedule.

**Operation ID:** `updateSiteScanSchedule`

## Parameters

### Parameter 1
**Name:** `scanSchedule`
**Location:** body
**Type:** ScanSchedule
**Required:** No
**Description:** Resource for updating the specified scan schedule.
**JSON Example:**
```json
{
  "assets": {
    "excludedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "excludedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    }
  },
  "duration": "",
  "enabled": false,
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "nextRuntimes": [
    "string"
  ],
  "onScanRepeat": "",
  "repeat": {
    "dayOfWeek": "",
    "every": "date-of-month",
    "interval": 1,
    "lastDayOfMonth": false,
    "weekOfMonth": ""
  },
  "scanEngineId": "",
  "scanName": "",
  "scanTemplateId": "",
  "start": "2018-03-01T04:31:56Z"
}
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 3
**Name:** `scheduleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the scan schedule.

## Request Body
**Name:** `scanSchedule`
**Location:** body
**Type:** ScanSchedule
**Required:** No
**Description:** Resource for updating the specified scan schedule.
**JSON Example:**
```json
{
  "assets": {
    "excludedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "excludedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedAssetGroups": {
      "assetGroupIDs": [
        42
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "includedTargets": {
      "addresses": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    }
  },
  "duration": "",
  "enabled": false,
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "nextRuntimes": [
    "string"
  ],
  "onScanRepeat": "",
  "repeat": {
    "dayOfWeek": "",
    "every": "date-of-month",
    "interval": 1,
    "lastDayOfMonth": false,
    "weekOfMonth": ""
  },
  "scanEngineId": "",
  "scanName": "",
  "scanTemplateId": "",
  "start": "2018-03-01T04:31:56Z"
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

## 62. Site Scan Schedule

# Site Scan Schedule

**Endpoint:** `DELETE /api/3/sites/{id}/scan_schedules/{scheduleId}`

## Description
Deletes the specified scan schedule from the site.

**Operation ID:** `deleteSiteScanSchedule`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `scheduleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the scan schedule.

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

## 63. Site Scan Template

# Site Scan Template

**Endpoint:** `GET /api/3/sites/{id}/scan_template`

## Description
Retrieves the resource of the scan template assigned to the site.

**Operation ID:** `getSiteScanTemplate`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `ScanTemplate`
**Example JSON Response:**
```json
{
  "checks": {
    "categories": {
      "disabled": [
        "string"
      ],
      "enabled": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "correlate": false,
    "individual": {
      "disabled": [
        "string"
      ],
      "enabled": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "potential": false,
    "types": {
      "disabled": [
        "string"
      ],
      "enabled": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "unsafe": false
  },
  "database": {
    "db2": "database",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "oracle": [
      "string"
    ],
    "postgres": "postgres"
  },
  "description": "Performs a full network audit of all systems using only safe checks...",
  "discovery": {
    "asset": {
      "collectWhoisInformation": false,
      "fingerprintMinimumCertainty": 0.16,
      "fingerprintRetries": 0,
      "ipFingerprintingEnabled": true,
      "sendArpPings": true,
      "sendIcmpPings": true,
      "tcpPorts": [
        42
      ],
      "treatTcpResetAsAsset": true,
      "udpPorts": [
        42
      ]
    },
    "performance": {
      "packetRate": {
        "defeatRateLimit": true,
        "maximum": 15000,
        "minimum": 450
      },
      "parallelism": {
        "maximum": 0,
        "minimum": 0
      },
      "retryLimit": 3,
      "scanDelay": {
        "maximum": "PT0S",
        "minimum": "PT0S"
      },
      "timeout": {
        "initial": "PT0.5S",
        "maximum": "PT3S",
        "minimum": "PT0S"
      }
    },
    "service": {
      "serviceNameFile": "",
      "tcp": {
        "additionalPorts": [
          {}
        ],
        "excludedPorts": [
          {}
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "method": "SYN",
        "ports": "well-known"
      },
      "udp": {
        "additionalPorts": [
          {}
        ],
        "excludedPorts": [
          {}
        ],
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "ports": "well-known"
      }
    }
  },
  "discoveryOnly": false,
  "enableWindowsServices": false,
  "enhancedLogging": false,
  "id": "full-audit-without-web-spider",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "maxParallelAssets": 10,
  "maxScanProcesses": 10,
  "name": "Full audit",
  "policy": {
    "enabled": [
      42
    ],
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "recursiveWindowsFSSearch": false,
    "storeSCAP": false
  },
  "policyEnabled": true,
  "telnet": {
    "characterSet": "ASCII",
    "failedLoginRegex": "(?:[i,I]ncorrect|[u,U]nknown|[f,F]ail|[i,I]nvalid|[l,L]ogin|[p,P]assword|[p,P]asswd|[u,U]sername|[u,U]nable|[e,E]rror|[d,D]enied|[r,R]eject|[r,R]efuse|[c,C]lose|[c,C]losing|Not on system console|% Bad)",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "loginRegex": "(?:[l,L]ogin|[u,U]ser.?[nN]ame) *\\:",
    "passwordPromptRegex": "(?:[p,P]assword|[p,P]asswd) *\\:",
    "questionableLoginRegex": "(?:[l,L]ast [l,L]ogin *\\:|allows only .* Telnet Client License)"
  },
  "vulnerabilityEnabled": true,
  "web": {
    "dontScanMultiUseDevices": true,
    "includeQueryStrings": false,
    "paths": {
      "boostrap": "/root",
      "excluded": "/root/sensitive.html",
      "honorRobotDirectives": false
    },
    "patterns": {
      "sensitiveContent": "",
      "sensitiveField": "(p|pass)(word|phrase|wd|code)"
    },
    "performance": {
      "httpDaemonsToSkip": [
        "string"
      ],
      "maximumDirectoryLevels": 6,
      "maximumForeignHosts": 100,
      "maximumLinkDepth": 6,
      "maximumPages": 3000,
      "maximumRetries": 2,
      "maximumTime": "PT0S",
      "responseTimeout": "PT2M",
      "threadsPerServer": 3
    },
    "testCommonUsernamesAndPasswords": false,
    "testXssInSingleScan": false,
    "userAgent": "Mozilla/5.0 (compatible; MSIE 7.0; Windows NT 6.0; .NET CLR 1.1.4322; .NET CLR 2.0.50727)"
  },
  "webEnabled": true
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

## 64. Site Scan Template

# Site Scan Template

**Endpoint:** `PUT /api/3/sites/{id}/scan_template`

## Description
Updates the assigned scan template to the site.

**Operation ID:** `setSiteScanTemplate`

## Parameters

### Parameter 1
**Name:** `scanTemplateId`
**Location:** body
**Type:** string
**Required:** No
**Description:** The identifier of the scan template.
**JSON Example:**
```json
"string"
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `scanTemplateId`
**Location:** body
**Type:** string
**Required:** No
**Description:** The identifier of the scan template.
**JSON Example:**
```json
"string"
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

## 65. Assigned Shared Credentials

# Assigned Shared Credentials

**Endpoint:** `GET /api/3/sites/{id}/shared_credentials`

## Description
Retrieve all of the shared credentials assigned to the site. These shared credentials can be enabled/disabled for the site's scan.

**Operation ID:** `getSiteSharedCredentials`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SiteSharedCredential»`
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
      "enabled": false,
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "service": ""
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

## 66. Assigned Shared Credential Enablement

# Assigned Shared Credential Enablement

**Endpoint:** `PUT /api/3/sites/{id}/shared_credentials/{credentialId}/enabled`

## Description
Enable or disable the shared credential for the site's scans.

**Operation ID:** `enableSharedCredentialOnSite`

## Parameters

### Parameter 1
**Name:** `status`
**Location:** body
**Type:** boolean
**Required:** No
**Description:** Flag indicating whether the shared credential is enabled for the site's scans.
**JSON Example:**
```json
true
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 3
**Name:** `credentialId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the shared credential.

## Request Body
**Name:** `status`
**Location:** body
**Type:** boolean
**Required:** No
**Description:** Flag indicating whether the shared credential is enabled for the site's scans.
**JSON Example:**
```json
true
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

## 67. Site Scan Credentials

# Site Scan Credentials

**Endpoint:** `GET /api/3/sites/{id}/site_credentials`

## Description
Retrieves all defined site credential resources.

**Operation ID:** `getSiteCredentials`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SiteCredential»`
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
      "account": {
        "service": "string"
      },
      "description": "",
      "enabled": false,
      "hostRestriction": "",
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "portRestriction": ""
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

## 68. Site Scan Credentials

# Site Scan Credentials

**Endpoint:** `POST /api/3/sites/{id}/site_credentials`

## Description
Creates a new site credential.

**Operation ID:** `createSiteCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `siteCredential`
**Location:** body
**Type:** SiteCredential
**Required:** No
**Description:** The specification of a site credential.
**JSON Example:**
```json
{
  "account": {
    "service": "string"
  },
  "description": "",
  "enabled": false,
  "hostRestriction": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "portRestriction": ""
}
```

## Request Body
**Name:** `siteCredential`
**Location:** body
**Type:** SiteCredential
**Required:** No
**Description:** The specification of a site credential.
**JSON Example:**
```json
{
  "account": {
    "service": "string"
  },
  "description": "",
  "enabled": false,
  "hostRestriction": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "portRestriction": ""
}
```

## Responses

### 201
**Description:** Created
**Schema:** `CreatedReference«CredentialID,Link»`
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

## 69. Site Scan Credentials

# Site Scan Credentials

**Endpoint:** `PUT /api/3/sites/{id}/site_credentials`

## Description
Updates multiple site credentials.

**Operation ID:** `setSiteCredentials`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `siteCredentials`
**Location:** body
**Type:** array
**Required:** No
**Description:** A list of site credentials resources.
**JSON Example:**
```json
[
  {
    "account": {
      "service": "string"
    },
    "description": "",
    "enabled": false,
    "hostRestriction": "",
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "portRestriction": ""
  }
]
```

## Request Body
**Name:** `siteCredentials`
**Location:** body
**Type:** array
**Required:** No
**Description:** A list of site credentials resources.
**JSON Example:**
```json
[
  {
    "account": {
      "service": "string"
    },
    "description": "",
    "enabled": false,
    "hostRestriction": "",
    "id": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "portRestriction": ""
  }
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

## 70. Site Scan Credentials

# Site Scan Credentials

**Endpoint:** `DELETE /api/3/sites/{id}/site_credentials`

## Description
Deletes all site credentials from the site.

**Operation ID:** `deleteAllSiteCredentials`

## Parameters

### Parameter 1
**Name:** `id`
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

## 71. Site Scan Credential

# Site Scan Credential

**Endpoint:** `GET /api/3/sites/{id}/site_credentials/{credentialId}`

## Description
Retrieves the specified site credential.

**Operation ID:** `getSiteCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `credentialId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site credential.

## Responses

### 200
**Description:** OK
**Schema:** `SiteCredential`
**Example JSON Response:**
```json
{
  "account": {
    "service": "string"
  },
  "description": "",
  "enabled": false,
  "hostRestriction": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "portRestriction": ""
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

## 72. Site Scan Credential

# Site Scan Credential

**Endpoint:** `PUT /api/3/sites/{id}/site_credentials/{credentialId}`

## Description
Updates the specified site credential.

**Operation ID:** `updateSiteCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `credentialId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site credential.

### Parameter 3
**Name:** `siteCredential`
**Location:** body
**Type:** SiteCredential
**Required:** No
**Description:** The specification of the site credential to update.
**JSON Example:**
```json
{
  "account": {
    "service": "string"
  },
  "description": "",
  "enabled": false,
  "hostRestriction": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "portRestriction": ""
}
```

## Request Body
**Name:** `siteCredential`
**Location:** body
**Type:** SiteCredential
**Required:** No
**Description:** The specification of the site credential to update.
**JSON Example:**
```json
{
  "account": {
    "service": "string"
  },
  "description": "",
  "enabled": false,
  "hostRestriction": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "portRestriction": ""
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

## 73. Site Scan Credential

# Site Scan Credential

**Endpoint:** `DELETE /api/3/sites/{id}/site_credentials/{credentialId}`

## Description
Deletes the specified site credential.

**Operation ID:** `deleteSiteCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `credentialId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site credential.

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

## 74. Site Credential Enablement

# Site Credential Enablement

**Endpoint:** `PUT /api/3/sites/{id}/site_credentials/{credentialId}/enabled`

## Description
Enable or disable the site credential for scans.

**Operation ID:** `enableSiteCredential`

## Parameters

### Parameter 1
**Name:** `status`
**Location:** body
**Type:** boolean
**Required:** No
**Description:** Flag indicating whether the credential is enabled for use during the scan.
**JSON Example:**
```json
true
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 3
**Name:** `credentialId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site credential.

## Request Body
**Name:** `status`
**Location:** body
**Type:** boolean
**Required:** No
**Description:** Flag indicating whether the credential is enabled for use during the scan.
**JSON Example:**
```json
true
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

## 75. Site Tags

# Site Tags

**Endpoint:** `GET /api/3/sites/{id}/tags`

## Description
Retrieves the list of tags added to the sites.

**Operation ID:** `getSiteTags`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«Tag»`
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

## 76. Site Tags

# Site Tags

**Endpoint:** `PUT /api/3/sites/{id}/tags`

## Description
Updates the site's list of tags.

**Operation ID:** `setSiteTags`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `tags`
**Location:** body
**Type:** array
**Required:** No
**Description:** A list of tag identifiers to replace the site's tags.
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
**Description:** A list of tag identifiers to replace the site's tags.
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

## 77. Site Tag

# Site Tag

**Endpoint:** `PUT /api/3/sites/{id}/tags/{tagId}`

## Description
Adds a tag to the site.

**Operation ID:** `addSiteTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `tagId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the tag.

## Responses

### 201
**Description:** Created
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

## 78. Site Tag

# Site Tag

**Endpoint:** `DELETE /api/3/sites/{id}/tags/{tagId}`

## Description
Removes the specified tag from the site's tags.

**Operation ID:** `removeSiteTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

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

## 79. Site Users Access

# Site Users Access

**Endpoint:** `GET /api/3/sites/{id}/users`

## Description
Retrieve the list of non-administrator users that have access to the site.

**Operation ID:** `getSiteUsers`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«User»`
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
      "authentication": {
        "external": false,
        "id": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "type": ""
      },
      "email": "",
      "enabled": false,
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "locale": {
        "default": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "reports": ""
      },
      "locked": false,
      "login": "",
      "name": "",
      "role": {
        "allAssetGroups": false,
        "allSites": false,
        "id": "",
        "name": "",
        "privileges": [
          "all-permissions"
        ],
        "superuser": false
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

## 80. Site Users Access

# Site Users Access

**Endpoint:** `POST /api/3/sites/{id}/users`

## Description
Grants a non-administrator user access to the specified site.

**Operation ID:** `addSiteUser`

## Parameters

### Parameter 1
**Name:** `param0`
**Location:** body
**Type:** integer
**Required:** No
**Description:** The identifier of the user.
**JSON Example:**
```json
42
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `param0`
**Location:** body
**Type:** integer
**Required:** No
**Description:** The identifier of the user.
**JSON Example:**
```json
42
```

## Responses

### 201
**Description:** Created
**Schema:** `ReferenceWith«UserID,Link»`
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

## 81. Site Users Access

# Site Users Access

**Endpoint:** `PUT /api/3/sites/{id}/users`

## Description
Updates the site's access list.

**Operation ID:** `setSiteUsers`

## Parameters

### Parameter 1
**Name:** `users`
**Location:** body
**Type:** array
**Required:** No
**Description:** A list of user identifiers to replace the site's access list.
**JSON Example:**
```json
[
  42
]
```

### Parameter 2
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Request Body
**Name:** `users`
**Location:** body
**Type:** array
**Required:** No
**Description:** A list of user identifiers to replace the site's access list.
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

## 82. Site User Access

# Site User Access

**Endpoint:** `DELETE /api/3/sites/{id}/users/{userId}`

## Description
Removes the specified user from the site's access list.

**Operation ID:** `removeSiteUser`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

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

## 83. Web Authentication HTML Forms

# Web Authentication HTML Forms

**Endpoint:** `GET /api/3/sites/{id}/web_authentication/html_forms`

## Description
Retrieves all HTML form authentications configured in the site.

**Operation ID:** `getWebAuthHtmlForms`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«WebFormAuthentication»`
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
      "baseURL": "",
      "enabled": false,
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "loginRegularExpression": "",
      "loginURL": "",
      "name": "",
      "service": ""
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

## 84. Web Authentication HTTP Headers

# Web Authentication HTTP Headers

**Endpoint:** `GET /api/3/sites/{id}/web_authentication/http_headers`

## Description
Retrieves all HTTP header authentications configured in the site.

**Operation ID:** `getWebAuthHTTPHeaders`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«WebHeaderAuthentication»`
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
      "baseURL": "",
      "enabled": false,
      "headers": {},
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "loginRegularExpression": "",
      "name": "",
      "service": ""
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
