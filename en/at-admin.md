# User Guide - Tax Authority Administrator

TIN Validation System - CRS-CIAT

> For authorized users only.

## Quick Navigation

- [Statistics](#statistics)
- [Upload Certificate](#upload-certificate)
- [Manage Users](#manage-users)
- [API Configuration](#api-configuration)

## Statistics

*(Add your content, screenshots, steps, etc. here)*

## Upload Certificate

### Process to upload public certificate:

1. Navigate to "Certificates" section in main menu
2. Click "Upload Certificate"
3. Select the `public_cert.pem` file
4. Verify the certificate is valid
5. Click "Save"

### Certificate requirements:
- Format: PEM (Privacy Enhanced Mail)
- Algorithm: RSA with minimum 2048 bits
- Public certificate only (do not include private key)
- Maximum size: 5KB

### Certificate verification:
The system will automatically validate:
- Correct certificate format
- Expiration date (minimum 30 days validity)
- Valid RSA key structure

## Manage Users

### Create new user:

1. Go to "User Management"
2. Click "New User"
3. Complete required fields:
   - Full name
   - Email address
   - Role (Select: USER, AT_ADMIN, CIAT_ADMIN)
   - Assigned country
4. Click "Create User"

### Permissions by role:

- **USER**: Validate single and batch TINs, view results
- **AT_ADMIN**: Manage users, upload certificates, API configuration, view statistics
- **CIAT_ADMIN**: All system functions, global administration

### Reset password:

1. Find user in the list
2. Click "Actions" → "Reset Password"
3. System will generate a temporary password
4. Send new password to user via secure email

## API Configuration

### Available endpoints:

- **Single validation**: `POST /api/v1/validate/single`
- **Batch validation**: `POST /api/v1/validate/batch`
- **Results query**: `GET /api/v1/results/{id}`

### Configure rate limits:

1. Navigate to "API Configuration"
2. Set per-user limits:
   - Maximum requests per minute
   - Maximum TINs per batch
   - Maximum timeout
3. Save configuration

### API monitoring:

The system provides:
- Real-time usage metrics
- Error and access logs
- Overload alerts
- Daily/weekly/monthly activity reports

### Connection testing:

To verify API connectivity:
1. Go to "Tools" → "Connection Test"
2. Select endpoint to test
3. Click "Test Connection"
4. Verify response and response time

---

*For technical assistance, contact support team: support.tinvalidator@ciat.org*