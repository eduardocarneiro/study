
<pre>
AWS CONTROL TOWER
│
├── 1. CORE CONCEPTS
│   │
│   ├── Landing Zone
│   │     ├── Multi-account AWS environment
│   │     ├── Governed environment
│   │     ├── Preconfigured security baseline
│   │     ├── Centralized logging and auditing
│   │     └── Built using AWS best practices
│   │
│   ├── Governance
│   │     ├── Preventive controls
│   │     ├── Detective controls
│   │     ├── Proactive controls
│   │     ├── Policy enforcement
│   │     └── Compliance monitoring
│   │
│   ├── Organizational Units (OUs)
│   │     ├── Security OU
│   │     ├── Sandbox OU
│   │     ├── Infrastructure OU
│   │     ├── Workloads OU
│   │     └── Custom OUs
│   │
│   ├── Accounts
│   │     ├── Management account
│   │     ├── Shared accounts
│   │     ├── Member accounts
│   │     ├── Enrolled accounts
│   │     └── Provisioned accounts
│   │
│   ├── Guardrails / Controls
│   │     ├── Mandatory
│   │     ├── Strongly recommended
│   │     ├── Elective
│   │     └── Region-specific controls
│   │
│   └── Drift
│         ├── Configuration drift
│         ├── OU drift
│         ├── Account drift
│         └── Landing zone repair
│
├── 2. LANDING ZONE ARCHITECTURE
│   │
│   ├── Management Account
│   │     ├── Billing owner
│   │     ├── Organization administrator
│   │     ├── Control Tower administrator
│   │     └── Central governance
│   │
│   ├── Shared Accounts
│   │     │
│   │     ├── Log Archive Account
│   │     │     ├── Centralized logs
│   │     │     ├── Immutable storage
│   │     │     ├── CloudTrail aggregation
│   │     │     └── Compliance retention
│   │     │
│   │     └── Audit Account
│   │           ├── Security audits
│   │           ├── Cross-account access
│   │           ├── Incident investigation
│   │           └── Security tooling
│   │
│   ├── AWS Organizations Integration
│   │     ├── Root
│   │     ├── OUs
│   │     ├── SCP integration
│   │     ├── Account lifecycle
│   │     └── Delegated administration
│   │
│   ├── Identity Integration
│   │     ├── AWS IAM Identity Center integration
│   │     ├── Centralized access management
│   │     ├── Permission sets
│   │     ├── Federated users
│   │     └── SSO access
│   │
│   └── Regional Governance
│         ├── Home Region
│         ├── Governed Regions
│         ├── Region deny controls
│         └── Multi-region operations
│
├── 3. CONTROL TYPES
│   │
│   ├── Preventive Controls
│   │     ├── Implemented using SCPs
│   │     ├── Prevent non-compliant actions
│   │     ├── Enforced before action occurs
│   │     └── Example:
│   │           ├── Disallow public S3 buckets
│   │           ├── Restrict regions
│   │           └── Restrict root usage
│   │
│   ├── Detective Controls
│   │     ├── Implemented using AWS Config Rules
│   │     ├── Detect policy violations
│   │     ├── Continuous monitoring
│   │     └── Example:
│   │           ├── Detect unencrypted volumes
│   │           ├── Detect open security groups
│   │           └── Detect disabled CloudTrail
│   │
│   ├── Proactive Controls
│   │     ├── Implemented using CloudFormation hooks
│   │     ├── Validate resources before deployment
│   │     ├── Stop non-compliant provisioning
│   │     └── Example:
│   │           ├── Require encryption
│   │           ├── Validate tags
│   │           └── Enforce standards
│   │
│   └── Guidance Levels
│         ├── Mandatory
│         ├── Strongly recommended
│         └── Elective
│
├── 4. ACCOUNT FACTORY
│   │
│   ├── Purpose
│   │     ├── Automated account provisioning
│   │     ├── Standardized account creation
│   │     ├── Governance at creation time
│   │     └── Scalable multi-account setup
│   │
│   ├── Features
│   │     ├── Preconfigured baselines
│   │     ├── Network configuration
│   │     ├── SSO assignments
│   │     ├── Tagging standards
│   │     └── Automated enrollment
│   │
│   ├── Account Factory for Terraform (AFT)
│   │     ├── Terraform-based provisioning
│   │     ├── GitOps workflows
│   │     ├── CI/CD integration
│   │     ├── Customizations
│   │     └── Pipeline automation
│   │
│   ├── Customizations
│   │     ├── Baseline packages
│   │     ├── Account bootstrap
│   │     ├── Custom IAM roles
│   │     ├── Security agents
│   │     └── Networking standards
│   │
│   └── Lifecycle
│         ├── Provision
│         ├── Enroll
│         ├── Update
│         ├── Drift detection
│         └── Decommission
│
├── 5. SECURITY & COMPLIANCE
│   │
│   ├── Logging
│   │     ├── AWS CloudTrail
│   │     ├── AWS Config
│   │     ├── S3 centralized logs
│   │     ├── Log retention
│   │     └── Audit trails
│   │
│   ├── Monitoring
│   │     ├── AWS Config rules
│   │     ├── Security Hub integration
│   │     ├── CloudWatch integration
│   │     ├── EventBridge integration
│   │     └── Compliance dashboards
│   │
│   ├── Security Services Integration
│   │     ├── AWS Security Hub
│   │     ├── Amazon GuardDuty
│   │     ├── AWS IAM Identity Center
│   │     ├── AWS KMS
│   │     └── AWS CloudTrail
│   │
│   ├── Compliance Frameworks
│   │     ├── CIS benchmarks
│   │     ├── NIST alignment
│   │     ├── Internal governance
│   │     └── Regulatory standards
│   │
│   └── Root User Protection
│         ├── MFA requirements
│         ├── Restricted root usage
│         ├── Monitoring root activity
│         └── Security alerts
│
├── 6. NETWORKING & REGIONS
│   │
│   ├── Region Management
│   │     ├── Governed Regions
│   │     ├── Home Region
│   │     ├── Region deny SCPs
│   │     └── Expansion strategy
│   │
│   ├── Networking Models
│   │     ├── Centralized networking
│   │     ├── Shared services VPC
│   │     ├── Transit Gateway
│   │     ├── Hub-and-spoke
│   │     └── Decentralized networking
│   │
│   ├── Connectivity
│   │     ├── VPC sharing
│   │     ├── Direct Connect
│   │     ├── VPN
│   │     ├── PrivateLink
│   │     └── Peering
│   │
│   └── DNS Strategy
│         ├── Route 53 Resolver
│         ├── Private hosted zones
│         ├── Shared DNS services
│         └── Hybrid DNS
│
├── 7. OPERATIONS & LIFECYCLE
│   │
│   ├── Landing Zone Setup
│   │     ├── Initial configuration
│   │     ├── OU structure
│   │     ├── Region selection
│   │     ├── Logging configuration
│   │     └── Identity setup
│   │
│   ├── Updates
│   │     ├── Landing zone version updates
│   │     ├── Control updates
│   │     ├── Baseline updates
│   │     └── Feature enhancements
│   │
│   ├── Drift Management
│   │     ├── Detect drift
│   │     ├── Repair drift
│   │     ├── Re-register OU
│   │     └── Re-enroll account
│   │
│   ├── Enrollment
│   │     ├── Existing account enrollment
│   │     ├── OU registration
│   │     ├── Baseline application
│   │     └── Governance enablement
│   │
│   └── Decommissioning
│         ├── Unmanage accounts
│         ├── Remove controls
│         ├── Delete landing zone
│         └── Cleanup resources
│
├── 8. INTEGRATIONS
│   │
│   ├── AWS Organizations
│   ├── AWS IAM Identity Center
│   ├── AWS Config
│   ├── AWS CloudTrail
│   ├── AWS Service Catalog
│   ├── AWS Security Hub
│   ├── Amazon EventBridge
│   ├── AWS CloudFormation
│   ├── AWS Control Catalog
│   └── Terraform / AFT
│
├── 9. BEST PRACTICES
│   │
│   ├── Multi-account Strategy
│   │     ├── Separate workloads
│   │     ├── Environment isolation
│   │     ├── Least privilege
│   │     └── Blast-radius reduction
│   │
│   ├── OU Design
│   │     ├── Security OU
│   │     ├── Infrastructure OU
│   │     ├── Sandbox OU
│   │     ├── Production OU
│   │     └── SDLC separation
│   │
│   ├── Security
│   │     ├── Centralized logging
│   │     ├── Mandatory controls
│   │     ├── Encryption everywhere
│   │     ├── MFA enforcement
│   │     └── Continuous monitoring
│   │
│   ├── Automation
│   │     ├── Infrastructure as Code
│   │     ├── GitOps
│   │     ├── CI/CD integration
│   │     ├── Automated provisioning
│   │     └── Policy as Code
│   │
│   └── Operations
│         ├── Regular updates
│         ├── Drift remediation
│         ├── Compliance reviews
│         └── Cost governance
│
└── 10. ADVANCED TOPICS
    │
    ├── Account Factory for Terraform (AFT)
    │     ├── GitOps pipelines
    │     ├── Terraform modules
    │     ├── Account request framework
    │     ├── Custom workflows
    │     └── Enterprise automation
    │
    ├── Customizations for AWS Control Tower (CfCT)
    │     ├── StackSets
    │     ├── SCP deployment
    │     ├── Custom baselines
    │     ├── Organization-wide deployments
    │     └── Infrastructure standardization
    │
    ├── Control APIs
    │     ├── Control Tower APIs
    │     ├── Automation scripts
    │     ├── SDK integrations
    │     └── Operational tooling
    │
    ├── Enterprise Governance
    │     ├── Central security operations
    │     ├── Compliance automation
    │     ├── Global account vending
    │     └── Enterprise standards
    │
    └── Hybrid & Enterprise Architecture
          ├── Multi-region enterprise
          ├── Hybrid cloud
          ├── Shared networking
          ├── Enterprise identity federation
          └── Large-scale governance
</pre>

