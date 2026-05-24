
<pre>
AWS ORGANIZATIONS
│
├── 1. CORE CONCEPTS
│   │
│   ├── Organization
│   ├── Management Account
│   ├── Member Accounts
│   ├── Root
│   ├── Organizational Units (OU)
│   ├── Policies
│   ├── Delegated Administrator
│   └── Handshakes
│
├── 2. FEATURE SETS
│   │
│   ├── Consolidated Billing
│   └── All Features
│
├── 3. ORGANIZATIONAL STRUCTURE
│   │
│   ├── Root
│   │
│   ├── Organizational Units (OUs)
│   │   │
│   │   ├── Nested OUs
│   │   ├── Environment-based
│   │   ├── Department-based
│   │   ├── Compliance-based
│   │   └── Security-based
│   │
│   └── AWS Accounts
│       │
│       ├── Account Isolation
│       ├── Account Lifecycle
│       ├── Account Metadata
│       └── Cross-account Access
│
├── 4. ACCOUNT MANAGEMENT
│   │
│   ├── Create Accounts
│   ├── Invite Existing Accounts
│   ├── Remove Accounts
│   ├── Close Accounts
│   └── OrganizationAccountAccessRole
│
├── 5. BILLING & COST MANAGEMENT
│   │
│   ├── Consolidated Billing
│   ├── Cost Allocation
│   ├── RI Sharing
│   ├── Savings Plans Sharing
│   ├── Chargeback
│   └── Showback
│
├── 6. SERVICE CONTROL POLICIES (SCP)
│   │
│   ├── SCP Fundamentals
│   │   │
│   │   ├── Maximum Permission Boundary
│   │   ├── Explicit Deny
│   │   ├── Allow Chain
│   │   └── FullAWSAccess
│   │
│   ├── SCP Design Patterns
│   │   │
│   │   ├── Restrict Regions
│   │   ├── Deny Root Usage
│   │   ├── Restrict IAM Changes
│   │   ├── Enforce MFA
│   │   ├── Deny Public S3
│   │   ├── Restrict Expensive Services
│   │   └── Deny Leaving Organization
│   │
│   ├── SCP Advanced Topics
│   │   │
│   │   ├── Condition Keys
│   │   ├── PrincipalOrgID
│   │   ├── Tag-based SCP
│   │   ├── Policy Inheritance
│   │   └── SCP Debugging
│   │
│   └── SCP Limitations
│
├── 7. RESOURCE CONTROL POLICIES (RCP)
│   │
│   ├── Resource Governance
│   ├── Resource Protection
│   ├── RCP vs SCP
│   └── Shared Resource Protection
│
├── 8. TAG POLICIES
│   │
│   ├── Tag Standardization
│   ├── Allowed Values
│   ├── Case Enforcement
│   ├── Cost Center Governance
│   └── Compliance Detection
│
├── 9. BACKUP POLICIES
│   │
│   ├── AWS Backup Integration
│   ├── Retention Policies
│   ├── Cross-region Backups
│   ├── Cross-account Backups
│   └── Compliance Retention
│
├── 10. AI SERVICES OPT-OUT POLICIES
│   │
│   ├── AI Training Opt-out
│   ├── Privacy Governance
│   └── Sensitive Data Protection
│
├── 11. CHAT APPLICATION POLICIES
│   │
│   ├── Slack Governance
│   ├── Teams Governance
│   ├── ChatOps Security
│   └── Access Restrictions
│
├── 12. SECURITY HUB POLICIES
│   │
│   ├── Centralized Security Governance
│   ├── Findings Aggregation
│   ├── Security Standards
│   └── Compliance Monitoring
│
├── 13. AMAZON INSPECTOR POLICIES
│   │
│   ├── Vulnerability Management
│   ├── EC2 Scanning
│   ├── ECR Scanning
│   └── Lambda Scanning
│
├── 14. AMAZON BEDROCK POLICIES
│   │
│   ├── AI Governance
│   ├── Model Restrictions
│   ├── Organizational AI Controls
│   └── AI Guardrails
│
├── 15. DELEGATED ADMINISTRATOR
│   │
│   ├── Security Hub
│   ├── GuardDuty
│   ├── AWS Config
│   ├── AWS Backup
│   ├── Inspector
│   └── IAM Identity Center
│
├── 16. ORGANIZATION APIs & AUTOMATION
│   │
│   ├── AWS CLI
│   ├── Organizations API
│   ├── SDKs
│   ├── CloudFormation
│   ├── Terraform
│   └── CDK
│
├── 17. SECURITY & GOVERNANCE
│   │
│   ├── Security OU
│   ├── Log Archive Account
│   ├── Audit Account
│   ├── Centralized Logging
│   ├── Root User Governance
│   └── Compliance Architecture
│
├── 18. AWS CONTROL TOWER
│   │
│   ├── Landing Zone
│   ├── Account Factory
│   ├── Guardrails
│   ├── Drift Detection
│   └── OU Management
│
├── 19. NETWORK GOVERNANCE
│   │
│   ├── Shared VPC
│   ├── Transit Gateway
│   ├── Centralized Networking
│   ├── Inspection VPC
│   └── Network Account
│
├── 20. ORGANIZATION-WIDE SERVICES
│   │
│   ├── CloudTrail Organization Trail
│   ├── AWS Config Aggregator
│   ├── GuardDuty Delegation
│   ├── Security Hub Delegation
│   ├── IAM Identity Center
│   └── AWS RAM
│
├── 21. CROSS-ACCOUNT ACCESS
│   │
│   ├── IAM Roles
│   ├── AssumeRole
│   ├── PrincipalOrgID
│   ├── OrganizationAccountAccessRole
│   └── Trusted Access
│
├── 22. POLICY MANAGEMENT
│   │
│   ├── Create Policies
│   ├── Attach Policies
│   ├── Detach Policies
│   ├── Delete Policies
│   ├── Policy Versioning
│   └── Policy Testing
│
├── 23. IaC & DEVOPS
│   │
│   ├── Terraform
│   ├── GitOps
│   ├── Account Vending
│   ├── CI/CD Governance
│   └── Organizational Automation
│
├── 24. MONITORING & AUDITING
│   │
│   ├── CloudTrail
│   ├── AWS Config
│   ├── Audit Manager
│   ├── EventBridge
│   └── Detective
│
├── 25. BEST PRACTICES
│   │
│   ├── Multi-account Strategy
│   ├── Least Privilege
│   ├── OU Design
│   ├── SCP Strategy
│   ├── Centralized Security
│   └── Sandbox Isolation
│
├── 26. LIMITS & QUOTAS
│   │
│   ├── OU Limits
│   ├── Account Limits
│   ├── SCP Size Limits
│   ├── API Throttling
│   └── Nested OU Limits
│
├── 27. TROUBLESHOOTING
│   │
│   ├── SCP Debugging
│   ├── Access Denied Analysis
│   ├── Account Creation Failures
│   ├── Delegated Admin Issues
│   └── Organization Invitation Issues
│
├── 28. ENTERPRISE ARCHITECTURE
│   │
│   ├── Landing Zone Design
│   ├── Enterprise Governance
│   ├── Regulated Environments
│   ├── Multi-region Governance
│   └── Global Organization Strategy
│
└── 29. ADVANCED ENTERPRISE TOPICS
    │
    ├── Organizations + IAM Identity Center
    ├── Organizations + Control Tower
    ├── Organizations + Security Lake
    ├── Organizations + GuardDuty
    ├── Organizations + AWS Config
    ├── Organizations + AWS Backup
    └── Organizations + Bedrock Governance
</pre>