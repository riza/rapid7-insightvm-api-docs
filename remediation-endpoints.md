# Remediation Endpoints

## Description
Resources for determining the details required to remediate vulnerabilities.

This document contains 1 endpoints under the Remediation tag.

---

## 1. Asset Vulnerability Solution

# Asset Vulnerability Solution

**Endpoint:** `GET /api/3/assets/{id}/vulnerabilities/{vulnerabilityId}/solution`

## Description
Returns the highest-superceding rollup solutions for a vulnerability on an asset. The solution(s) selected will be the most recent and cost-effective means by which the vulnerability can be remediated.

**Operation ID:** `getAssetVulnerabilitySolutions`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** integer
**Required:** Yes
**Description:** The identifier of the asset.

### Parameter 2
**Name:** `vulnerabilityId`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the vulnerability.

## Responses

### 200
**Description:** OK
**Schema:** `Resources«MatchedSolution»`
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
      "additionalInformation": {
        "html": "",
        "text": ""
      },
      "appliesTo": "libexpat1 on Ubuntu Linux",
      "confidence": "",
      "estimate": "PT10M",
      "id": "ubuntu-upgrade-libexpat1",
      "links": [
        {
          "href": "https://hostname:3780/api/3/...",
          "rel": "self"
        }
      ],
      "matches": [
        {
          "check": "",
          "confidence": "",
          "fingerprint": {
            "description": "Ubuntu libexpat1 2.1.0-4ubuntu1.2",
            "family": "",
            "product": "libexpat1",
            "vendor": "Ubuntu",
            "version": "2.1.0-4ubuntu1.2"
          },
          "links": [
            {
              "href": "https://hostname:3780/api/3/...",
              "rel": "self"
            }
          ],
          "solution": "ubuntu-upgrade-libexpat1",
          "type": "software"
        }
      ],
      "steps": {
        "html": "<p>\n    Use `apt-get upgrade` to upgrade libexpat1 to the latest version.\n  </p>",
        "text": "Use `apt-get upgrade` to upgrade libexpat1 to the latest version."
      },
      "summary": {
        "html": "Upgrade libexpat1",
        "text": "Upgrade libexpat1"
      },
      "type": "configuration"
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
