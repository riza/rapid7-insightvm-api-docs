# Policy Override Endpoints

## Description
Policy Override Resource Controller

This document contains 8 endpoints under the Policy Override tag.

---

## 1. Asset Policy Overrides

# Asset Policy Overrides

**Endpoint:** `GET /api/3/assets/{id}/policy_overrides`

## Description
Retrieves policy overrides defined on policy rules for the specified asset.

**Operation ID:** `getAssetPolicyOverrides`

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
**Schema:** `Resources«PolicyOverride»`
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
      "expires": "",
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "review": {
        "comment": "",
        "date": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "user": ""
      },
      "scope": {
        "asset": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "newResult": "",
        "originalResult": "",
        "rule": "",
        "type": ""
      },
      "state": "",
      "submit": {
        "comment": "",
        "date": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "user": ""
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

## 2. Policy Overrides

# Policy Overrides

**Endpoint:** `GET /api/3/policy_overrides`

## Description
Retrieves policy overrides defined on policy rules.

**Operation ID:** `getPolicyOverrides`

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
**Schema:** `PageOf«PolicyOverride»`
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
      "expires": "",
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "review": {
        "comment": "",
        "date": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "user": ""
      },
      "scope": {
        "asset": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "newResult": "",
        "originalResult": "",
        "rule": "",
        "type": ""
      },
      "state": "",
      "submit": {
        "comment": "",
        "date": "",
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "user": ""
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

## 3. Policy Overrides

# Policy Overrides

**Endpoint:** `POST /api/3/policy_overrides`

## Description
Submit a policy override. The policy override can be submitted or it can be submitted and approved in a single request.

**Operation ID:** `createPolicyOverride`

## Parameters

### Parameter 1
**Name:** `policyOverride`
**Location:** body
**Type:** PolicyOverride
**Required:** No
**Description:** The specification of a policy override. Allows users to override the compliance result of a policy rule.
**JSON Example:**
```json
{
  "expires": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "review": {
    "comment": "",
    "date": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "user": ""
  },
  "scope": {
    "asset": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "newResult": "",
    "originalResult": "",
    "rule": "",
    "type": ""
  },
  "state": "",
  "submit": {
    "comment": "",
    "date": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "user": ""
  }
}
```

## Request Body
**Name:** `policyOverride`
**Location:** body
**Type:** PolicyOverride
**Required:** No
**Description:** The specification of a policy override. Allows users to override the compliance result of a policy rule.
**JSON Example:**
```json
{
  "expires": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "review": {
    "comment": "",
    "date": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "user": ""
  },
  "scope": {
    "asset": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "newResult": "",
    "originalResult": "",
    "rule": "",
    "type": ""
  },
  "state": "",
  "submit": {
    "comment": "",
    "date": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "user": ""
  }
}
```

## Responses

### 200
**Description:** OK
**Schema:** `CreatedReference«PolicyOverrideID,Link»`
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

## 4. Policy Override

# Policy Override

**Endpoint:** `GET /api/3/policy_overrides/{id}`

## Description
Retrieve the specified policy override.

**Operation ID:** `getPolicyOverride`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy override.

## Responses

### 200
**Description:** OK
**Schema:** `PolicyOverride`
**Example JSON Response:**
```json
{
  "expires": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "review": {
    "comment": "",
    "date": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "user": ""
  },
  "scope": {
    "asset": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "newResult": "",
    "originalResult": "",
    "rule": "",
    "type": ""
  },
  "state": "",
  "submit": {
    "comment": "",
    "date": "",
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "user": ""
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

## 5. Policy Override

# Policy Override

**Endpoint:** `DELETE /api/3/policy_overrides/{id}`

## Description
Removes a policy override created for a policy rule.

**Operation ID:** `deletePolicyOverride`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy override.

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

## 6. Policy Override Expiration

# Policy Override Expiration

**Endpoint:** `GET /api/3/policy_overrides/{id}/expires`

## Description
Get the expiration date for a policy override.

**Operation ID:** `getPolicyOverrideExpiration`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy override.

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
- `application/json;charset=UTF-8`


---

## 7. Policy Override Expiration

# Policy Override Expiration

**Endpoint:** `PUT /api/3/policy_overrides/{id}/expires`

## Description
Set the expiration date for a policy override. This must be a valid date in the future.

**Operation ID:** `setPolicyOverrideExpiration`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy override.

### Parameter 2
**Name:** `expiration`
**Location:** body
**Type:** string
**Required:** No
**Description:** The date the policy override is set to expire. Date is represented in ISO 8601 format.
**JSON Example:**
```json
"string"
```

## Request Body
**Name:** `expiration`
**Location:** body
**Type:** string
**Required:** No
**Description:** The date the policy override is set to expire. Date is represented in ISO 8601 format.
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

## 8. Policy Override Status

# Policy Override Status

**Endpoint:** `POST /api/3/policy_overrides/{id}/{status}`

## Description
Update the status of the specified policy override. The status can be one of the following: `"recall"`, `"approve"`, or `"reject"`.

**Operation ID:** `setPolicyOverrideStatus`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy override.

### Parameter 2
**Name:** `status`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** Policy Override Status

### Parameter 3
**Name:** `comment`
**Location:** body
**Type:** string
**Required:** No
**Description:** A comment describing the change of the policy override status.
**JSON Example:**
```json
"string"
```

## Request Body
**Name:** `comment`
**Location:** body
**Type:** string
**Required:** No
**Description:** A comment describing the change of the policy override status.
**JSON Example:**
```json
"string"
```

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
