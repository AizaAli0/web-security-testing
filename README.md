# Web Security Testing

## Overview

A practical web application security assessment performed against a locally hosted OWASP Juice Shop instance.
The goal was to practice the basic VAPT workflow:

**Reconnaissance → Testing → Evidence Collection → Analysis → Reporting**

---

## Target

**Application:** OWASP Juice Shop  
**Environment:** Localhost  
**Target URL:** `http://localhost:3000`  
**Target Type:** Intentionally Vulnerable Web Application

Testing was performed in a controlled local environment.

---

## Objectives

- Understand web application functionality
- Inspect HTTP requests and responses
- Identify API endpoints
- Test authentication behavior
- Test authorization and access control
- Test input validation
- Investigate XSS
- Test file upload validation
- Analyze error handling
- Document confirmed vulnerabilities and security controls

---

## Tools

- Google Chrome
- Chrome Developer Tools
- OWASP Juice Shop
- Manual HTTP request analysis

---

### Reconnaissance

Explored:

- Login and registration
- User profile
- Search
- Shopping basket
- Password recovery
- File upload
- API communication

### Authentication

Tested invalid credentials and observed generic authentication errors.

**Result:** No basic account-enumeration issue identified.

### Authorization

Tested basket object references between two local accounts.

**Result:** Cross-account access was rejected.

### Input Validation

Tested special characters and HTML/JavaScript payloads through search functionality.

### File Upload

Tested:

- JPG
- PNG
- TXT
- TXT renamed as JPG

The renamed text file was rejected.

### Business Logic

Tested basket quantity limits.

Observed range:

```text
1–5
