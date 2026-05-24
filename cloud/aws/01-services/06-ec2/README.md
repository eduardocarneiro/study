
<pre>
AWS EC2
│
├── 1. CORE CONCEPTS
│   │
│   ├── Virtual Machines in AWS
│   ├── Elastic Compute Capacity
│   ├── Infrastructure as a Service (IaaS)
│   ├── On-demand Compute
│   ├── Shared Responsibility Model
│   ├── Regional Service
│   ├── Availability Zones (AZs)
│   ├── Instances
│   ├── Amazon Machine Images (AMIs)
│   ├── Instance Lifecycle
│   └── Hypervisor / Nitro System
│
├── 2. EC2 INSTANCE TYPES
│   │
│   ├── General Purpose
│   │     ├── T Family
│   │     ├── M Family
│   │     └── Mac Instances
│   │
│   ├── Compute Optimized
│   │     └── C Family
│   │
│   ├── Memory Optimized
│   │     ├── R Family
│   │     ├── X Family
│   │     ├── High Memory
│   │     └── z1d
│   │
│   ├── Storage Optimized
│   │     ├── I Family
│   │     ├── D Family
│   │     └── H Family
│   │
│   ├── Accelerated Computing
│   │     ├── GPU Instances
│   │     ├── FPGA Instances
│   │     ├── Inferentia
│   │     └── Trainium
│   │
│   ├── Burstable Performance
│   ├── Dedicated Instances
│   ├── Dedicated Hosts
│   └── Bare Metal Instances
│
├── 3. AMAZON MACHINE IMAGES (AMIs)
│   │
│   ├── AMI Components
│   │     ├── Root Volume Template
│   │     ├── Launch Permissions
│   │     └── Block Device Mapping
│   │
│   ├── AMI Types
│   │     ├── AWS Managed
│   │     ├── Marketplace AMIs
│   │     ├── Community AMIs
│   │     └── Custom AMIs
│   │
│   ├── Create AMIs
│   ├── Copy AMIs
│   ├── Share AMIs
│   ├── Encrypt AMIs
│   ├── Deregister AMIs
│   └── Golden Image Strategy
│
├── 4. EC2 INSTANCE LIFECYCLE
│   │
│   ├── Pending
│   ├── Running
│   ├── Stopping
│   ├── Stopped
│   ├── Shutting-down
│   ├── Terminated
│   │
│   ├── Reboot Instances
│   ├── Stop vs Terminate
│   ├── Hibernate
│   ├── Instance Retirement
│   ├── Scheduled Events
│   └── Recovery Actions
│
├── 5. STORAGE
│   │
│   ├── Amazon EBS (Elastic Block Store)
│   │     │
│   │     ├── Persistent Block Storage
│   │     ├── Volume Types
│   │     │     ├── gp3 / gp2
│   │     │     ├── io1 / io2
│   │     │     ├── st1
│   │     │     └── sc1
│   │     │
│   │     ├── Snapshots
│   │     ├── Encryption
│   │     ├── Multi-Attach
│   │     ├── Resize Volumes
│   │     ├── Lifecycle Management
│   │     └── Fast Snapshot Restore
│   │
│   ├── Instance Store
│   │     ├── Ephemeral Storage
│   │     ├── High Performance
│   │     └── Data Loss on Stop/Terminate
│   │
│   ├── EFS Integration
│   └── FSx Integration
│
├── 6. NETWORKING
│   │
│   ├── VPC Integration
│   ├── Elastic Network Interface (ENI)
│   ├── Private IP Addresses
│   ├── Public IP Addresses
│   ├── Elastic IP Addresses
│   ├── Security Groups
│   ├── Placement Groups
│   │     ├── Cluster
│   │     ├── Partition
│   │     └── Spread
│   │
│   ├── Enhanced Networking
│   ├── Elastic Fabric Adapter (EFA)
│   ├── IPv4 / IPv6
│   ├── DNS Hostnames
│   └── EC2 Instance Connect
│
├── 7. SECURITY
│   │
│   ├── Shared Responsibility Model
│   ├── IAM Integration
│   │     ├── IAM Users
│   │     ├── IAM Roles
│   │     ├── Instance Profiles
│   │     └── Temporary Credentials
│   │
│   ├── Security Groups
│   ├── Key Pairs
│   │     ├── RSA
│   │     └── ED25519
│   │
│   ├── SSH Access
│   ├── Systems Manager Session Manager
│   ├── Nitro Enclaves
│   ├── Encryption
│   │     ├── EBS Encryption
│   │     ├── AMI Encryption
│   │     └── TLS
│   │
│   ├── IMDSv2
│   ├── Instance Metadata Service
│   ├── Secure Boot
│   ├── Trusted Launch Concepts
│   └── GuardDuty / Inspector Integration
│
├── 8. EC2 PRICING MODELS
│   │
│   ├── On-Demand Instances
│   ├── Reserved Instances (RIs)
│   │     ├── Standard RI
│   │     ├── Convertible RI
│   │     └── Scheduled RI
│   │
│   ├── Savings Plans
│   ├── Spot Instances
│   │     ├── Spot Pricing
│   │     ├── Interruption Handling
│   │     └── Spot Fleets
│   │
│   ├── Dedicated Hosts
│   ├── Capacity Reservations
│   └── Cost Optimization Strategies
│
├── 9. AUTO SCALING
│   │
│   ├── EC2 Auto Scaling
│   │     ├── Auto Scaling Groups (ASGs)
│   │     ├── Launch Templates
│   │     ├── Scaling Policies
│   │     ├── Desired Capacity
│   │     ├── Min / Max Capacity
│   │     └── Health Checks
│   │
│   ├── Scaling Types
│   │     ├── Dynamic Scaling
│   │     ├── Predictive Scaling
│   │     ├── Scheduled Scaling
│   │     └── Manual Scaling
│   │
│   ├── Target Tracking
│   ├── Step Scaling
│   ├── Lifecycle Hooks
│   └── Warm Pools
│
├── 10. LOAD BALANCING INTEGRATION
│   │
│   ├── Elastic Load Balancer (ELB)
│   │     ├── Application Load Balancer (ALB)
│   │     ├── Network Load Balancer (NLB)
│   │     ├── Gateway Load Balancer (GWLB)
│   │     └── Classic Load Balancer (Legacy)
│   │
│   ├── Target Groups
│   ├── Health Checks
│   ├── Cross-Zone Load Balancing
│   ├── Sticky Sessions
│   └── SSL/TLS Termination
│
├── 11. MONITORING & OBSERVABILITY
│   │
│   ├── Amazon CloudWatch
│   │     ├── Metrics
│   │     ├── Logs
│   │     ├── Alarms
│   │     └── Dashboards
│   │
│   ├── EC2 Status Checks
│   │     ├── System Status Checks
│   │     ├── Instance Status Checks
│   │     └── Attached EBS Checks
│   │
│   ├── CloudTrail Integration
│   ├── VPC Flow Logs
│   ├── AWS Config
│   ├── Compute Optimizer
│   └── Systems Manager Monitoring
│
├── 12. AUTOMATION & MANAGEMENT
│   │
│   ├── Launch Templates
│   ├── User Data
│   ├── Cloud-init
│   ├── EC2 Image Builder
│   ├── AWS Systems Manager
│   │     ├── Run Command
│   │     ├── Patch Manager
│   │     ├── Automation
│   │     ├── Inventory
│   │     └── Session Manager
│   │
│   ├── Tags
│   ├── Resource Groups
│   ├── Infrastructure as Code
│   │     ├── CloudFormation
│   │     ├── Terraform
│   │     └── CDK
│   │
│   └── Fleet Management
│
├── 13. HIGH AVAILABILITY & RESILIENCY
│   │
│   ├── Multi-AZ Deployments
│   ├── Auto Recovery
│   ├── Placement Groups
│   ├── Elastic Load Balancing
│   ├── Auto Scaling
│   ├── Backup Strategies
│   ├── EBS Snapshots
│   ├── Cross-Region AMIs
│   └── Disaster Recovery Patterns
│
├── 14. MIGRATION & MODERNIZATION
│   │
│   ├── VM Import/Export
│   ├── Application Migration Service (MGN)
│   ├── Lift-and-Shift Migration
│   ├── Hybrid Environments
│   ├── Legacy Workloads
│   └── Cloud Adoption
│
├── 15. PERFORMANCE OPTIMIZATION
│   │
│   ├── Right Sizing
│   ├── Enhanced Networking
│   ├── Nitro System
│   ├── CPU Optimization
│   ├── Memory Optimization
│   ├── Storage Throughput Tuning
│   ├── Placement Groups
│   ├── EBS Optimization
│   └── HPC Workloads
│
├── 16. BACKUP & DISASTER RECOVERY
│   │
│   ├── EBS Snapshots
│   ├── AMI Backups
│   ├── AWS Backup
│   ├── Cross-Region Replication
│   ├── Pilot Light
│   ├── Warm Standby
│   ├── Multi-Site Active/Active
│   └── Recovery Automation
│
├── 17. COMPLIANCE & GOVERNANCE
│   │
│   ├── AWS Config
│   ├── CloudTrail
│   ├── IAM Policies
│   ├── SCPs with Organizations
│   ├── Tag Policies
│   ├── Security Hub
│   ├── Audit Manager
│   └── Compliance Programs
│
└── 18. COMMON ARCHITECTURE PATTERNS
    │
    ├── Web Application Architecture
    ├── Three-tier Architecture
    ├── Bastion Host Pattern
    ├── Auto Scaling Web Tier
    ├── Stateless Applications
    ├── Stateful Workloads
    ├── Batch Processing
    ├── HPC Clusters
    ├── Hybrid Cloud
    ├── Shared Services VPC
    ├── Immutable Infrastructure
    └── Blue/Green Deployments
</pre>