
**Mental MAP - AWS Identity and Access Management (IAM)**

AWS IAM
│
├── 1. IDENTITIES (Principals)
│   │
│   ├── Root User
│   │
│   ├── IAM Users
│   │     ├── Console password
│   │     ├── Access keys
│   │     ├── MFA devices
│   │     ├── Tags
│   │     ├── Permissions
│   │     └── SSH keys (CodeCommit)
│   │
│   ├── IAM Groups
│   │     ├── Attach policies
│   │     └── Organize users
│   │
│   └── IAM Roles
│         │
│         ├── Service Roles
│         │     ├── EC2 roles
│         │     ├── Lambda roles
│         │     ├── ECS task roles
│         │     ├── EKS node roles
│         │     └── Step Functions roles
│         │
│         ├── Cross-Account Roles
│         │
│         ├── Federation Roles
│         │
│         ├── Service-Linked Roles
│         │
│         └── Instance Profiles
│
│
├── 2. AUTHENTICATION
│   │
│   ├── Console login
│   │
│   ├── Access keys
│   │     ├── Access Key ID
│   │     └── Secret Access Key
│   │
│   ├── Temporary credentials
│   │
│   └── Multi-Factor Authentication (MFA)
│         ├── Virtual MFA
│         ├── Hardware MFA
│         ├── FIDO2 security keys
│         └── U2F keys
│
│
├── 3. AUTHORIZATION (POLICIES)
│   │
│   ├── Policy Types
│   │     │
│   │     ├── Identity-based policies
│   │     │     ├── AWS Managed Policies
│   │     │     ├── Customer Managed Policies
│   │     │     └── Inline Policies
│   │     │
│   │     ├── Resource-based policies
│   │     │     ├── S3 Bucket Policies
│   │     │     ├── Lambda Resource Policies
│   │     │     ├── KMS Key Policies
│   │     │     ├── SNS Topic Policies
│   │     │     └── SQS Queue Policies
│   │     │
│   │     ├── Permissions Boundaries
│   │     │
│   │     ├── Session Policies
│   │     │
│   │     ├── Service Control Policies (SCP)
│   │     │
│   │     └── Resource Control Policies (RCP)
│   │
│   ├── Policy Structure
│   │     │
│   │     ├── Version
│   │     ├── Statement
│   │     │
│   │     ├── Effect
│   │     │     ├── Allow
│   │     │     └── Deny
│   │     │
│   │     ├── Action
│   │     │
│   │     ├── Resource
│   │     │
│   │     ├── Principal
│   │     │
│   │     └── Condition
│   │
│   └── Policy Conditions
│         │
│         ├── String conditions
│         ├── Numeric conditions
│         ├── Date conditions
│         ├── Boolean conditions
│         ├── IP conditions
│         ├── ARN conditions
│         └── Tag conditions
│
│
├── 4. ACCESS CONTROL MODELS
│   │
│   ├── RBAC
│   │     └── Role-Based Access Control
│   │
│   ├── ABAC
│   │     └── Attribute-Based Access Control
│   │
│   └── Tag-based access control
│
│
├── 5. SECURITY TOKEN SERVICE (STS)
│   │
│   ├── Temporary Credentials
│   │
│   ├── STS APIs
│   │     ├── AssumeRole
│   │     ├── AssumeRoleWithSAML
│   │     ├── AssumeRoleWithWebIdentity
│   │     ├── GetSessionToken
│   │     └── GetFederationToken
│   │
│   └── Session duration configuration
│
│
├── 6. FEDERATION
│   │
│   ├── Identity Providers
│   │     │
│   │     ├── SAML 2.0
│   │     │     ├── Active Directory
│   │     │     ├── Okta
│   │     │     └── Azure AD
│   │     │
│   │     ├── OpenID Connect (OIDC)
│   │     │     ├── Google
│   │     │     ├── GitHub
│   │     │     ├── Auth0
│   │     │     └── Kubernetes IRSA
│   │     │
│   │     └── Web Identity Federation
│   │
│   └── IAM Identity Center (SSO)
│
│
├── 7. CROSS-ACCOUNT ACCESS
│   │
│   ├── Role assumption
│   │
│   ├── Trust policies
│   │
│   └── External ID usage
│
│
├── 8. POLICY EVALUATION ENGINE
│   │
│   ├── Evaluation logic
│   │
│   ├── Explicit deny
│   │
│   ├── Implicit deny
│   │
│   ├── Policy evaluation order
│   │
│   └── Combined policies
│
│
├── 9. SECURITY FEATURES
│   │
│   ├── IAM Access Analyzer
│   │     ├── External access detection
│   │     ├── Cross-account detection
│   │     └── Policy generation
│   │
│   ├── IAM Policy Simulator
│   │
│   ├── Access Advisor
│   │
│   ├── Last Accessed Information
│   │
│   └── Credential reports
│
│
├── 10. AUDITING & MONITORING
│   │
│   ├── CloudTrail integration
│   │
│   ├── AWS Config
│   │
│   ├── EventBridge
│   │
│   └── CloudWatch Logs
│
│
├── 11. RESOURCE MANAGEMENT
│   │
│   ├── Tags
│   │
│   ├── Naming conventions
│   │
│   └── Policy versioning
│
│
├── 12. ADMINISTRATION
│   │
│   ├── Delegated administration
│   │
│   ├── Policy delegation
│   │
│   ├── Permissions boundaries
│   │
│   └── Organizational governance
│
│
├── 13. AWS ORGANIZATIONS INTEGRATION
│   │
│   ├── Service Control Policies (SCP)
│   │
│   ├── Organizational Units (OU)
│   │
│   └── Multi-account security model
│
│
├── 14. SERVICE INTEGRATIONS
│   │
│   ├── EC2 Instance Profiles
│   │
│   ├── EKS IAM Roles for Service Accounts (IRSA)
│   │
│   ├── Lambda execution roles
│   │
│   ├── ECS task roles
│   │
│   ├── CodeBuild roles
│   │
│   └── Step Functions roles
│
│
├── 15. LIMITS AND QUOTAS
│   │
│   ├── Users per account
│   ├── Roles per account
│   ├── Groups per account
│   ├── Policies per identity
│   └── Policy size limits
│
│
└── 16. BEST PRACTICES
    │
    ├── Least privilege
    │
    ├── Avoid root usage
    │
    ├── MFA everywhere
    │
    ├── Prefer roles over access keys
    │
    ├── Rotate credentials
    │
    ├── Use Access Analyzer
    │
    └── Use federation for workforce access