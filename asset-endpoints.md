# Asset Endpoints

## Description
Resources and operations for managing assets. Assets can be created under the Site Assets resource.

This document contains 25 endpoints under the Asset tag.

---

## 1. Assets

# Assets

**Endpoint:** `GET /api/3/assets`

## Description
Returns all assets for which you have access.

**Operation ID:** `getAssets`

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

## 2. Assets

# Assets

**Endpoint:** `POST /api/3/sites/{id}/assets`

## Description
Creates or updates an asset with the specified details.

**Operation ID:** `createAsset`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the site.

### Parameter 2
**Name:** `asset`
**Location:** body
**Type:** AssetCreate
**Required:** No
**Description:** The details of the asset being added or updated. The operating system can be specified in one of three ways, with the order of precedence: `"osFingerprint"`, `"os"`, `"cpe"`
**JSON Example:**
```json
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
  "cpe": "",
  "databases": [
    {
      "description": "Microsoft SQL Server",
      "id": 13,
      "name": "MSSQL"
    }
  ],
  "date": "",
  "description": "",
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
  "hostName": {
    "name": "corporate-workstation-1102DC.acme.com",
    "source": "DNS"
  },
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
  "os": "",
  "osCertainty": "",
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
```

## Request Body
**Name:** `asset`
**Location:** body
**Type:** AssetCreate
**Required:** No
**Description:** The details of the asset being added or updated. The operating system can be specified in one of three ways, with the order of precedence: `"osFingerprint"`, `"os"`, `"cpe"`
**JSON Example:**
```json
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
  "cpe": "",
  "databases": [
    {
      "description": "Microsoft SQL Server",
      "id": 13,
      "name": "MSSQL"
    }
  ],
  "date": "",
  "description": "",
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
  "hostName": {
    "name": "corporate-workstation-1102DC.acme.com",
    "source": "DNS"
  },
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
  "os": "",
  "osCertainty": "",
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
```

## Responses

### 200
**Description:** OK
**Schema:** `CreatedReference`
**Example JSON Response:**
```json
{
  "id": {},
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ]
}
```

### 201
**Description:** Created
**Schema:** `CreatedOrUpdatedReference`
**Example JSON Response:**
```json
{
  "id": {},
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

## 3. Asset Search

# Asset Search

**Endpoint:** `POST /api/3/assets/search`

## Description
Returns all assets for which you have access that match the given search criteria.

**Operation ID:** `findAssets`

## Parameters

### Parameter 1
**Name:** `param1`
**Location:** body
**Type:** SearchCriteria
**Required:** Yes
**Description:** param1
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

## Request Body
**Name:** `param1`
**Location:** body
**Type:** SearchCriteria
**Required:** Yes
**Description:** param1
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

## 4. Asset

# Asset

**Endpoint:** `GET /api/3/assets/{id}`

## Description
Returns the specified asset.

**Operation ID:** `getAsset`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Asset`
**Example JSON Response:**
```json
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

## 5. Asset

# Asset

**Endpoint:** `DELETE /api/3/assets/{id}`

## Description
Deletes the specified asset.

**Operation ID:** `deleteAsset`

## Parameters

### Parameter 1
**Name:** `id`
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

## 6. Asset Databases

# Asset Databases

**Endpoint:** `GET /api/3/assets/{id}/databases`

## Description
Returns the databases enumerated on an asset.

**Operation ID:** `getAssetDatabases`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«Database»`
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
      "description": "Microsoft SQL Server",
      "id": 13,
      "name": "MSSQL"
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

## 7. Asset Files

# Asset Files

**Endpoint:** `GET /api/3/assets/{id}/files`

## Description
Returns the files discovered on an asset.

**Operation ID:** `getAssetFiles`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«File»`
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

## 8. Asset Services

# Asset Services

**Endpoint:** `GET /api/3/assets/{id}/services`

## Description
Returns the services discovered on an asset.

**Operation ID:** `getAssetServices`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«ReferenceWithEndpointIDLink,ServiceLink»`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "port": 22,
      "protocol": "tcp",
      "rel": "Service"
    }
  ],
  "resources": [
    {
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "port": 22,
      "protocol": "tcp"
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

## 9. Asset Service

# Asset Service

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}`

## Description
Returns the service running a port and protocol on the asset.

**Operation ID:** `getAssetService`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

## Responses

### 200
**Description:** OK
**Schema:** `Service`
**Example JSON Response:**
```json
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

## 10. Asset Service Configurations

# Asset Service Configurations

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}/configurations`

## Description
Returns the configuration (properties) of a port and protocol on an asset.

**Operation ID:** `getAssetServiceConfigurations`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«Configuration»`
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
      "name": "<name>",
      "value": "<value>"
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

## 11. Asset Service Databases

# Asset Service Databases

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}/databases`

## Description
Returns the databases running on a port and protocol on an asset.

**Operation ID:** `getAssetServiceDatabases`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«Database»`
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
      "description": "Microsoft SQL Server",
      "id": 13,
      "name": "MSSQL"
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

## 12. Asset Service User Groups

# Asset Service User Groups

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}/user_groups`

## Description
Returns the user groups enumerated on a port and protocol on an asset.

**Operation ID:** `getAssetServiceUserGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«GroupAccount»`
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
      "id": 972,
      "name": "Administrators"
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

## 13. Asset Service Users

# Asset Service Users

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}/users`

## Description
Returns the users enumerated on a port and protocol on an asset.

**Operation ID:** `getAssetServiceUsers`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«UserAccount»`
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
      "fullName": "Smith, John",
      "id": 8952,
      "name": "john_smith"
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

## 14. Asset Service Web Applications

# Asset Service Web Applications

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}/web_applications`

## Description
Returns the web applications running on a port and protocol on an asset.

**Operation ID:** `getAssetServiceWebApplications`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

## Responses

### 200
**Description:** OK
**Schema:** `ReferencesWith«WebApplicationID,Link»`
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

## 15. Asset Service Web Application

# Asset Service Web Application

**Endpoint:** `GET /api/3/assets/{id}/services/{protocol}/{port}/web_applications/{webApplicationId}`

## Description
Returns a web application running on a port and protocol on an asset.

**Operation ID:** `getAssetServiceWebApplication`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `protocol`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The protocol of the service.

### Parameter 3
**Name:** `port`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The port of the service.

### Parameter 4
**Name:** `webApplicationId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the web application.

## Responses

### 200
**Description:** OK
**Schema:** `WebApplication`
**Example JSON Response:**
```json
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

## 16. Asset Software

# Asset Software

**Endpoint:** `GET /api/3/assets/{id}/software`

## Description
Returns the software on an asset.

**Operation ID:** `getAssetSoftware`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«Software»`
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

## 17. Asset Tags

# Asset Tags

**Endpoint:** `GET /api/3/assets/{id}/tags`

## Description
Returns tags assigned to an asset.

**Operation ID:** `getAssetTags`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«AssetTag»`
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
      "riskModifier": {},
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
      "sources": [
        {
          "id": 92,
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ],
          "source": "site"
        }
      ],
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

## 18. Asset Tag

# Asset Tag

**Endpoint:** `PUT /api/3/assets/{id}/tags/{tagId}`

## Description
Assigns the specified tag to the asset.

**Operation ID:** `addAssetTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

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

## 19. Asset Tag

# Asset Tag

**Endpoint:** `DELETE /api/3/assets/{id}/tags/{tagId}`

## Description
Removes the specified tag from the asset's tags.

**Operation ID:** `removeAssetTag`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

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

## 20. Asset User Groups

# Asset User Groups

**Endpoint:** `GET /api/3/assets/{id}/user_groups`

## Description
Returns user groups enumerated on an asset.

**Operation ID:** `getAssetUserGroups`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«GroupAccount»`
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
      "id": 972,
      "name": "Administrators"
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

## 21. Asset Users

# Asset Users

**Endpoint:** `GET /api/3/assets/{id}/users`

## Description
Returns users enumerated on an asset.

**Operation ID:** `getAssetUsers`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«UserAccount»`
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
      "fullName": "Smith, John",
      "id": 8952,
      "name": "john_smith"
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

## 22. Operating Systems

# Operating Systems

**Endpoint:** `GET /api/3/operating_systems`

## Description
Returns all operating systems discovered across all assets.

**Operation ID:** `getOperatingSystems`

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
**Schema:** `PageOf«OperatingSystem»`
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

## 23. Operating System

# Operating System

**Endpoint:** `GET /api/3/operating_systems/{id}`

## Description
Returns the details for an operating system.

**Operation ID:** `getOperatingSystem`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the operating system.

## Responses

### 200
**Description:** OK
**Schema:** `OperatingSystem`
**Example JSON Response:**
```json
{
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

## 24. Software

# Software

**Endpoint:** `GET /api/3/software`

## Description
Returns all software enumerated on any asset.

**Operation ID:** `getSoftwares`

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
**Schema:** `PageOf«Software»`
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

## 25. Software

# Software

**Endpoint:** `GET /api/3/software/{id}`

## Description
Returns the details for software.

**Operation ID:** `getSoftware`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the software.

## Responses

### 200
**Description:** OK
**Schema:** `Software`
**Example JSON Response:**
```json
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
