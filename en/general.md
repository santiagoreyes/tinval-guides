# User Guide

TIN Validation System - CRS-CIAT

> This guide is intended for authorized users only.

## Quick Navigation

- [Getting Started](#getting-started)
- [Validation Process](#validation-process)  
- [FAQ](#faq)

## Getting Started

### How does Tin Validator Work
- Cloud based system managed by Ciat
- Countries can enroll to use the system by following the defined process.
- The countries can validate batches of Tins using an API endpoint or a Web interface.

### How Does Security Work
- API security is based on Oauth2 with Self Signed Certificates
- Web security is based on login and secure password.

### Who can access the System
- Country Administration user, for managing users, upload public certificate, defining url API endpoints.
- API users (based on token access), for validating batchs of Tins.
- Web users, for validating individual Tins, batch of Tins, and view validation results.
- Ciat Administrator, for system administration and configuration tasks, also for viewing statistics.

## Validation Process

### Step-by-Step Guide
*(Add your detailed steps here)*

## Frequently Asked Questions

### What File Formats are supported?
The system supports XML, JSON and csv

### How long does validation take?
Typical validation time is 0.2-0.3 seconds per TIN. Batch processing of 1000 TINs usually completes within 3-4 minutes. As Level 2 and 3 validation depends on provider countries, the response time may vary.

---

*For more detailed guides, please login and access role-specific documentation.*