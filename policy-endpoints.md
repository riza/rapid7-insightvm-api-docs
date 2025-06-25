# Policy Endpoints

## Description
Resources and operations for managing policies.

This document contains 26 endpoints under the Policy tag.

---

## 1. Policies For Asset

# Policies For Asset

**Endpoint:** `GET /api/3/assets/{assetId}/policies`

## Description
Retrieves the list of policies with compliance results for the specified asset.

**Operation ID:** `getPoliciesForAsset`

## Parameters

### Parameter 1
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `applicableOnly`
**Location:** query
**Type:** boolean
**Required:** No
**Description:** An optional boolean parameter indicating the policies retrieved should only include those with a policy compliance status of either a PASS of FAIL result. Default value is `false`, which will also include policies with a compliance status of NOT_APPLICABLE.

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
**Schema:** `PageOf«AssetPolicy»`
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
      "benchmarkName": "",
      "benchmarkVersion": "",
      "category": "",
      "description": "",
      "failedAssetsCount": "",
      "failedRulesCount": "",
      "id": "",
      "isCustom": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "notApplicableAssetsCount": "",
      "notApplicableRulesCount": "",
      "passedAssetsCount": "",
      "passedRulesCount": "",
      "policyName": "",
      "ruleCompliance": "",
      "ruleComplianceDelta": "",
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": "",
      "unscoredRules": ""
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

## 2. Policy Rules or Groups Directly Under Policy For Asset

# Policy Rules or Groups Directly Under Policy For Asset

**Endpoint:** `GET /api/3/assets/{assetId}/policies/{policyId}/children`

## Description
Retrieves a paged resource of either policy rules, or groups, that are defined directly underneath the specified policy with rule compliance results for the specified asset.

**Operation ID:** `getAssetPolicyChildren`

## Parameters

### Parameter 1
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«AssetPolicyItem»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "description": "",
      "hasOverride": false,
      "id": "",
      "isUnscored": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "policy": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "rules": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": "",
        "unscored": ""
      },
      "scope": "",
      "status": "",
      "title": "",
      "type": ""
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

## 3. Policy Rules or Groups Directly Under Policy Group For Asset

# Policy Rules or Groups Directly Under Policy Group For Asset

**Endpoint:** `GET /api/3/assets/{assetId}/policies/{policyId}/groups/{groupId}/children`

## Description
Retrieves a paged resource of either policy rules, or groups, that are defined directly underneath the specified policy group with rule compliance results for the specified asset.

**Operation ID:** `getAssetPolicyGroupChildren`

## Parameters

### Parameter 1
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 3
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«AssetPolicyItem»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "description": "",
      "hasOverride": false,
      "id": "",
      "isUnscored": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "policy": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "rules": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": "",
        "unscored": ""
      },
      "scope": "",
      "status": "",
      "title": "",
      "type": ""
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

## 4. Policy Rules Under Policy Group For Asset

# Policy Rules Under Policy Group For Asset

**Endpoint:** `GET /api/3/assets/{assetId}/policies/{policyId}/groups/{groupId}/rules`

## Description
Retrieves the list of policy rules defined directly, or indirectly, underneath the specified policy group and the compliance results for the specified asset.

**Operation ID:** `getPolicyGroupRulesWithAssetAssessment`

## Parameters

### Parameter 1
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 3
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

### Parameter 4
**Name:** `page`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The index of the page (zero-based) to retrieve.

### Parameter 5
**Name:** `size`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The number of records per page to retrieve.

### Parameter 6
**Name:** `sort`
**Location:** query
**Type:** array
**Required:** No
**Description:** The criteria to sort the records by, in the format: `property[,ASC|DESC]`. The default sort order is ascending. Multiple sort criteria can be specified using multiple sort query parameters.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«PolicyRule»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "benchmark": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "description": "",
      "id": "",
      "isCustom": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "role": "",
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": ""
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

## 5. Policy Rules For Asset

# Policy Rules For Asset

**Endpoint:** `GET /api/3/assets/{assetId}/policies/{policyId}/rules`

## Description
Retrieves the list of policy rules with compliance results for the specified asset and policy.

**Operation ID:** `getAssetPolicyRulesSummary`

## Parameters

### Parameter 1
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

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
**Schema:** `PageOf«PolicyRule»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "benchmark": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "description": "",
      "id": "",
      "isCustom": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "role": "",
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": ""
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

## 6. Policies

# Policies

**Endpoint:** `GET /api/3/policies`

## Description
Retrieves a paged resource of policies.

**Operation ID:** `getPolicies`

## Parameters

### Parameter 1
**Name:** `filter`
**Location:** query
**Type:** string
**Required:** No
**Description:** Filters the retrieved policies with those whose titles that match the parameter.

### Parameter 2
**Name:** `scannedOnly`
**Location:** query
**Type:** boolean
**Required:** No
**Description:** Flag indicating the policies retrieved should only include those with Pass or Fail compliance results. The list of scanned policies is based on the user's list of accessible assets.

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
**Schema:** `PageOf«Policy»`
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

## 7. Policy Rules or Groups Directly Under Policy

# Policy Rules or Groups Directly Under Policy

**Endpoint:** `GET /api/3/policies/{id}/children`

## Description
Retrieves a paged resource of either policy rules, or groups, that are defined directly underneath the specified policy.

**Operation ID:** `getPolicyChildren`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«PolicyItem»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "description": "",
      "hasOverride": false,
      "id": "",
      "isUnscored": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "policy": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "rules": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": "",
        "unscored": ""
      },
      "scope": "",
      "status": "",
      "title": "",
      "type": ""
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

## 8. Policy

# Policy

**Endpoint:** `GET /api/3/policies/{policyId}`

## Description
Retrieves the specified policy.

**Operation ID:** `getPolicy`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

## Responses

### 200
**Description:** OK
**Schema:** `Policy`
**Example JSON Response:**
```json
{
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

## 9. Policy Asset Results

# Policy Asset Results

**Endpoint:** `GET /api/3/policies/{policyId}/assets`

## Description
Retrieves asset resources with rule compliance results for the specified policy.

**Operation ID:** `getPolicyAssetResults`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `applicableOnly`
**Location:** query
**Type:** boolean
**Required:** No
**Description:** An optional boolean parameter indicating the assets retrieved should only include those with rule results of either PASS or FAIL. Default value is `false`, which will also include assets with a compliance status of NOT_APPLICABLE.

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
**Schema:** `PageOf«PolicyAsset»`
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
      "hostname": "",
      "id": "",
      "ip": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "os": {
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
      "status": ""
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

## 10. Policy Asset Result

# Policy Asset Result

**Endpoint:** `GET /api/3/policies/{policyId}/assets/{assetId}`

## Description
Retrieves an asset resource with rule compliance results for the specified asset and policy.

**Operation ID:** `getPolicyAssetResult`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `PolicyAsset`
**Example JSON Response:**
```json
{
  "hostname": "",
  "id": "",
  "ip": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "os": {
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

## 11. Policy Groups

# Policy Groups

**Endpoint:** `GET /api/3/policies/{policyId}/groups`

## Description
Retrieves a paged resource of policy groups for the specified policy.

**Operation ID:** `getPolicyGroups`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

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
**Schema:** `PageOf«PolicyGroup»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "benchmark": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "description": "",
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "policy": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": ""
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

## 12. Policy Group

# Policy Group

**Endpoint:** `GET /api/3/policies/{policyId}/groups/{groupId}`

## Description
Retrieves the specified policy group.

**Operation ID:** `getPolicyGroup`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

## Responses

### 200
**Description:** OK
**Schema:** `PolicyGroup`
**Example JSON Response:**
```json
{
  "assets": {
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "total": "",
    "totalFailed": "",
    "totalNotApplicable": "",
    "totalPassed": 42
  },
  "benchmark": {
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "title": "",
    "version": ""
  },
  "description": "",
  "id": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "policy": {
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "title": "",
    "version": ""
  },
  "scope": "",
  "status": "",
  "surrogateId": "",
  "title": ""
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

## 13. Assets Compliance For Policy Rules Under Policy Group

# Assets Compliance For Policy Rules Under Policy Group

**Endpoint:** `GET /api/3/policies/{policyId}/groups/{groupId}/assets`

## Description
Retrieves asset resources with rule compliance status against all rules under the specified policy group.

**Operation ID:** `getPolicyGroupAssetResults`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

### Parameter 3
**Name:** `applicableOnly`
**Location:** query
**Type:** boolean
**Required:** No
**Description:** An optional boolean parameter indicating the assets retrieved should only include those with rule results of either PASS or FAIL. Default value is `false`, which will also include assets with a compliance status of NOT_APPLICABLE.

### Parameter 4
**Name:** `page`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The index of the page (zero-based) to retrieve.

### Parameter 5
**Name:** `size`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The number of records per page to retrieve.

### Parameter 6
**Name:** `sort`
**Location:** query
**Type:** array
**Required:** No
**Description:** The criteria to sort the records by, in the format: `property[,ASC|DESC]`. The default sort order is ascending. Multiple sort criteria can be specified using multiple sort query parameters.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«PolicyAsset»`
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
      "hostname": "",
      "id": "",
      "ip": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "os": {
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
      "status": ""
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

## 14. Asset Compliance For Policy Rules Under Policy Group

# Asset Compliance For Policy Rules Under Policy Group

**Endpoint:** `GET /api/3/policies/{policyId}/groups/{groupId}/assets/{assetId}`

## Description
Retrieves an asset resource with rule compliance status against all rules under the specified policy group.

**Operation ID:** `getPolicyGroupAssetResult`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

### Parameter 3
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `PolicyAsset`
**Example JSON Response:**
```json
{
  "hostname": "",
  "id": "",
  "ip": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "os": {
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

## 15. Policy Rules or Groups Directly Under Policy Group

# Policy Rules or Groups Directly Under Policy Group

**Endpoint:** `GET /api/3/policies/{policyId}/groups/{groupId}/children`

## Description
Retrieves a paged resource of either policy rules, or groups, that are defined directly underneath the specified policy group.

**Operation ID:** `getPolicyGroupChildren`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«PolicyItem»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "description": "",
      "hasOverride": false,
      "id": "",
      "isUnscored": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "policy": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "rules": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": "",
        "unscored": ""
      },
      "scope": "",
      "status": "",
      "title": "",
      "type": ""
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

## 16. Policy Rules Under Policy Group

# Policy Rules Under Policy Group

**Endpoint:** `GET /api/3/policies/{policyId}/groups/{groupId}/rules`

## Description
Retrieves the list of policy rules defined directly, or indirectly, underneath the specified policy group.

**Operation ID:** `getDescendantPolicyRules`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `groupId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy group.

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
**Schema:** `PageOf«PolicyRule»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "benchmark": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "description": "",
      "id": "",
      "isCustom": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "role": "",
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": ""
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

## 17. Policy Rules

# Policy Rules

**Endpoint:** `GET /api/3/policies/{policyId}/rules`

## Description
Retrieves a paged resource of policy rules for the specified policy.

**Operation ID:** `getPolicyRules`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

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
**Schema:** `PageOf«PolicyRule»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "benchmark": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "description": "",
      "id": "",
      "isCustom": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "role": "",
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": ""
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

## 18. Disabled Policy Rules

# Disabled Policy Rules

**Endpoint:** `GET /api/3/policies/{policyId}/rules/disabled`

## Description
Retrieves a paged resource of disabled policy rules for the specified policy.

**Operation ID:** `getDisabledPolicyRules`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

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
**Schema:** `PageOf«PolicyRule»`
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
      "assets": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "total": "",
        "totalFailed": "",
        "totalNotApplicable": "",
        "totalPassed": 42
      },
      "benchmark": {
        "links": [
          {
            "href": "https://hostname:3780/api/3/...",
            "rel": "self"
          }
        ],
        "name": "",
        "title": "",
        "version": ""
      },
      "description": "",
      "id": "",
      "isCustom": false,
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "name": "",
      "role": "",
      "scope": "",
      "status": "",
      "surrogateId": "",
      "title": ""
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

## 19. Policy Rule

# Policy Rule

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}`

## Description
Retrieves the specified policy rule.

**Operation ID:** `getPolicyRule`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

## Responses

### 200
**Description:** OK
**Schema:** `PolicyRule`
**Example JSON Response:**
```json
{
  "assets": {
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "total": "",
    "totalFailed": "",
    "totalNotApplicable": "",
    "totalPassed": 42
  },
  "benchmark": {
    "links": [
      {
        "href": "https://hostname:3780/api/3/...",
        "rel": "self"
      }
    ],
    "name": "",
    "title": "",
    "version": ""
  },
  "description": "",
  "id": "",
  "isCustom": false,
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "name": "",
  "role": "",
  "scope": "",
  "status": "",
  "surrogateId": "",
  "title": ""
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

## 20. Assets Compliance For Policy Rule

# Assets Compliance For Policy Rule

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}/assets`

## Description
Retrieves asset resources with rule compliance results for the specified policy policy rule.

**Operation ID:** `getPolicyRuleAssetResults`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

### Parameter 3
**Name:** `applicableOnly`
**Location:** query
**Type:** boolean
**Required:** No
**Description:** An optional boolean parameter indicating the assets retrieved should only include those with rule results of either PASS or FAIL. Default value is `false`, which will also include assets with a compliance status of NOT_APPLICABLE.

### Parameter 4
**Name:** `page`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The index of the page (zero-based) to retrieve.

### Parameter 5
**Name:** `size`
**Location:** query
**Type:** integer
**Required:** No
**Description:** The number of records per page to retrieve.

### Parameter 6
**Name:** `sort`
**Location:** query
**Type:** array
**Required:** No
**Description:** The criteria to sort the records by, in the format: `property[,ASC|DESC]`. The default sort order is ascending. Multiple sort criteria can be specified using multiple sort query parameters.

## Responses

### 200
**Description:** OK
**Schema:** `PageOf«PolicyAsset»`
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
      "hostname": "",
      "id": "",
      "ip": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "os": {
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
      "status": ""
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

## 21. Asset Compliance For Policy Rule

# Asset Compliance For Policy Rule

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}/assets/{assetId}`

## Description
Retrieves an asset resource with rule compliance results for the specified policy policy rule.

**Operation ID:** `getPolicyRuleAssetResult`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

### Parameter 3
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

## Responses

### 200
**Description:** OK
**Schema:** `PolicyAsset`
**Example JSON Response:**
```json
{
  "hostname": "",
  "id": "",
  "ip": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "os": {
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

## 22. Policy Rule Proof For Asset

# Policy Rule Proof For Asset

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}/assets/{assetId}/proof`

## Description
Retrieves the policy rule proof captured during evaluation against the specified asset.

**Operation ID:** `getPolicyRuleAssetResultProof`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

### Parameter 3
**Name:** `assetId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

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
- `text/html`


---

## 23. Policy Rule Controls

# Policy Rule Controls

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}/controls`

## Description
Retrieves all NIST SP 800-53 controls mappings for each CCE within the specified policy rule.

**Operation ID:** `getPolicyRuleControls`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

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
**Schema:** `PageOf«PolicyControl»`
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
      "cceItemId": "",
      "ccePlatform": "",
      "controlName": "",
      "id": "",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "publishedDate": ""
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

## 24. Policy Rule Rationale

# Policy Rule Rationale

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}/rationale`

## Description
Retrieves the policy rule rationale for the specified policy.

**Operation ID:** `getPolicyRuleRationale`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

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
- `text/html`


---

## 25. Policy Rule Remediation

# Policy Rule Remediation

**Endpoint:** `GET /api/3/policies/{policyId}/rules/{ruleId}/remediation`

## Description
Retrieves the policy rule remediation for the specified policy.

**Operation ID:** `getPolicyRuleRemediation`

## Parameters

### Parameter 1
**Name:** `policyId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy

### Parameter 2
**Name:** `ruleId`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the policy rule.

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
- `text/html`


---

## 26. Policy Compliance Summaries

# Policy Compliance Summaries

**Endpoint:** `GET /api/3/policy/summary`

## Description
Retrieves a compliance summary of all policies.

**Operation ID:** `getPolicySummary`

## Responses

### 200
**Description:** OK
**Schema:** `PolicySummaryResource`
**Example JSON Response:**
```json
{
  "decreasedCompliance": "",
  "increasedCompliance": "",
  "links": [
    {
      "href": "https://hostname:3780/api/3/...",
      "rel": "self"
    }
  ],
  "numberOfPolicies": "",
  "overallCompliance": "",
  "scannedPolicies": ""
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
