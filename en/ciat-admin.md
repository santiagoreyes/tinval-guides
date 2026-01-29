# User Guide - CIAT Administrator

TIN Validation System - CRS-CIAT

> This guide is intended for authorized users only.

Previous Guides: [Access Guide](./access.md)

## Statistics
Statistics provides real-time information about system usage and performance.

### Generate Reports:
1. Navigate to "Statistics"
2. Select report type (Requested Data Volume, Requested Batches, Queries Made or Received, etc.).
3. Choose date range.
4. Choose Level (L1, L2, L3).
5. Choose Period.
6. Select countries: Origin country, Destination country, or all countries.
7. Click "Generate Report"
8. Export to PDF, Excel, or CSV

![Statistics Generate Reports](CIAT_ADMIN_GenerarReportes_01.png)

## Manage Countries

### Add New Country:
1. Go to "Manage Countries" → "Add New Country and Administrator User"
2. Select a Country:
   - Country Name (official name)
   - Tax Authority Name
   - Tax administration acronym
3. Create Administrator user
   - First Name
   - Last Name
   - Email address
   - Password and Confirmation
5. Click "Enroll"

![Manage Countries](CIAT_ADMIN_GestionarPaises_01.png)

### Available Options

- Modify administrator data.

![Manage Countries](CIAT_ADMIN_GestionarPaises_EditarAdmin_01.png)

- Change Administrator by removing the current one.

![Manage Countries](CIAT_ADMIN_GestionarPaises_CambiarAdmin_01.png)

## Country Level Definitions
Country Level Definitions can be:
1. Bilateral Agreements: Direct validation between two countries
2. Default: The country chooses a level to be validated
3. Minimum: The country chooses a minimum level to be validated

### Add New Definition
1. Select "Add New Definition"
2. Choose definition type
3. Select participating countries
4. Define validation levels (1, 2, or 3)
6. Click "Create"

![Level Definitions](CIAT_ADMIN_DefinicionesNivel_CrearDefinicion_01.png)

### Validation Levels:
- Level 1: Only format validation and Check Digit.
- Level 2: Validates number existence in registry and name match percentage.
- Level 3: Complete validation with taxpayer details.

## Level 1 Rules Configuration
Countries already added appear with their options for configuring Level 1 rules. These can be created, edited, and deleted.

### Rules Configuration:
1. Select the Country whose rules you want to configure
2. Click "Manage Rules"
3. Click "Add New Rules" and add Document Type, Person, Name.
4. Add the JSON rules and Test Case with the Test TINs.

![Rules Configuration](CIAT_ADMIN_ConfigurarL1_AddNewRule.png)

5. Test the Rule by clicking "Test Rule"
6. Click "Save Rule"

![Rules Configuration](CIAT_ADMIN_ConfigurarL1_AddNewRule_TestRule_01.png)

![Rules Configuration](CIAT_ADMIN_ConfigurarL1_AddNewRuleTest_01.png)

## System Health
System monitoring with tools such as:

### Monitoring of Country Endpoints:
- Active or inactive country endpoints.
Click "Verify EndPoints" to see the active or inactive endpoints that countries make available for verifying L2 and L3.

![System Health](CIAT_ADMIN_SaludSistema_Direcciones_01.png)

### Monitoring L1 Rules Validation
Click "Verify Rules" to see the defined test cases for TINs from different countries with their configured rules.

![System Health](CIAT_ADMIN_SaludSistema_ReglasValidadas_01.png)

### Monitoring Level Coverage Definitions:
Click "Get Coverage" to see the defined levels for different countries.

![System Health](CIAT_ADMIN_SaludSistema_DefinicionNiveles_01.png)

---

*For system emergencies, contact CIAT technical support immediately: ciat.emergencia@ciat.org*
