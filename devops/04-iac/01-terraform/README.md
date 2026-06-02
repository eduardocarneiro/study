
<pre>
Terraform
├── Introduction
│   ├── What is Terraform
│   ├── Infrastructure as Code
│   ├── Declarative Configuration
│   ├── Immutable Infrastructure
│   ├── Desired State
│   ├── Execution Plan
│   ├── Resource Graph
│   ├── State Management
│   ├── Providers
│   ├── Modules
│   ├── Terraform Ecosystem
│   ├── Terraform Editions
│   │   ├── Terraform OSS
│   │   ├── HCP Terraform
│   │   └── Terraform Enterprise
│   ├── Terraform Architecture
│   │   ├── Core
│   │   ├── Plugins
│   │   ├── Provider Plugins
│   │   ├── Provisioner Plugins
│   │   └── RPC Communication
│   └── Terraform Workflow
│       ├── Write
│       ├── Init
│       ├── Validate
│       ├── Plan
│       ├── Apply
│       ├── Destroy
│       └── Manage State
│
├── Installation
│   ├── Install Terraform
│   │   ├── Linux
│   │   ├── macOS
│   │   ├── Windows
│   │   └── Package Managers
│   ├── Verify Installation
│   ├── Terraform CLI
│   ├── Terraform Binary
│   ├── Environment Variables
│   ├── CLI Configuration File
│   └── Credentials Configuration
│
├── Terraform Language
│   ├── Configuration Syntax
│   │   ├── Native Syntax
│   │   ├── JSON Syntax
│   │   ├── UTF-8 Encoding
│   │   ├── Comments
│   │   ├── Identifiers
│   │   ├── Blocks
│   │   ├── Arguments
│   │   ├── Labels
│   │   └── Expressions
│   │
│   ├── Files
│   │   ├── .tf
│   │   ├── .tfvars
│   │   ├── .tf.json
│   │   ├── override.tf
│   │   ├── terraform.tfvars
│   │   ├── *.auto.tfvars
│   │   └── Dependency Lock File
│   │
│   ├── Blocks
│   │   ├── terraform
│   │   ├── resource
│   │   ├── data
│   │   ├── variable
│   │   ├── output
│   │   ├── locals
│   │   ├── provider
│   │   ├── module
│   │   ├── moved
│   │   ├── import
│   │   └── check
│   │
│   ├── Arguments
│   │   ├── Required Arguments
│   │   ├── Optional Arguments
│   │   ├── Meta Arguments
│   │   ├── Nested Arguments
│   │   └── Dynamic Arguments
│   │
│   ├── Types and Values
│   │   ├── Primitive Types
│   │   │   ├── string
│   │   │   ├── number
│   │   │   └── bool
│   │   ├── Collection Types
│   │   │   ├── list
│   │   │   ├── set
│   │   │   └── map
│   │   ├── Structural Types
│   │   │   ├── object
│   │   │   └── tuple
│   │   ├── Dynamic Types
│   │   │   └── any
│   │   ├── null
│   │   ├── Unknown Values
│   │   ├── Type Constraints
│   │   ├── Type Conversion
│   │   └── Sensitive Values
│   │
│   ├── Strings and Templates
│   │   ├── String Literals
│   │   ├── Heredoc Strings
│   │   ├── Template Interpolation
│   │   ├── Template Directives
│   │   ├── Escape Sequences
│   │   ├── Indented Heredoc
│   │   └── templatefile Function
│   │
│   ├── References
│   │   ├── Named Values
│   │   ├── Resource References
│   │   ├── Data Source References
│   │   ├── Module References
│   │   ├── Variable References
│   │   ├── Local References
│   │   ├── Path References
│   │   ├── Terraform Workspace Reference
│   │   └── Block References
│   │
│   ├── Expressions
│   │   ├── Literal Expressions
│   │   ├── Collection Expressions
│   │   ├── Arithmetic Operators
│   │   ├── Equality Operators
│   │   ├── Comparison Operators
│   │   ├── Logical Operators
│   │   ├── Conditional Expressions
│   │   ├── For Expressions
│   │   ├── Splat Expressions
│   │   ├── Dynamic Blocks
│   │   ├── Null Values
│   │   ├── Type Conversion Expressions
│   │   └── Index and Attribute Access
│   │
│   ├── Functions
│   │   ├── Numeric Functions
│   │   ├── String Functions
│   │   ├── Collection Functions
│   │   ├── Encoding Functions
│   │   ├── Filesystem Functions
│   │   ├── Date and Time Functions
│   │   ├── Hash and Crypto Functions
│   │   ├── IP Network Functions
│   │   ├── Type Conversion Functions
│   │   ├── Terraform Specific Functions
│   │   └── Sensitive Functions
│   │
│   ├── Variables
│   │   ├── Input Variables
│   │   ├── Variable Types
│   │   ├── Default Values
│   │   ├── Variable Validation
│   │   ├── Nullable Variables
│   │   ├── Sensitive Variables
│   │   ├── Ephemeral Variables
│   │   ├── Variable Definition Priority
│   │   ├── tfvars Files
│   │   ├── Environment Variables
│   │   └── CLI Variable Assignment
│   │
│   ├── Local Values
│   │   ├── locals Block
│   │   ├── Local Scope
│   │   ├── Local Expressions
│   │   └── Computed Values
│   │
│   ├── Outputs
│   │   ├── output Block
│   │   ├── Sensitive Outputs
│   │   ├── Depends On Outputs
│   │   ├── Output Preconditions
│   │   └── Module Outputs
│   │
│   ├── Meta Arguments
│   │   ├── count
│   │   ├── for_each
│   │   ├── depends_on
│   │   ├── provider
│   │   ├── lifecycle
│   │   │   ├── create_before_destroy
│   │   │   ├── prevent_destroy
│   │   │   ├── ignore_changes
│   │   │   └── replace_triggered_by
│   │   └── providers
│   │
│   ├── Resource Behavior
│   │   ├── Resource Dependencies
│   │   ├── Implicit Dependencies
│   │   ├── Explicit Dependencies
│   │   ├── Resource Addressing
│   │   ├── Resource Instances
│   │   ├── Tainted Resources
│   │   ├── Replace Operations
│   │   └── Drift Detection
│   │
│   ├── Provisioners
│   │   ├── local-exec
│   │   ├── remote-exec
│   │   ├── file
│   │   ├── Connection Block
│   │   ├── Failure Behavior
│   │   ├── Destroy-Time Provisioners
│   │   └── Provisioner Best Practices
│   │
│   ├── Checks and Validations
│   │   ├── check Blocks
│   │   ├── Preconditions
│   │   ├── Postconditions
│   │   ├── Variable Validation
│   │   ├── Custom Conditions
│   │   └── Runtime Assertions
│   │
│   ├── Import
│   │   ├── import Blocks
│   │   ├── CLI Import
│   │   ├── Generated Configuration
│   │   ├── Import Existing Infrastructure
│   │   └── Import Workflows
│   │
│   ├── Moved Blocks
│   │   ├── Resource Refactoring
│   │   ├── Address Changes
│   │   ├── Module Refactoring
│   │   └── State Preservation
│   │
│   └── Style Conventions
│       ├── Naming Conventions
│       ├── File Organization
│       ├── Module Structure
│       ├── Formatting
│       ├── terraform fmt
│       ├── Documentation Practices
│       ├── Variable Naming
│       ├── Output Naming
│       └── Readability Practices
│
├── Terraform Block
│   ├── required_version
│   ├── required_providers
│   ├── backend
│   ├── cloud
│   ├── experiments
│   └── Provider Installation
│
├── Providers
│   ├── Provider Architecture
│   ├── Provider Requirements
│   ├── Provider Installation
│   ├── Provider Configuration
│   ├── Provider Aliases
│   ├── Multiple Providers
│   ├── Provider Inheritance
│   ├── Third-Party Providers
│   ├── Private Providers
│   ├── Provider Version Constraints
│   ├── Dependency Lock File
│   ├── Provider Mirrors
│   └── Plugin Cache
│
├── Resources
│   ├── Managed Resources
│   ├── Resource Syntax
│   ├── Resource Lifecycle
│   ├── Resource Dependencies
│   ├── Resource Targeting
│   ├── Resource Replacement
│   ├── Resource Drift
│   ├── Resource Timeouts
│   ├── Dynamic Nested Blocks
│   ├── Count Resources
│   ├── for_each Resources
│   └── Resource Graph
│
├── Data Sources
│   ├── Data Resource Syntax
│   ├── Data Dependencies
│   ├── External Data
│   ├── Remote State Data
│   ├── Computed Data
│   └── Data Evaluation
│
├── Modules
│   ├── Module Basics
│   ├── Child Modules
│   ├── Root Module
│   ├── Module Structure
│   ├── Module Inputs
│   ├── Module Outputs
│   ├── Module Providers
│   ├── Module Dependencies
│   ├── Local Modules
│   ├── Registry Modules
│   ├── Git Modules
│   ├── Remote Modules
│   ├── Module Versioning
│   ├── Module Composition
│   ├── Module Refactoring
│   ├── Published Modules
│   ├── Private Registry
│   ├── Module Testing
│   ├── Module Best Practices
│   └── Module Scalability
│
├── State Management
│   ├── Terraform State
│   ├── State File
│   ├── State Snapshots
│   ├── Local State
│   ├── Remote State
│   ├── State Locking
│   ├── State Consistency
│   ├── State Commands
│   │   ├── state list
│   │   ├── state show
│   │   ├── state mv
│   │   ├── state rm
│   │   ├── state pull
│   │   ├── state push
│   │   └── state replace-provider
│   ├── State Security
│   ├── State Encryption
│   ├── State Backup
│   ├── Sensitive Data in State
│   ├── Drift Detection
│   ├── Remote State Sharing
│   └── State Recovery
│
├── Backends
│   ├── Backend Types
│   ├── Local Backend
│   ├── Remote Backend
│   ├── HCP Terraform Backend
│   ├── S3 Backend
│   ├── AzureRM Backend
│   ├── GCS Backend
│   ├── Consul Backend
│   ├── PostgreSQL Backend
│   ├── HTTP Backend
│   ├── Kubernetes Backend
│   ├── Backend Initialization
│   ├── Partial Configuration
│   ├── Backend Authentication
│   ├── State Locking
│   └── Backend Migration
│
├── Workspaces
│   ├── CLI Workspaces
│   ├── Workspace Commands
│   ├── Multiple Environments
│   ├── Environment Isolation
│   ├── Workspace State
│   ├── terraform.workspace
│   └── Workspace Strategies
│
├── Terraform CLI
│   ├── terraform init
│   ├── terraform validate
│   ├── terraform fmt
│   ├── terraform plan
│   ├── terraform apply
│   ├── terraform destroy
│   ├── terraform refresh
│   ├── terraform import
│   ├── terraform taint
│   ├── terraform untaint
│   ├── terraform output
│   ├── terraform console
│   ├── terraform graph
│   ├── terraform providers
│   ├── terraform login
│   ├── terraform logout
│   ├── terraform version
│   ├── terraform show
│   ├── terraform force-unlock
│   ├── terraform workspace
│   ├── terraform state
│   ├── terraform test
│   ├── terraform metadata
│   └── terraform stacks
│
├── Dependency Management
│   ├── Dependency Lock File
│   ├── Version Constraints
│   │   ├── Exact Versions
│   │   ├── Minimum Versions
│   │   ├── Maximum Versions
│   │   ├── Pessimistic Constraints
│   │   └── Multiple Constraints
│   ├── Provider Dependencies
│   ├── Module Dependencies
│   └── Dependency Resolution
│
├── Testing
│   ├── terraform test
│   ├── Test Files
│   ├── Run Blocks
│   ├── Assertions
│   ├── Mock Providers
│   ├── Mock Resources
│   ├── Mock Data Sources
│   ├── Unit Testing
│   ├── Integration Testing
│   ├── Validation Testing
│   └── Testing Strategies
│
├── Stacks
│   ├── Stack Configuration
│   ├── Stack Components
│   ├── Deployment Orchestration
│   ├── Stack Dependencies
│   ├── Stack State
│   ├── Stack Variables
│   ├── Stack Outputs
│   ├── Stack Providers
│   ├── Stack Workflow
│   └── Stack Automation
│
├── HCP Terraform
│   ├── Organizations
│   ├── Projects
│   ├── Workspaces
│   ├── Runs
│   ├── Remote Execution
│   ├── VCS Integration
│   ├── Policy Enforcement
│   ├── Sentinel Policies
│   ├── Run Tasks
│   ├── Variable Sets
│   ├── Teams and Permissions
│   ├── Agents
│   ├── Cost Estimation
│   ├── Private Registry
│   ├── Notifications
│   ├── API Access
│   └── Governance
│
├── Terraform Enterprise
│   ├── Private Installation
│   ├── Replicated Architecture
│   ├── Active Active
│   ├── Disaster Recovery
│   ├── External Services
│   ├── Security Hardening
│   ├── Operational Management
│   ├── License Management
│   ├── Air Gap Deployments
│   ├── Monitoring
│   └── Scaling
│
├── Policies and Governance
│   ├── Sentinel
│   ├── Policy Sets
│   ├── Advisory Policies
│   ├── Soft Mandatory Policies
│   ├── Hard Mandatory Policies
│   ├── Governance Workflows
│   ├── Compliance Enforcement
│   ├── Cost Control
│   └── Security Policies
│
├── Security
│   ├── Sensitive Data
│   ├── Secrets Management
│   ├── Credential Management
│   ├── State Encryption
│   ├── Least Privilege
│   ├── Provider Authentication
│   ├── Secure Variables
│   ├── Vault Integration
│   ├── Remote State Security
│   ├── Policy Enforcement
│   ├── Supply Chain Security
│   ├── Dependency Verification
│   ├── Signed Providers
│   └── Secure Module Practices
│
├── Debugging and Troubleshooting
│   ├── TF_LOG
│   ├── TF_LOG_PATH
│   ├── Debug Output
│   ├── Crash Logs
│   ├── Provider Debugging
│   ├── State Troubleshooting
│   ├── Dependency Graph Analysis
│   ├── terraform console
│   ├── Error Diagnostics
│   ├── Validation Errors
│   ├── Apply Errors
│   └── Performance Analysis
│
├── Performance and Scalability
│   ├── Graph Optimization
│   ├── Parallelism
│   ├── Provider Performance
│   ├── State Performance
│   ├── Large Infrastructure
│   ├── Module Scalability
│   ├── Dependency Optimization
│   ├── Backend Performance
│   ├── Caching
│   └── Execution Tuning
│
├── Automation and CI/CD
│   ├── GitOps
│   ├── CI Pipelines
│   ├── CD Pipelines
│   ├── Plan Automation
│   ├── Apply Automation
│   ├── Drift Automation
│   ├── Policy Automation
│   ├── Terraform in Containers
│   ├── Terraform in Kubernetes
│   ├── Remote Execution
│   └── Infrastructure Pipelines
│
├── Cloud Integration
│   ├── AWS
│   ├── Azure
│   ├── Google Cloud
│   ├── Kubernetes
│   ├── VMware
│   ├── OCI
│   ├── Alibaba Cloud
│   ├── Cloudflare
│   ├── GitHub
│   ├── GitLab
│   ├── Datadog
│   ├── Fastly
│   ├── Snowflake
│   └── Multi Cloud Architecture
│
├── Best Practices
│   ├── Repository Structure
│   ├── Module Reusability
│   ├── State Isolation
│   ├── Environment Separation
│   ├── Version Pinning
│   ├── Code Review
│   ├── Documentation
│   ├── Naming Standards
│   ├── Secure Design
│   ├── Least Privilege
│   ├── DRY Principles
│   ├── Testing Strategy
│   ├── CI/CD Integration
│   ├── Drift Management
│   ├── Dependency Management
│   └── Operational Governance
│
└── Advanced Concepts
    ├── Resource Graph
    ├── Graph Theory
    ├── Dependency Resolution
    ├── Lazy Evaluation
    ├── Unknown Values
    ├── Partial Applies
    ├── Execution Model
    ├── Plan Internals
    ├── Apply Internals
    ├── Plugin Architecture
    ├── RPC Protocol
    ├── Provider SDK
    ├── Dynamic Infrastructure
    ├── Infrastructure Composition
    ├── Multi Environment Design
    ├── Multi Account Architecture
    ├── Multi Region Architecture
    ├── Multi Cloud Architecture
    ├── Immutable Deployments
    ├── Drift Reconciliation
    ├── Infrastructure Lifecycle
    └── Enterprise Scale Operations
</pre>