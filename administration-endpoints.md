# Administration Endpoints

## Description
Provides access administrative operations and procedures.

This document contains 6 endpoints under the Administration tag.

---

## 1. Console Commands

# Console Commands

**Endpoint:** `POST /api/3/administration/commands`

## Description
Executes a console command against the Security Console. Global Administrator

**Operation ID:** `executeCommand`

## Parameters

### Parameter 1
**Name:** `command`
**Location:** body
**Type:** string
**Required:** No
**Description:** The console command to execute.
**JSON Example:**
```json
"string"
```

## Request Body
**Name:** `command`
**Location:** body
**Type:** string
**Required:** No
**Description:** The console command to execute.
**JSON Example:**
```json
"string"
```

## Responses

### 200
**Description:** OK
**Schema:** `ConsoleCommandOutput`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "output": ""
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

## 2. Information

# Information

**Endpoint:** `GET /api/3/administration/info`

## Description
Returns system details, including host and version information.

**Operation ID:** `getInfo`

## Responses

### 200
**Description:** OK
**Schema:** `Info`
**Example JSON Response:**
```json
{
  "cpu": {
    "clockSpeed": 2600,
    "count": 8
  },
  "disk": {
    "free": {
      "bytes": 166532222976,
      "formatted": "155.1 GB"
    },
    "installation": {
      "backups": {
        "bytes": 0,
        "formatted": "0 bytes"
      },
      "database": {
        "bytes": 5364047843,
        "formatted": "5 GB"
      },
      "directory": "",
      "reports": {
        "bytes": 24789050,
        "formatted": "23.6 MB"
      },
      "scans": {
        "bytes": 1370433223,
        "formatted": "1.3 GB"
      },
      "total": {
        "bytes": 12125933077,
        "formatted": "11.3 GB"
      }
    },
    "total": {
      "bytes": 499004735488,
      "formatted": "464.7 GB"
    }
  },
  "distinguishedName": "CN=Rapid7 Security Console/ O=Rapid7",
  "fqdn": "server.acme.com",
  "host": "SERVER",
  "ip": "192.168.1.99",
  "jvm": {
    "name": "OpenJDK 64-Bit Server VM",
    "startTime": "2018-02-13T20:35:35.076Z",
    "uptime": "PT8H21M7.978S",
    "vendor": "Azul Systems, Inc.",
    "version": "25.102-b14"
  },
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "memory": {
    "free": {
      "bytes": 45006848,
      "formatted": "42.9 MB"
    },
    "total": {
      "bytes": 17179869184,
      "formatted": "16 GB"
    }
  },
  "operatingSystem": "Ubuntu Linux 16.04",
  "serial": "729F31B1C92F3C91DFA8A649F4D5C883C269BD45",
  "superuser": true,
  "user": "root",
  "version": {
    "build": "2017-12-10-14-11",
    "changeset": "7061fb4e7c355160df79a77d8983bed2af01f2bf",
    "platform": "Linux64",
    "semantic": "6.4.65",
    "update": {
      "content": "3192129162",
      "contentPartial": "723680177",
      "id": {
        "productId": "281474976711146",
        "versionId": "490"
      },
      "product": "2200922472"
    }
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

## 3. License

# License

**Endpoint:** `GET /api/3/administration/license`

## Description
Returns the enabled features and limits of the current license. Global Administrator

**Operation ID:** `getLicense`

## Responses

### 200
**Description:** OK
**Schema:** `License`
**Example JSON Response:**
```json
{
  "edition": "InsightVM",
  "evaluation": false,
  "expires": "2018-12-31T23:59:59.999Z",
  "features": {
    "adaptiveSecurity": false,
    "agents": true,
    "dynamicDiscovery": true,
    "earlyAccess": false,
    "enginePool": true,
    "insightPlatform": true,
    "mobile": true,
    "multitenancy": false,
    "policyEditor": true,
    "policyManager": true,
    "remediationAnalytics": true,
    "reporting": {
      "advanced": true,
      "customizableCSVExport": true,
      "pci": true
    },
    "scanning": {
      "discovery": true,
      "policy": {
        "benchmarks": {
          "cis": true,
          "custom": true,
          "disa": true,
          "fdcc": true,
          "usgcb": true
        },
        "scanning": true
      },
      "scada": true,
      "virtual": true,
      "webApplication": true
    }
  },
  "limits": {
    "assets": 100000,
    "assetsWithHostedEngine": 1000,
    "scanEngines": 100,
    "users": 1000
  },
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "perpetual": false,
  "status": "Activated"
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

## 4. License

# License

**Endpoint:** `POST /api/3/administration/license`

## Description
Licenses the product with an activation key or a provided license file. If both are provided, the license file is preferred. Global Administrator

**Operation ID:** `activateLicense`

## Parameters

### Parameter 1
**Name:** `license`
**Location:** formData
**Type:** file
**Required:** No
**Description:** The contents of a license (.lic) file.

### Parameter 2
**Name:** `key`
**Location:** query
**Type:** string
**Required:** No
**Description:** A license activation key.

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
- `multipart/form-data`

## Response Content-Type
- `application/json;charset=UTF-8`


---

## 5. Properties

# Properties

**Endpoint:** `GET /api/3/administration/properties`

## Description
Returns system details, including host and version information.

**Operation ID:** `getProperties`

## Responses

### 200
**Description:** OK
**Schema:** `EnvironmentProperties`
**Example JSON Response:**
```json
{
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "properties": {}
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

## 6. Settings

# Settings

**Endpoint:** `GET /api/3/administration/settings`

## Description
Returns the current administration settings. Global Administrator

**Operation ID:** `getSettings`

## Responses

### 200
**Description:** OK
**Schema:** `Settings`
**Example JSON Response:**
```json
{
  "assetLinking": true,
  "authentication": {
    "2fa": false,
    "loginLockThreshold": "true"
  },
  "database": {
    "connection": {
      "maximumAdministrationPoolSize": -1,
      "maximumPoolSize": -1,
      "maximumPreparedStatementPoolSize": 256
    },
    "host": "127.0.0.1",
    "maintenanceThreadPoolSize": 20,
    "port": 5432,
    "url": "//127.0.0.1:5432/nexpose",
    "user": "nxpgsql",
    "vendor": "postgresql"
  },
  "directory": "/opt/rapid7/nexpose",
  "insightPlatform": true,
  "insightPlatformRegion": "us-east-1",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "risk": {
    "adjustWithCriticality": true,
    "criticalityModifiers": {
      "high": 1.5,
      "low": 0.75,
      "medium": 1,
      "veryHigh": 2,
      "veryLow": 0.5
    },
    "model": "real_risk"
  },
  "scan": {
    "connectionTimeout": "PT15S",
    "incremental": true,
    "maximumThreads": -1,
    "readTimeout": "PT15M",
    "statusIdleTimeout": "PT3M",
    "statusThreads": 3
  },
  "serialNumber": "729F31B1C92F3C91DFA8A649F4D5C883C269BD45",
  "smtp": {
    "distributionId": "string",
    "host": "mail@acme.com",
    "port": 25,
    "sender": "security@acme.com"
  },
  "updates": {
    "contentAutoUpdate": true,
    "enabled": true,
    "productAutoUpdate": true
  },
  "uuid": "7231036a-e052-11e7-80c1-9a214cf093ae",
  "web": {
    "maxThreads": 100,
    "minThreads": 10,
    "port": 3780,
    "sessionTimeout": "PT10M"
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
