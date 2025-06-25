# Credential Endpoints

## Description
Resources and operations for managing shared credentials.

This document contains 6 endpoints under the Credential tag.

---

## 1. Shared Credentials

# Shared Credentials

**Endpoint:** `GET /api/3/shared_credentials`

## Description
Retrieves all defined shared credential resources.

**Operation ID:** `getSharedCredentials`

## Responses

### 200
**Description:** OK
**Schema:** `Resources«SharedCredential»`
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
        "authenticationType": "string",
        "communityName": "string",
        "database": "string",
        "domain": "string",
        "enumerateSids": true,
        "notesIDPassword": "string",
        "ntlmHash": "string",
        "oracleListenerPassword": "string",
        "password": "string",
        "pemKey": "string",
        "permissionElevation": "string",
        "permissionElevationPassword": "string",
        "permissionElevationUsername": "string",
        "privacyPassword": "string",
        "privacyType": "string",
        "privateKeyPassword": "string",
        "realm": "string",
        "service": "string",
        "serviceName": "string",
        "sid": "string",
        "useWindowsAuthentication": true,
        "username": "string"
      },
      "description": "",
      "hostRestriction": "",
      "id": "",
      "name": "",
      "portRestriction": "",
      "siteAssignment": "",
      "sites": [
        42
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

## 2. Shared Credentials

# Shared Credentials

**Endpoint:** `POST /api/3/shared_credentials`

## Description
Creates a new shared credential.

**Operation ID:** `createSharedCredential`

## Parameters

### Parameter 1
**Name:** `credential`
**Location:** body
**Type:** SharedCredential
**Required:** No
**Description:** The specification of a shared credential.
**JSON Example:**
```json
{
  "account": {
    "authenticationType": "string",
    "communityName": "string",
    "database": "string",
    "domain": "string",
    "enumerateSids": true,
    "notesIDPassword": "string",
    "ntlmHash": "string",
    "oracleListenerPassword": "string",
    "password": "string",
    "pemKey": "string",
    "permissionElevation": "string",
    "permissionElevationPassword": "string",
    "permissionElevationUsername": "string",
    "privacyPassword": "string",
    "privacyType": "string",
    "privateKeyPassword": "string",
    "realm": "string",
    "service": "string",
    "serviceName": "string",
    "sid": "string",
    "useWindowsAuthentication": true,
    "username": "string"
  },
  "description": "",
  "hostRestriction": "",
  "id": "",
  "name": "",
  "portRestriction": "",
  "siteAssignment": "",
  "sites": [
    42
  ]
}
```

## Request Body
**Name:** `credential`
**Location:** body
**Type:** SharedCredential
**Required:** No
**Description:** The specification of a shared credential.
**JSON Example:**
```json
{
  "account": {
    "authenticationType": "string",
    "communityName": "string",
    "database": "string",
    "domain": "string",
    "enumerateSids": true,
    "notesIDPassword": "string",
    "ntlmHash": "string",
    "oracleListenerPassword": "string",
    "password": "string",
    "pemKey": "string",
    "permissionElevation": "string",
    "permissionElevationPassword": "string",
    "permissionElevationUsername": "string",
    "privacyPassword": "string",
    "privacyType": "string",
    "privateKeyPassword": "string",
    "realm": "string",
    "service": "string",
    "serviceName": "string",
    "sid": "string",
    "useWindowsAuthentication": true,
    "username": "string"
  },
  "description": "",
  "hostRestriction": "",
  "id": "",
  "name": "",
  "portRestriction": "",
  "siteAssignment": "",
  "sites": [
    42
  ]
}
```

## Responses

### 200
**Description:** OK
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

## 3. Shared Credentials

# Shared Credentials

**Endpoint:** `DELETE /api/3/shared_credentials`

## Description
Deletes all shared credentials.

**Operation ID:** `deleteAllSharedCredentials`

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

## 4. Shared Credential

# Shared Credential

**Endpoint:** `GET /api/3/shared_credentials/{id}`

## Description
Retrieves the specified shared credential.

**Operation ID:** `getSharedCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the credential.

## Responses

### 200
**Description:** OK
**Schema:** `SharedCredential`
**Example JSON Response:**
```json
{
  "account": {
    "authenticationType": "string",
    "communityName": "string",
    "database": "string",
    "domain": "string",
    "enumerateSids": true,
    "notesIDPassword": "string",
    "ntlmHash": "string",
    "oracleListenerPassword": "string",
    "password": "string",
    "pemKey": "string",
    "permissionElevation": "string",
    "permissionElevationPassword": "string",
    "permissionElevationUsername": "string",
    "privacyPassword": "string",
    "privacyType": "string",
    "privateKeyPassword": "string",
    "realm": "string",
    "service": "string",
    "serviceName": "string",
    "sid": "string",
    "useWindowsAuthentication": true,
    "username": "string"
  },
  "description": "",
  "hostRestriction": "",
  "id": "",
  "name": "",
  "portRestriction": "",
  "siteAssignment": "",
  "sites": [
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

## 5. Shared Credential

# Shared Credential

**Endpoint:** `PUT /api/3/shared_credentials/{id}`

## Description
Updates the specified shared credential.

**Operation ID:** `updateSharedCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the credential.

### Parameter 2
**Name:** `credential`
**Location:** body
**Type:** SharedCredential
**Required:** No
**Description:** The specification of the shared credential to update.
**JSON Example:**
```json
{
  "account": {
    "authenticationType": "string",
    "communityName": "string",
    "database": "string",
    "domain": "string",
    "enumerateSids": true,
    "notesIDPassword": "string",
    "ntlmHash": "string",
    "oracleListenerPassword": "string",
    "password": "string",
    "pemKey": "string",
    "permissionElevation": "string",
    "permissionElevationPassword": "string",
    "permissionElevationUsername": "string",
    "privacyPassword": "string",
    "privacyType": "string",
    "privateKeyPassword": "string",
    "realm": "string",
    "service": "string",
    "serviceName": "string",
    "sid": "string",
    "useWindowsAuthentication": true,
    "username": "string"
  },
  "description": "",
  "hostRestriction": "",
  "id": "",
  "name": "",
  "portRestriction": "",
  "siteAssignment": "",
  "sites": [
    42
  ]
}
```

## Request Body
**Name:** `credential`
**Location:** body
**Type:** SharedCredential
**Required:** No
**Description:** The specification of the shared credential to update.
**JSON Example:**
```json
{
  "account": {
    "authenticationType": "string",
    "communityName": "string",
    "database": "string",
    "domain": "string",
    "enumerateSids": true,
    "notesIDPassword": "string",
    "ntlmHash": "string",
    "oracleListenerPassword": "string",
    "password": "string",
    "pemKey": "string",
    "permissionElevation": "string",
    "permissionElevationPassword": "string",
    "permissionElevationUsername": "string",
    "privacyPassword": "string",
    "privacyType": "string",
    "privateKeyPassword": "string",
    "realm": "string",
    "service": "string",
    "serviceName": "string",
    "sid": "string",
    "useWindowsAuthentication": true,
    "username": "string"
  },
  "description": "",
  "hostRestriction": "",
  "id": "",
  "name": "",
  "portRestriction": "",
  "siteAssignment": "",
  "sites": [
    42
  ]
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

## 6. Shared Credential

# Shared Credential

**Endpoint:** `DELETE /api/3/shared_credentials/{id}`

## Description
Deletes the specified shared scan credential.

**Operation ID:** `deleteSharedCredential`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the credential.

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
