# Scan Template Endpoints

## Description
Scan Template Resource Controller

This document contains 5 endpoints under the Scan Template tag.

---

## 1. Scan Templates

# Scan Templates

**Endpoint:** `GET /api/3/scan_templates`

## Description
Returns all scan templates.

**Operation ID:** `getScanTemplates`

## Responses

### 200
**Description:** OK
**Schema:** `Resources«ScanTemplate»`
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

## 2. Scan Templates

# Scan Templates

**Endpoint:** `POST /api/3/scan_templates`

## Description
Creates a new scan template.

**Operation ID:** `createScanTemplate`

## Parameters

### Parameter 1
**Name:** `scanTemplate`
**Location:** body
**Type:** ScanTemplate
**Required:** No
**Description:** The details of the scan template.
**JSON Example:**
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

## Request Body
**Name:** `scanTemplate`
**Location:** body
**Type:** ScanTemplate
**Required:** No
**Description:** The details of the scan template.
**JSON Example:**
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

## Responses

### 200
**Description:** OK
**Schema:** `CreatedReference«ScanTemplateID,Link»`
**Example JSON Response:**
```json
{
  "id": "1",
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

## 3. Scan Template

# Scan Template

**Endpoint:** `GET /api/3/scan_templates/{id}`

## Description
Returns a scan template.

**Operation ID:** `getScanTemplate`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the scan template

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

## 4. Scan Template

# Scan Template

**Endpoint:** `PUT /api/3/scan_templates/{id}`

## Description
Updates a scan template.

**Operation ID:** `updateScanTemplate`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the scan template

### Parameter 2
**Name:** `scanTemplate`
**Location:** body
**Type:** ScanTemplate
**Required:** No
**Description:** The details of the scan template.
**JSON Example:**
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

## Request Body
**Name:** `scanTemplate`
**Location:** body
**Type:** ScanTemplate
**Required:** No
**Description:** The details of the scan template.
**JSON Example:**
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

## 5. Scan Template

# Scan Template

**Endpoint:** `DELETE /api/3/scan_templates/{id}`

## Description
Deletes a scan template.

**Operation ID:** `deleteScanTemplate`

## Parameters

### Parameter 1
**Name:** `id`
**Location:** path
**Type:** string
**Required:** Yes
**Description:** The identifier of the scan template

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
