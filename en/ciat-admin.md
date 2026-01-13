# User Guide - CIAT Administrator

TIN Validation System - CRS-CIAT

> This guide is intended for authorized users only.

## Quick Navigation

- [Statistics](#statistics)
- [Manage Countries](#manage-countries)
- [Country Level Definitions](#country-level-definitions)
- [Level 1 Rules Config](#level-1-rules-config)
- [System Health](#system-health)

## Statistics

### Overview Dashboard
The statistics dashboard provides real-time insights into system usage and performance.

### Key Metrics:
- **Total Validations**: Number of TINs validated (daily, weekly, monthly)
- **Success Rate**: Percentage of successful validations
- **Country Activity**: Validation volume by participating country
- **API Usage**: Number of API calls vs web interface usage
- **Peak Hours**: System load patterns throughout the day

### Generating Reports:
1. Navigate to "Statistics" → "Reports"
2. Select report type (Summary, Detailed, Custom)
3. Choose date range
4. Select countries (optional)
5. Click "Generate Report"
6. Export to PDF, Excel, or CSV

### Real-time Monitoring:
- Live validation counter
- API response time graphs
- Error rate monitoring
- User activity tracking

## Manage Countries

### Adding a New Country:
1. Go to "Countries" → "Add New Country"
2. Enter country information:
   - Country Code (ISO 3166-1 alpha-2)
   - Country Name (official name)
   - Tax Authority Name
   - Contact Information
   - Status (Active/Inactive)
3. Upload country flag/logo (optional)
4. Click "Save"

### Country Status Management:
- **Active**: Country can participate in validations
- **Inactive**: Country temporarily suspended
- **Pending**: Awaiting approval/configuration
- **Retired**: No longer participating

### Bulk Operations:
- Import country list via CSV
- Update multiple countries simultaneously
- Export country configuration

## Country Level Definitions

### Agreement Types:
1. **Bilateral Agreements**: Direct validation between two countries
2. **Multilateral Agreements**: Multiple countries under common framework
3. **Unilateral Access**: Country can validate but not be validated

### Setting Up Agreements:
1. Select "Agreements" from main menu
2. Choose agreement type
3. Select participating countries
4. Define validation levels (1, 2, or 3)
5. Set effective dates
6. Configure notification rules

### Validation Levels:
- **Level 1**: Format validation only
- **Level 2**: Basic existence check
- **Level 3**: Full validation with taxpayer details

### Agreement Monitoring:
- Track agreement expiration dates
- Monitor usage against quotas
- Generate compliance reports
- Send renewal reminders

## Level 1 Rules Config

### Rule Types:
1. **Format Rules**: TIN structure validation
2. **Check Digit Rules**: Mathematical validation
3. **Length Rules**: Minimum/maximum character count
4. **Pattern Rules**: Regular expression matching

### Creating Format Rules:

Rule Name: US_TIN_Format
Country: United States
Rule Type: Pattern
Pattern: ^[0-9]{3}-[0-9]{2}-[0-9]{4}$
Description: Validates XXX-XX-XXXX format


### Rule Priority:
1. Country-specific rules
2. Regional rules (if applicable)
3. Global default rules

### Testing Rules:
1. Go to "Rules" → "Test Rules"
2. Enter test TINs
3. Select country
4. Run validation
5. Review results and rule application

### Rule Maintenance:
- Version control for rule changes
- Audit trail of modifications
- Rollback capability
- Scheduled rule updates

## System Health

### Monitoring Dashboard:
- **System Uptime**: Current and historical availability
- **API Performance**: Response times and success rates
- **Database Health**: Connection status and performance
- **Server Resources**: CPU, memory, and disk usage
- **Network Status**: Connectivity and latency

### Health Checks:
1. **Database Connectivity**: Verify all database connections
2. **API Endpoints**: Test all API endpoints
3. **External Services**: Check third-party integrations
4. **Certificate Validity**: Verify SSL/TLS certificates
5. **Backup Status**: Confirm backup completion

### Alert Configuration:
1. Navigate to "Health" → "Alerts"
2. Set thresholds for:
   - CPU usage (>80%)
   - Memory usage (>85%)
   - Disk space (<10% free)
   - API errors (>5% error rate)
   - Response time (>5 seconds)
3. Configure notification channels:
   - Email alerts
   - SMS notifications
   - Dashboard warnings

### Maintenance Tasks:
- **Daily**: Log rotation, temporary file cleanup
- **Weekly**: Database optimization, report generation
- **Monthly**: Full system backup, certificate renewal checks
- **Quarterly**: Security audit, performance review

### Incident Response:
1. **Detection**: System alerts or user reports
2. **Assessment**: Determine severity and scope
3. **Containment**: Isolate affected components
4. **Resolution**: Apply fixes or workarounds
5. **Recovery**: Restore normal operations
6. **Review**: Analyze root cause and prevent recurrence

---

*For system emergencies, contact CIAT technical support immediately: ciat.emergency@ciat.org*