
<pre>
AWS IAM Identity Center
│
├── 1. CORE CONCEPTS
│   │
│   ├── IAM Identity Center
│   │     ├── Centralized workforce access
│   │     ├── Single Sign-On (SSO)
│   │     ├── Multi-account access management
│   │     ├── Application access management
│   │     └── Central identity orchestration
│   │
│   ├── Identity Source
│   │     ├── Internal Identity Store
│   │     ├── Active Directory
│   │     ├── External Identity Providers
│   │     │     ├── Okta
│   │     │     ├── Microsoft Entra ID
│   │     │     ├── Ping Identity
│   │     │     └── JumpCloud
│   │     └── SCIM Synchronization
│   │
│   ├── Workforce Identities
│   │     ├── Users
│   │     ├── Groups
│   │     ├── Attributes
│   │     └── Group-based authorization
│   │
│   ├── AWS Organizations Integration
│   │     ├── Organization Instance
│   │     ├── Delegated Administration
│   │     ├── Multi-account management
│   │     └── OU-aware access governance
│   │
│   ├── Permission Sets
│   │     ├── IAM Policy Collections
│   │     ├── AWS Managed Policies
│   │     ├── Customer Managed Policies
│   │     ├── Inline Policies
│   │     ├── Session Duration
│   │     ├── Relay State
│   │     └── Provisioned IAM Roles
│   │
│   ├── Assignments
│   │     ├── User Assignments
│   │     ├── Group Assignments
│   │     ├── Account Assignments
│   │     └── Permission Set Assignments
│   │
│   ├── User Portal
│   │     ├── AWS Account Access
│   │     ├── Application Launcher
│   │     ├── CLI Access
│   │     └── Federated Console Access
│   │
│   └── Authentication & Federation
│         ├── SAML 2.0
│         ├── OAuth 2.0
│         ├── OpenID Connect (OIDC)
│         ├── MFA
│         └── External IdP Federation
│
├── 2. INSTANCE TYPES
│   │
│   ├── Organization Instance (Recommended)
│   │     ├── Enabled in Management Account
│   │     ├── Supports AWS Organizations
│   │     ├── Centralized account access
│   │     ├── Delegated administration
│   │     └── Multi-account scalability
│   │
│   └── Account Instance
│         ├── Single-account scope
│         ├── No Organizations integration
│         ├── Isolated identity management
│         └── Limited scalability
│
├── 3. IDENTITY SOURCES
│   │
│   ├── IAM Identity Center Identity Store
│   │     ├── Native users
│   │     ├── Native groups
│   │     ├── Password policies
│   │     └── MFA support
│   │
│   ├── Active Directory
│   │     ├── AWS Managed Microsoft AD
│   │     ├── Self-managed AD
│   │     ├── Directory synchronization
│   │     └── Kerberos integration
│   │
│   ├── External Identity Providers
│   │     ├── SAML Federation
│   │     ├── SCIM Provisioning
│   │     ├── Attribute Mapping
│   │     └── Lifecycle Management
│   │
│   └── Identity Synchronization
│         ├── SCIM
│         ├── Automatic provisioning
│         ├── Deprovisioning
│         └── Group synchronization
│
├── 4. ACCESS MANAGEMENT
│   │
│   ├── AWS Account Access
│   │     ├── Cross-account access
│   │     ├── Temporary credentials
│   │     ├── Role assumption
│   │     └── Federated sessions
│   │
│   ├── Permission Sets
│   │     ├── AdministratorAccess
│   │     ├── PowerUserAccess
│   │     ├── ReadOnlyAccess
│   │     ├── Custom permission sets
│   │     └── Least privilege design
│   │
│   ├── Application Access
│   │     ├── AWS Managed Applications
│   │     ├── Customer Managed Applications
│   │     ├── SaaS integrations
│   │     └── Enterprise applications
│   │
│   ├── Attribute-Based Access Control (ABAC)
│   │     ├── User attributes
│   │     ├── Session tags
│   │     ├── Dynamic authorization
│   │     └── Fine-grained access
│   │
│   └── Delegated Administration
│         ├── Administrative delegation
│         ├── Separation of duties
│         ├── Access governance
│         └── Central operations
│
├── 5. APPLICATION INTEGRATION
│   │
│   ├── AWS Managed Applications
│   │     ├── Amazon QuickSight
│   │     ├── Amazon SageMaker
│   │     ├── AWS Systems Manager
│   │     ├── Amazon Redshift
│   │     └── Other AWS services
│   │
│   ├── Customer Managed Applications
│   │     ├── SAML Applications
│   │     ├── OIDC Applications
│   │     ├── Enterprise SaaS
│   │     └── Custom applications
│   │
│   ├── Federation Standards
│   │     ├── SAML 2.0
│   │     ├── OAuth 2.0
│   │     ├── OpenID Connect
│   │     └── SCIM
│   │
│   └── Application Assignment
│         ├── User assignments
│         ├── Group assignments
│         ├── Access policies
│         └── Attribute mappings
│
├── 6. TRUSTED IDENTITY PROPAGATION
│   │
│   ├── Identity Context Propagation
│   │     ├── User identity forwarding
│   │     ├── Group context propagation
│   │     ├── Service-to-service authorization
│   │     └── Fine-grained authorization
│   │
│   ├── OAuth-based Trust
│   │     ├── OAuth 2.0 token exchange
│   │     ├── Trusted token issuer
│   │     ├── Identity assertions
│   │     └── Federated authorization
│   │
│   ├── Supported Integrations
│   │     ├── Amazon Redshift
│   │     ├── Amazon EMR
│   │     ├── Amazon QuickSight
│   │     └── Analytics integrations
│   │
│   └── Auditability
│         ├── CloudTrail visibility
│         ├── User activity tracing
│         ├── Identity-aware logging
│         └── Compliance tracking
│
├── 7. SECURITY FEATURES
│   │
│   ├── Multi-Factor Authentication (MFA)
│   │     ├── Built-in MFA
│   │     ├── External MFA providers
│   │     ├── Adaptive authentication
│   │     └── Conditional MFA
│   │
│   ├── Session Management
│   │     ├── Session duration
│   │     ├── Session revocation
│   │     ├── Token expiration
│   │     └── Relay state
│   │
│   ├── Audit & Monitoring
│   │     ├── AWS CloudTrail
│   │     ├── Access logging
│   │     ├── Sign-in events
│   │     └── Permission tracking
│   │
│   ├── Least Privilege
│   │     ├── Fine-grained access
│   │     ├── Scoped permissions
│   │     ├── Temporary credentials
│   │     └── Centralized governance
│   │
│   └── Compliance & Governance
│         ├── Access reviews
│         ├── Centralized auditing
│         ├── Security controls
│         └── Enterprise governance
│
├── 8. CLI & PROGRAMMATIC ACCESS
│   │
│   ├── AWS CLI v2 Integration
│   │     ├── aws configure sso
│   │     ├── Browser authentication
│   │     ├── Token caching
│   │     └── Automatic credential retrieval
│   │
│   ├── SDK Integration
│   │     ├── Temporary credentials
│   │     ├── Federated authentication
│   │     ├── OIDC token flow
│   │     └── Programmatic access
│   │
│   ├── IAM Roles Behind the Scenes
│   │     ├── Auto-created roles
│   │     ├── Role provisioning
│   │     ├── STS integration
│   │     └── Session assumption
│   │
│   └── Access Patterns
│         ├── Human access
│         ├── Console access
│         ├── CLI access
│         └── Federated workflows
│
├── 9. ADMINISTRATION & OPERATIONS
│   │
│   ├── Delegated Administration
│   │     ├── Management account delegation
│   │     ├── Admin separation
│   │     ├── Operational governance
│   │     └── Central management
│   │
│   ├── User Lifecycle Management
│   │     ├── Provisioning
│   │     ├── Deprovisioning
│   │     ├── Group lifecycle
│   │     └── Identity synchronization
│   │
│   ├── Regional Considerations
│   │     ├── Home region
│   │     ├── Multi-region design
│   │     ├── Regional failover
│   │     └── Identity replication
│   │
│   └── Operational Tasks
│         ├── Permission updates
│         ├── Assignment management
│         ├── Session revocation
│         └── Troubleshooting
│
├── 10. BEST PRACTICES
│   │
│   ├── Use Organization Instance
│   ├── Integrate with AWS Organizations
│   ├── Prefer Groups over Direct User Assignments
│   ├── Implement Least Privilege
│   ├── Use ABAC when Possible
│   ├── Enable MFA Everywhere
│   ├── Centralize Workforce Access
│   ├── Avoid IAM Users for Humans
│   ├── Use Permission Sets Strategically
│   ├── Separate Admin and Read-Only Roles
│   ├── Delegate Administration Carefully
│   ├── Audit with CloudTrail
│   └── Automate Identity Lifecycle
│
└── 11. COMMON ARCHITECTURE PATTERNS
    │
    ├── Enterprise Workforce Federation
    │     ├── Entra ID → IAM Identity Center
    │     ├── Okta → IAM Identity Center
    │     └── AD → IAM Identity Center
    │
    ├── Multi-Account AWS Organizations Access
    │     ├── Centralized permission management
    │     ├── OU-based access strategy
    │     └── Shared permission sets
    │
    ├── SaaS SSO Hub
    │     ├── Salesforce
    │     ├── GitHub
    │     ├── Atlassian
    │     └── Internal applications
    │
    ├── Modern Human Access Pattern
    │     ├── Humans → Identity Center
    │     ├── Machines → IAM Roles
    │     └── Workloads → Service Roles
    │
    └── Data Lake Identity Propagation
          ├── User identity propagation
          ├── Fine-grained analytics access
          ├── End-user auditability
          └── Trusted identity propagation
</pre>