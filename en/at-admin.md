# User Guide - Tax Authority Administrator

TIN Validation System - CRS-CIAT

> For authorized users only.

Previous Guides: [Access Guide](./access.md)

### Access to the Technical API Integration Guide

To integrate your system with the TIN validation API (authentication using x.509 certificates, OAuth token retrieval, and API calls), refer to the [API Guide](./api.md).

This guide includes:
- Step-by-step instructions for generating and registering certificates
- Complete reference Python script
- Examples of calls to production and test endpoints
- Specific troubleshooting for common errors (401, invalid issuer, etc.)

**Important**: This guide contains sensitive technical details of the authentication flow. Do not share it externally or publish it on public sites.

## Statistics
You can generate reports using the various filters: report type, start date, end date, period level, destination country, origin country. You can only view data where the country is involved as Origin or Destination.

### Steps
1. Navigate to the "Statistics" section in the main menu.
2. Choose the different filters available.
3. Click "Generate Report" - the requested information will be displayed.
4. You can "Download" the Report.

![Statistics](AT_ADMIN_StatisticsAdmin_01.png)

## Upload Certificate
The administrator must enter the client's data as well as the certificate according to the requested specifications. They can also update the certificate once created.

### Process for uploading a public certificate:

1. Navigate to the "Upload Certificate" section in the main menu.
2. Enter the Client Name.
3. Enter the Client Email.
4. Select the `public_cert.pem` file.
5. Verify that the certificate is valid.
6. Click "Register Client".

![Upload Certificate](AT_ADMIN_UploadCertificate_01.png)

## Manage Users
The administrator can create new users or edit the data of existing users. They can also disable users.

### Create a new user:

1. Go to "User Management"
2. Complete the information in "Create New User" with the required fields:
   - First Name
   - Last Name
   - Email Address
   - Password
   - Confirm Password
3. Click "Create User"

![Manage Users](AT_ADMIN_ManageUser_01.png)

### Modify an existing user:

1. Go to "User Management"
2. Click "Edit" on an existing user, enter the information to modify:
   - First Name
   - Last Name
   - Email Address
3. Click "Save Changes"

![Manage Users](AT_ADMIN_ManageUser_EditUser_01.png)

## API Configuration

1. Navigate to "API Configuration"
2. Enter URL
3. Choose Format JSON, XML, CSV
4. Save configuration

![API Configuration](AT_ADMIN_APIConfiguration_01.png)

### Maintenance Window 

1. Navigate to "API Configuration"
2. Swipe to open Maintenance Window
3. Choose start date
4. Choose end date
5. Write Note
6. Save

![Maintenance Window](AT_ADMIN_MaintenanceWindow_01.png) 



### Scheduled maintenance email

The system will send an email with the scheduled maintenance information to all registered country administrators. Additionally, it will schedule a reminder email if the maintenance is due to begin within the next 24 hours.

![Maintenance Window](AT_ADMIN_EmailMaintenanceWindow_01.png) 

![Maintenance Window](AT_ADMIN_EmailOMaintenanceWindow_01.png) 





---

*For technical assistance, contact the support team: support.tinvalidator@ciat.org*
