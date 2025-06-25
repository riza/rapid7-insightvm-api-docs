# InsightVM API Documentation - Context7

This Context7 documentation provides comprehensive coverage of the Rapid7 InsightVM API v3, automatically generated from the official OpenAPI 2.0 specification.

## 📖 About InsightVM API

The InsightVM Application Programming Interface (API) v3 enables programmatic access to vulnerability management capabilities including:

- **Asset Management**: Discover, track, and manage IT assets
- **Vulnerability Assessment**: Scan and identify security vulnerabilities  
- **Risk Management**: Prioritize and track remediation efforts
- **Reporting**: Generate comprehensive security reports
- **Site Management**: Organize and configure scan targets
- **Policy Compliance**: Assess compliance with security policies

## 🏗️ API Architecture

- **REST Design**: Follows RESTful design patterns
- **JSON Format**: Uses `application/json` media type
- **HATEOAS**: Implements Hypermedia as the Engine of Application State
- **HTTPS Required**: All connections must use HTTPS
- **Authentication**: HTTP Basic Authentication with optional 2FA

## 📚 Documentation Structure

This Context7 documentation is organized into **20 functional modules**, each covering specific API capabilities:

### Core Management
- **[Administration](administration-endpoints.md)** - System administration operations (6 endpoints)
- **[Root](root-endpoints.md)** - API discovery and entry points (1 endpoint)

### Asset & Discovery
- **[Assets](asset-endpoints.md)** - Asset lifecycle management (25 endpoints)
- **[Asset Groups](asset-group-endpoints.md)** - Asset organization and grouping (22 endpoints)
- **[Asset Discovery](asset-discovery-endpoints.md)** - Automated asset discovery mechanisms (10 endpoints)
- **[Sites](site-endpoints.md)** - Scan target configuration and management (84 endpoints)

### Security & Scanning
- **[Scans](scan-endpoints.md)** - Scan execution and management (5 endpoints)
- **[Scan Engines](scan-engine-endpoints.md)** - Scan engine configuration (22 endpoints)
- **[Scan Templates](scan-template-endpoints.md)** - Scan configuration templates (5 endpoints)

### Vulnerability Management
- **[Vulnerabilities](vulnerability-endpoints.md)** - Vulnerability content and management (24 endpoints)
- **[Vulnerability Checks](vulnerability-check-endpoints.md)** - Vulnerability check definitions (4 endpoints)
- **[Vulnerability Results](vulnerability-result-endpoints.md)** - Assessment results and findings (7 endpoints)
- **[Vulnerability Exceptions](vulnerability-exception-endpoints.md)** - Exception management (7 endpoints)
- **[Remediation](remediation-endpoints.md)** - Remediation guidance and tracking (1 endpoint)

### Compliance & Policy
- **[Policies](policy-endpoints.md)** - Policy management and assessment (26 endpoints)
- **[Policy Overrides](policy-override-endpoints.md)** - Policy exception handling (8 endpoints)

### Reporting & Access
- **[Reports](report-endpoints.md)** - Report generation and distribution (13 endpoints)
- **[Users](user-endpoints.md)** - User management and permissions (32 endpoints)
- **[Credentials](credential-endpoints.md)** - Shared credential management (6 endpoints)
- **[Tags](tag-endpoints.md)** - Asset tagging and categorization (21 endpoints)

## 🎯 Documentation Features

Each endpoint documentation includes:

### Request Information
- **HTTP Method & Path**: Complete endpoint specification
- **Parameters**: Detailed parameter documentation with types and examples
- **Request Body**: JSON schema and examples for POST/PUT operations
- **Authentication**: Security requirements and permissions

### Response Information  
- **Status Codes**: All possible HTTP response codes
- **Response Schemas**: Complete data structure definitions
- **JSON Examples**: Auto-generated realistic response examples
- **Error Handling**: Detailed error response formats

### Technical Details
- **Content Types**: Supported request/response formats
- **Operation IDs**: Unique identifiers for code generation
- **Schema References**: Links to reusable data models

## 🔧 Technical Specifications

- **API Version**: v3
- **Base URL**: `https://<host>:<port>/api/3/`
- **OpenAPI Version**: 2.0 (Swagger)
- **Total Endpoints**: 328
- **Schema Definitions**: 315
- **Authentication**: HTTP Basic + Optional 2FA Token

## 🚀 Getting Started

1. **Authentication Setup**: Configure HTTP Basic Authentication credentials
2. **Base URL Configuration**: Set your InsightVM console URL
3. **API Discovery**: Start with the [Root endpoint](root-endpoints.md) to discover available resources
4. **Choose Module**: Select the appropriate documentation module for your use case

## 📋 Context7 Integration

This documentation is optimized for Context7 with:
- **Structured Navigation**: Organized by functional domains
- **Rich Examples**: Auto-generated JSON examples from OpenAPI schemas
- **Complete Coverage**: All 328 endpoints documented
- **Search-Friendly**: Detailed descriptions and parameter information
- **Developer-Ready**: Code generation compatible operation IDs

---

*Generated from InsightVM API v3 OpenAPI 2.0 specification with 315 schema definitions* 