# Report Endpoints

## Description
Resources and operations for managing and generating reports. Reports are broadly categorized into `document`, `export`, and `file` types. `document` reports use section-based report templates to control the output and can be generated in several formats. `export` reports are designed to output their contents into a specific file format. `file` reports are templatized reports that output based on the format of a template file. Reports can be configured to generate on a schedule and be distributed via email to specific recipients.

This document contains 13 endpoints under the Report tag.

---

## 1. Report Formats

# Report Formats

**Endpoint:** `GET /api/3/report_formats`

## Description
Returns all available report formats. A report format indicates an output file format specification (e.g. PDF, XML, etc). Some printable formats may be templated, and others may not. The supported templates for each formated are provided.

**Operation ID:** `getReportFormats`

## Responses

### 200
**Description:** OK
**Schema:** `Resources«AvailableReportFormat»`
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
      "format": "pdf",
      "templates": [
        "string"
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

## 2. Report Templates

# Report Templates

**Endpoint:** `GET /api/3/report_templates`

## Description
Returns all available report templates.

**Operation ID:** `getReportTemplates`

## Responses

### 200
**Description:** OK
**Schema:** `Resources«ReportTemplate»`
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
      "builtin": true,
      "description": "Provides comprehensive details about discovered assets, vulnerabilities, and users.",
      "id": "audit-report",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "Audit Report",
      "sections": [
        "string"
      ],
      "type": "document"
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

## 3. Report Template

# Report Template

**Endpoint:** `GET /api/3/report_templates/{id}`

## Description
Returns the details of a report template. Report templates govern the contents generated within a report.

**Operation ID:** `getReportTemplate`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the report template;

## Responses

### 200
**Description:** OK
**Schema:** `ReportTemplate`
**Example JSON Response:**
```json
{
  "builtin": true,
  "description": "Provides comprehensive details about discovered assets, vulnerabilities, and users.",
  "id": "audit-report",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Audit Report",
  "sections": [
    "string"
  ],
  "type": "document"
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

## 4. Reports

# Reports

**Endpoint:** `GET /api/3/reports`

## Description
Returns all defined report configurations.

**Operation ID:** `getReports`

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
**Schema:** `PageOf«Report»`
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
      "baseline": {},
      "bureau": "Bureau",
      "component": "Component",
      "email": {
        "access": "zip",
        "additional": "file",
        "additionalRecipients": [
          "string"
        ],
        "assetAccess": true,
        "owner": "file",
        "smtp": {
          "global": true,
          "relay": "mail.acme.com",
          "sender": "john_smith@acme.com"
        }
      },
      "enclave": "Enclave",
      "filters": {
        "categories": {
          "excluded": [
            "string"
          ],
          "included": [
            "string"
          ],
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ]
        },
        "severity": "",
        "statuses": [
          "vulnerable"
        ]
      },
      "format": "pdf",
      "frequency": {
        "nextRuntimes": [
          "string"
        ],
        "repeat": {
          "dayOfWeek": "",
          "every": "date-of-month",
          "interval": 1,
          "weekOfMonth": ""
        },
        "start": "2018-03-01T04:31:56Z",
        "type": "schedule"
      },
      "id": 17,
      "language": "en-US",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "Monthly Corporate Site Summary",
      "organization": "Acme, Inc.",
      "owner": 1,
      "policies": [
        42
      ],
      "policy": 789,
      "query": "SELECT * FROM dim_asset ORDER BY ip_address ASC",
      "range": {
        "every": "day",
        "from": "",
        "interval": 7,
        "to": ""
      },
      "remediation": {
        "solutions": 25,
        "sort": ""
      },
      "riskTrend": {
        "allAssets": {
          "total": true,
          "trend": "average-risk"
        },
        "assetGroupMembership": "historical",
        "assetGroups": "total",
        "assets": true,
        "from": "P3M",
        "sites": "average",
        "tagMembership": "historical",
        "tags": "average",
        "to": ""
      },
      "scope": {
        "assetGroups": [
          42
        ],
        "assets": [
          42
        ],
        "scan": 68,
        "sites": [
          42
        ],
        "tags": [
          42
        ]
      },
      "storage": {
        "location": "monthly_reports/site/corporate",
        "path": "$(install_dir)/nsc/reports/$(user)/monthly_reports/site/corporate"
      },
      "template": "executive-overview",
      "timezone": "America/Los_Angeles",
      "users": [
        42
      ],
      "version": "2.3.0"
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

## 5. Reports

# Reports

**Endpoint:** `POST /api/3/reports`

## Description
Configures a new report for generation. Report types are controlled through either or both a format and template. Non-templatized (`export`) report formats do not require a template and have their output format preset. Templatized (`document` and `file`) report formats support a report template that governs the content of the output and the output format can be chosen from a list of supported formats.

**Operation ID:** `createReport`

## Parameters

### Parameter 1
**Name:** `report`
**Location:** body
**Type:** Report
**Required:** No
**Description:** The specification of a report configuration.
**JSON Example:**
```json
{
  "baseline": {},
  "bureau": "Bureau",
  "component": "Component",
  "email": {
    "access": "zip",
    "additional": "file",
    "additionalRecipients": [
      "string"
    ],
    "assetAccess": true,
    "owner": "file",
    "smtp": {
      "global": true,
      "relay": "mail.acme.com",
      "sender": "john_smith@acme.com"
    }
  },
  "enclave": "Enclave",
  "filters": {
    "categories": {
      "excluded": [
        "string"
      ],
      "included": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "severity": "",
    "statuses": [
      "vulnerable"
    ]
  },
  "format": "pdf",
  "frequency": {
    "nextRuntimes": [
      "string"
    ],
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "weekOfMonth": ""
    },
    "start": "2018-03-01T04:31:56Z",
    "type": "schedule"
  },
  "id": 17,
  "language": "en-US",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Monthly Corporate Site Summary",
  "organization": "Acme, Inc.",
  "owner": 1,
  "policies": [
    42
  ],
  "policy": 789,
  "query": "SELECT * FROM dim_asset ORDER BY ip_address ASC",
  "range": {
    "every": "day",
    "from": "",
    "interval": 7,
    "to": ""
  },
  "remediation": {
    "solutions": 25,
    "sort": ""
  },
  "riskTrend": {
    "allAssets": {
      "total": true,
      "trend": "average-risk"
    },
    "assetGroupMembership": "historical",
    "assetGroups": "total",
    "assets": true,
    "from": "P3M",
    "sites": "average",
    "tagMembership": "historical",
    "tags": "average",
    "to": ""
  },
  "scope": {
    "assetGroups": [
      42
    ],
    "assets": [
      42
    ],
    "scan": 68,
    "sites": [
      42
    ],
    "tags": [
      42
    ]
  },
  "storage": {
    "location": "monthly_reports/site/corporate",
    "path": "$(install_dir)/nsc/reports/$(user)/monthly_reports/site/corporate"
  },
  "template": "executive-overview",
  "timezone": "America/Los_Angeles",
  "users": [
    42
  ],
  "version": "2.3.0"
}
```

## Request Body
**Name:** `report`
**Location:** body
**Type:** Report
**Required:** No
**Description:** The specification of a report configuration.
**JSON Example:**
```json
{
  "baseline": {},
  "bureau": "Bureau",
  "component": "Component",
  "email": {
    "access": "zip",
    "additional": "file",
    "additionalRecipients": [
      "string"
    ],
    "assetAccess": true,
    "owner": "file",
    "smtp": {
      "global": true,
      "relay": "mail.acme.com",
      "sender": "john_smith@acme.com"
    }
  },
  "enclave": "Enclave",
  "filters": {
    "categories": {
      "excluded": [
        "string"
      ],
      "included": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "severity": "",
    "statuses": [
      "vulnerable"
    ]
  },
  "format": "pdf",
  "frequency": {
    "nextRuntimes": [
      "string"
    ],
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "weekOfMonth": ""
    },
    "start": "2018-03-01T04:31:56Z",
    "type": "schedule"
  },
  "id": 17,
  "language": "en-US",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Monthly Corporate Site Summary",
  "organization": "Acme, Inc.",
  "owner": 1,
  "policies": [
    42
  ],
  "policy": 789,
  "query": "SELECT * FROM dim_asset ORDER BY ip_address ASC",
  "range": {
    "every": "day",
    "from": "",
    "interval": 7,
    "to": ""
  },
  "remediation": {
    "solutions": 25,
    "sort": ""
  },
  "riskTrend": {
    "allAssets": {
      "total": true,
      "trend": "average-risk"
    },
    "assetGroupMembership": "historical",
    "assetGroups": "total",
    "assets": true,
    "from": "P3M",
    "sites": "average",
    "tagMembership": "historical",
    "tags": "average",
    "to": ""
  },
  "scope": {
    "assetGroups": [
      42
    ],
    "assets": [
      42
    ],
    "scan": 68,
    "sites": [
      42
    ],
    "tags": [
      42
    ]
  },
  "storage": {
    "location": "monthly_reports/site/corporate",
    "path": "$(install_dir)/nsc/reports/$(user)/monthly_reports/site/corporate"
  },
  "template": "executive-overview",
  "timezone": "America/Los_Angeles",
  "users": [
    42
  ],
  "version": "2.3.0"
}
```

## Responses

### 200
**Description:** OK
**Schema:** `CreatedReference«int,Link»`
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

## 6. Report

# Report

**Endpoint:** `GET /api/3/reports/{id}`

## Description
Returns the configuration details of a report.

**Operation ID:** `getReport`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

## Responses

### 200
**Description:** OK
**Schema:** `Report`
**Example JSON Response:**
```json
{
  "baseline": {},
  "bureau": "Bureau",
  "component": "Component",
  "email": {
    "access": "zip",
    "additional": "file",
    "additionalRecipients": [
      "string"
    ],
    "assetAccess": true,
    "owner": "file",
    "smtp": {
      "global": true,
      "relay": "mail.acme.com",
      "sender": "john_smith@acme.com"
    }
  },
  "enclave": "Enclave",
  "filters": {
    "categories": {
      "excluded": [
        "string"
      ],
      "included": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "severity": "",
    "statuses": [
      "vulnerable"
    ]
  },
  "format": "pdf",
  "frequency": {
    "nextRuntimes": [
      "string"
    ],
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "weekOfMonth": ""
    },
    "start": "2018-03-01T04:31:56Z",
    "type": "schedule"
  },
  "id": 17,
  "language": "en-US",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Monthly Corporate Site Summary",
  "organization": "Acme, Inc.",
  "owner": 1,
  "policies": [
    42
  ],
  "policy": 789,
  "query": "SELECT * FROM dim_asset ORDER BY ip_address ASC",
  "range": {
    "every": "day",
    "from": "",
    "interval": 7,
    "to": ""
  },
  "remediation": {
    "solutions": 25,
    "sort": ""
  },
  "riskTrend": {
    "allAssets": {
      "total": true,
      "trend": "average-risk"
    },
    "assetGroupMembership": "historical",
    "assetGroups": "total",
    "assets": true,
    "from": "P3M",
    "sites": "average",
    "tagMembership": "historical",
    "tags": "average",
    "to": ""
  },
  "scope": {
    "assetGroups": [
      42
    ],
    "assets": [
      42
    ],
    "scan": 68,
    "sites": [
      42
    ],
    "tags": [
      42
    ]
  },
  "storage": {
    "location": "monthly_reports/site/corporate",
    "path": "$(install_dir)/nsc/reports/$(user)/monthly_reports/site/corporate"
  },
  "template": "executive-overview",
  "timezone": "America/Los_Angeles",
  "users": [
    42
  ],
  "version": "2.3.0"
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

## 7. Report

# Report

**Endpoint:** `PUT /api/3/reports/{id}`

## Description
Updates the configuration details of a report.

**Operation ID:** `updateReport`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

### Parameter 2
**Name:** `report`
**Location:** body
**Type:** Report
**Required:** No
**Description:** The specification of a report configuration.
**JSON Example:**
```json
{
  "baseline": {},
  "bureau": "Bureau",
  "component": "Component",
  "email": {
    "access": "zip",
    "additional": "file",
    "additionalRecipients": [
      "string"
    ],
    "assetAccess": true,
    "owner": "file",
    "smtp": {
      "global": true,
      "relay": "mail.acme.com",
      "sender": "john_smith@acme.com"
    }
  },
  "enclave": "Enclave",
  "filters": {
    "categories": {
      "excluded": [
        "string"
      ],
      "included": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "severity": "",
    "statuses": [
      "vulnerable"
    ]
  },
  "format": "pdf",
  "frequency": {
    "nextRuntimes": [
      "string"
    ],
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "weekOfMonth": ""
    },
    "start": "2018-03-01T04:31:56Z",
    "type": "schedule"
  },
  "id": 17,
  "language": "en-US",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Monthly Corporate Site Summary",
  "organization": "Acme, Inc.",
  "owner": 1,
  "policies": [
    42
  ],
  "policy": 789,
  "query": "SELECT * FROM dim_asset ORDER BY ip_address ASC",
  "range": {
    "every": "day",
    "from": "",
    "interval": 7,
    "to": ""
  },
  "remediation": {
    "solutions": 25,
    "sort": ""
  },
  "riskTrend": {
    "allAssets": {
      "total": true,
      "trend": "average-risk"
    },
    "assetGroupMembership": "historical",
    "assetGroups": "total",
    "assets": true,
    "from": "P3M",
    "sites": "average",
    "tagMembership": "historical",
    "tags": "average",
    "to": ""
  },
  "scope": {
    "assetGroups": [
      42
    ],
    "assets": [
      42
    ],
    "scan": 68,
    "sites": [
      42
    ],
    "tags": [
      42
    ]
  },
  "storage": {
    "location": "monthly_reports/site/corporate",
    "path": "$(install_dir)/nsc/reports/$(user)/monthly_reports/site/corporate"
  },
  "template": "executive-overview",
  "timezone": "America/Los_Angeles",
  "users": [
    42
  ],
  "version": "2.3.0"
}
```

## Request Body
**Name:** `report`
**Location:** body
**Type:** Report
**Required:** No
**Description:** The specification of a report configuration.
**JSON Example:**
```json
{
  "baseline": {},
  "bureau": "Bureau",
  "component": "Component",
  "email": {
    "access": "zip",
    "additional": "file",
    "additionalRecipients": [
      "string"
    ],
    "assetAccess": true,
    "owner": "file",
    "smtp": {
      "global": true,
      "relay": "mail.acme.com",
      "sender": "john_smith@acme.com"
    }
  },
  "enclave": "Enclave",
  "filters": {
    "categories": {
      "excluded": [
        "string"
      ],
      "included": [
        "string"
      ],
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ]
    },
    "severity": "",
    "statuses": [
      "vulnerable"
    ]
  },
  "format": "pdf",
  "frequency": {
    "nextRuntimes": [
      "string"
    ],
    "repeat": {
      "dayOfWeek": "",
      "every": "date-of-month",
      "interval": 1,
      "weekOfMonth": ""
    },
    "start": "2018-03-01T04:31:56Z",
    "type": "schedule"
  },
  "id": 17,
  "language": "en-US",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "Monthly Corporate Site Summary",
  "organization": "Acme, Inc.",
  "owner": 1,
  "policies": [
    42
  ],
  "policy": 789,
  "query": "SELECT * FROM dim_asset ORDER BY ip_address ASC",
  "range": {
    "every": "day",
    "from": "",
    "interval": 7,
    "to": ""
  },
  "remediation": {
    "solutions": 25,
    "sort": ""
  },
  "riskTrend": {
    "allAssets": {
      "total": true,
      "trend": "average-risk"
    },
    "assetGroupMembership": "historical",
    "assetGroups": "total",
    "assets": true,
    "from": "P3M",
    "sites": "average",
    "tagMembership": "historical",
    "tags": "average",
    "to": ""
  },
  "scope": {
    "assetGroups": [
      42
    ],
    "assets": [
      42
    ],
    "scan": 68,
    "sites": [
      42
    ],
    "tags": [
      42
    ]
  },
  "storage": {
    "location": "monthly_reports/site/corporate",
    "path": "$(install_dir)/nsc/reports/$(user)/monthly_reports/site/corporate"
  },
  "template": "executive-overview",
  "timezone": "America/Los_Angeles",
  "users": [
    42
  ],
  "version": "2.3.0"
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

## 8. Report

# Report

**Endpoint:** `DELETE /api/3/reports/{id}`

## Description
Deletes the configuration of a report.

**Operation ID:** `deleteReport`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

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

## 9. Report Generation

# Report Generation

**Endpoint:** `POST /api/3/reports/{id}/generate`

## Description
Generates a configured report and returns the instance identifier of the report.

**Operation ID:** `generateReport`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

## Responses

### 200
**Description:** OK
**Schema:** `ReferenceWithReportIDLink`
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

## 10. Report Histories

# Report Histories

**Endpoint:** `GET /api/3/reports/{id}/history`

## Description
Returns all historical details for generation of the report over time.

**Operation ID:** `getReportInstances`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«ReportInstance»`
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
      "generated": "2018-06-01T18:56:03Z",
      "id": 5,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "size": {
        "bytes": 24789050,
        "formatted": "23.6 MB"
      },
      "status": "complete",
      "uri": "https://hostname:3780/reports/..."
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

## 11. Report History

# Report History

**Endpoint:** `GET /api/3/reports/{id}/history/{instance}`

## Description
Returns the details for a generation of the report.

**Operation ID:** `getReportInstance`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

### Parameter 2
**Name:** `instance`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the report instance.

## Responses

### 200
**Description:** OK
**Schema:** `ReportInstance`
**Example JSON Response:**
```json
{
  "generated": "2018-06-01T18:56:03Z",
  "id": 5,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "size": {
    "bytes": 24789050,
    "formatted": "23.6 MB"
  },
  "status": "complete",
  "uri": "https://hostname:3780/reports/..."
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

## 12. Report History

# Report History

**Endpoint:** `DELETE /api/3/reports/{id}/history/{instance}`

## Description
Deletes an instance of a generated report.

**Operation ID:** `deleteReportInstance`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

### Parameter 2
**Name:** `instance`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the report instance.

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

## 13. Report Download

# Report Download

**Endpoint:** `GET /api/3/reports/{id}/history/{instance}/output`

## Description
Returns the contents of a generated report. The report content is usually returned in a GZip compressed format.

**Operation ID:** `downloadReport`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the report.

### Parameter 2
**Name:** `instance`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the report instance.

## Responses

### 200
**Description:** OK
**Example JSON Response:**
```json
"string"
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
- `application/octet-stream`
- `application/json;charset=UTF-8`


---
