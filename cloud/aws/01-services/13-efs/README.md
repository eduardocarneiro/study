
<pre>
Amazon EFS (Elastic File System)
├── Overview
│   ├── Fully managed NFS file system
│   ├── Serverless elastic storage
│   ├── Shared file storage for Linux workloads
│   ├── Supports multiple EC2 instances simultaneously
│   ├── Regional and highly available
│   ├── POSIX-compliant file system
│   ├── Automatic scaling
│   ├── Pay only for used storage
│   └── Integrates with AWS services
│
├── Core Components
│   ├── File Systems
│   │   ├── Regional file systems
│   │   ├── One Zone file systems
│   │   ├── Elastic capacity
│   │   ├── File system IDs
│   │   ├── Lifecycle state
│   │   └── Encryption support
│   │
│   ├── Mount Targets
│   │   ├── Elastic Network Interfaces (ENIs)
│   │   ├── One per Availability Zone
│   │   ├── Provide IP addresses for mounting
│   │   ├── Security group association
│   │   └── Subnet association
│   │
│   ├── Access Points
│   │   ├── Application-specific entry points
│   │   ├── Simplified permissions
│   │   ├── Root directory override
│   │   ├── POSIX user enforcement
│   │   ├── Multi-tenant isolation
│   │   └── IAM integration
│   │
│   ├── File System Policies
│   │   ├── Resource-based policies
│   │   ├── IAM access control
│   │   ├── Anonymous access control
│   │   ├── Read-only enforcement
│   │   └── Cross-account access
│   │
│   └── Replication
│       ├── Cross-region replication
│       ├── Automatic asynchronous replication
│       ├── Disaster recovery
│       ├── Read-only destination
│       └── Replication metrics
│
├── Storage Classes
│   ├── Standard Storage Class
│   │   ├── Frequently accessed files
│   │   ├── Multi-AZ durability
│   │   ├── Lowest latency
│   │   └── Highest availability
│   │
│   ├── Infrequent Access (IA)
│   │   ├── Lower storage cost
│   │   ├── Retrieval fee applies
│   │   ├── Lifecycle-managed
│   │   └── Ideal for infrequently used files
│   │
│   ├── Archive
│   │   ├── Lowest storage cost
│   │   ├── Higher retrieval latency
│   │   ├── Rarely accessed files
│   │   └── Lifecycle-managed
│   │
│   ├── One Zone Storage Classes
│   │   ├── Single Availability Zone
│   │   ├── Lower cost
│   │   ├── Reduced resiliency
│   │   ├── One Zone-IA
│   │   └── One Zone Archive
│   │
│   └── Lifecycle Management
│       ├── Automatic tiering
│       ├── Transition to IA
│       ├── Transition to Archive
│       ├── Transition back to Standard
│       └── Configurable policies
│
├── Performance
│   ├── Performance Modes
│   │   ├── General Purpose
│   │   │   ├── Lowest latency
│   │   │   ├── Default mode
│   │   │   └── Suitable for most workloads
│   │   │
│   │   └── Max I/O
│   │       ├── Higher scalability
│   │       ├── Higher latency
│   │       └── Parallel workloads
│   │
│   ├── Throughput Modes
│   │   ├── Elastic Throughput
│   │   │   ├── Automatic scaling
│   │   │   ├── Default recommendation
│   │   │   └── Pay per usage
│   │   │
│   │   ├── Bursting Throughput
│   │   │   ├── Throughput tied to storage size
│   │   │   ├── Burst credits
│   │   │   └── Suitable for spiky workloads
│   │   │
│   │   └── Provisioned Throughput
│   │       ├── Fixed throughput
│   │       ├── Independent from storage size
│   │       └── Predictable workloads
│   │
│   ├── Performance Metrics
│   │   ├── Throughput
│   │   ├── IOPS
│   │   ├── Latency
│   │   ├── Burst credits
│   │   └── Metered IO bytes
│   │
│   └── Optimization
│       ├── Parallelization
│       ├── NFS client tuning
│       ├── Mount options
│       ├── Throughput monitoring
│       └── Lifecycle optimization
│
├── Networking
│   ├── VPC Integration
│   │   ├── Mount targets in subnets
│   │   ├── Private IP addressing
│   │   ├── Route tables
│   │   └── DNS resolution
│   │
│   ├── Security Groups
│   │   ├── Control NFS traffic
│   │   ├── Port 2049
│   │   ├── Inbound rules
│   │   └── Outbound rules
│   │
│   ├── Network Access
│   │   ├── EC2 mounting
│   │   ├── On-premises mounting
│   │   ├── Direct Connect integration
│   │   ├── VPN integration
│   │   └── Transit Gateway support
│   │
│   └── DNS
│       ├── Regional DNS names
│       ├── AZ-specific DNS names
│       ├── Automatic resolution
│       └── Route 53 integration
│
├── Security
│   ├── Encryption
│   │   ├── Encryption at rest
│   │   ├── AWS KMS integration
│   │   ├── Customer managed keys
│   │   ├── AWS managed keys
│   │   └── Encryption in transit
│   │
│   ├── IAM
│   │   ├── Identity-based policies
│   │   ├── Resource-based policies
│   │   ├── IAM authorization for clients
│   │   └── Condition keys
│   │
│   ├── POSIX Permissions
│   │   ├── UID/GID ownership
│   │   ├── Read/write/execute permissions
│   │   ├── Directory permissions
│   │   └── Root squashing behavior
│   │
│   ├── Access Control
│   │   ├── Access points
│   │   ├── Security groups
│   │   ├── NACLs
│   │   ├── IAM policies
│   │   └── File system policies
│   │
│   └── Compliance
│       ├── CloudTrail logging
│       ├── AWS Config integration
│       ├── Audit support
│       └── Compliance programs
│
├── Availability and Durability
│   ├── Regional File Systems
│   │   ├── Multi-AZ replication
│   │   ├── High durability
│   │   ├── Automatic failover
│   │   └── Fault tolerance
│   │
│   ├── One Zone File Systems
│   │   ├── Single AZ storage
│   │   ├── Lower cost
│   │   ├── Backup recommendation
│   │   └── Dev/test workloads
│   │
│   ├── Backup and Recovery
│   │   ├── AWS Backup integration
│   │   ├── Automated backups
│   │   ├── On-demand backups
│   │   ├── Restore operations
│   │   └── Cross-region copy
│   │
│   └── Disaster Recovery
│       ├── Replication
│       ├── Backup strategy
│       ├── Multi-region architecture
│       └── Failover planning
│
├── Mounting and Clients
│   ├── Supported Clients
│   │   ├── Linux instances
│   │   ├── macOS clients
│   │   ├── ECS tasks
│   │   ├── EKS pods
│   │   └── Lambda functions
│   │
│   ├── Mount Methods
│   │   ├── NFSv4.1 protocol
│   │   ├── EFS mount helper
│   │   ├── Standard NFS client
│   │   └── TLS-enabled mounts
│   │
│   ├── Mount Helper
│   │   ├── amazon-efs-utils package
│   │   ├── Automatic TLS setup
│   │   ├── IAM authorization support
│   │   └── DNS simplification
│   │
│   ├── Mount Options
│   │   ├── Hard vs soft mounts
│   │   ├── Timeouts
│   │   ├── Retransmissions
│   │   ├── Read/write buffer sizes
│   │   └── TLS configuration
│   │
│   └── Container Integration
│       ├── Amazon ECS
│       ├── Amazon EKS
│       ├── Kubernetes CSI driver
│       ├── Persistent shared storage
│       └── Stateful containers
│
├── Integration with AWS Services
│   ├── Amazon EC2
│   │   ├── Shared storage
│   │   ├── Web servers
│   │   ├── Analytics workloads
│   │   └── Content management
│   │
│   ├── AWS Lambda
│   │   ├── Persistent shared storage
│   │   ├── Large reference datasets
│   │   ├── ML inference
│   │   └── Media processing
│   │
│   ├── Amazon ECS/EKS
│   │   ├── Shared container storage
│   │   ├── Persistent volumes
│   │   ├── Multi-container access
│   │   └── Stateful workloads
│   │
│   ├── AWS Backup
│   │   ├── Centralized backup
│   │   ├── Backup policies
│   │   ├── Vault integration
│   │   └── Lifecycle retention
│   │
│   ├── AWS DataSync
│   │   ├── Data migration
│   │   ├── Hybrid transfer
│   │   ├── Scheduled synchronization
│   │   └── On-premises integration
│   │
│   └── AWS Transfer Family
│       ├── SFTP access
│       ├── FTPS access
│       ├── FTP access
│       └── Managed file transfer
│
├── Monitoring and Management
│   ├── Amazon CloudWatch
│   │   ├── File system metrics
│   │   ├── Throughput monitoring
│   │   ├── Burst credit monitoring
│   │   ├── Alarm creation
│   │   └── Dashboard integration
│   │
│   ├── AWS CloudTrail
│   │   ├── API activity logging
│   │   ├── Governance
│   │   ├── Auditing
│   │   └── Compliance tracking
│   │
│   ├── AWS Config
│   │   ├── Resource inventory
│   │   ├── Compliance rules
│   │   ├── Change tracking
│   │   └── Configuration history
│   │
│   └── Management Tools
│       ├── AWS Console
│       ├── AWS CLI
│       ├── SDKs
│       ├── CloudFormation
│       └── Terraform integration
│
├── Data Management
│   ├── File Operations
│   │   ├── Standard POSIX operations
│   │   ├── Concurrent access
│   │   ├── File locking
│   │   └── Metadata operations
│   │
│   ├── Migration
│   │   ├── AWS DataSync
│   │   ├── rsync
│   │   ├── NFS copy tools
│   │   ├── Hybrid migration
│   │   └── Bulk data transfer
│   │
│   ├── Backup Strategies
│   │   ├── Automated backups
│   │   ├── Point-in-time recovery
│   │   ├── Cross-account backup
│   │   └── Long-term retention
│   │
│   └── Replication Management
│       ├── Source/destination setup
│       ├── Replication monitoring
│       ├── Failover process
│       └── Recovery procedures
│
├── Use Cases
│   ├── Web Serving
│   │   ├── Shared web content
│   │   ├── CMS platforms
│   │   └── Media hosting
│   │
│   ├── Enterprise Applications
│   │   ├── SAP workloads
│   │   ├── Oracle applications
│   │   ├── Shared application storage
│   │   └── Home directories
│   │
│   ├── Analytics and ML
│   │   ├── Big data analytics
│   │   ├── Machine learning datasets
│   │   ├── Model training
│   │   └── Shared research storage
│   │
│   ├── Container Storage
│   │   ├── Kubernetes persistent volumes
│   │   ├── Shared microservices storage
│   │   ├── CI/CD pipelines
│   │   └── Stateful applications
│   │
│   ├── Media Workflows
│   │   ├── Video rendering
│   │   ├── Content editing
│   │   ├── Shared asset repositories
│   │   └── Streaming pipelines
│   │
│   └── Backup and DR
│       ├── Disaster recovery storage
│       ├── Backup repositories
│       ├── Cross-region resilience
│       └── Business continuity
│
├── Pricing
│   ├── Storage Pricing
│   │   ├── Standard pricing
│   │   ├── IA pricing
│   │   ├── Archive pricing
│   │   └── One Zone pricing
│   │
│   ├── Throughput Pricing
│   │   ├── Elastic throughput charges
│   │   ├── Provisioned throughput pricing
│   │   └── Metered throughput
│   │
│   ├── Additional Costs
│   │   ├── Backup charges
│   │   ├── Data transfer
│   │   ├── Replication charges
│   │   └── Retrieval fees
│   │
│   └── Cost Optimization
│       ├── Lifecycle policies
│       ├── Right-sizing throughput
│       ├── One Zone usage
│       └── Monitoring unused storage
│
├── Best Practices
│   ├── Architecture
│   │   ├── Multi-AZ mount targets
│   │   ├── Regional deployment
│   │   ├── HA design
│   │   └── DR planning
│   │
│   ├── Performance
│   │   ├── Use Elastic Throughput
│   │   ├── Optimize client settings
│   │   ├── Parallel workloads
│   │   └── Monitor burst credits
│   │
│   ├── Security
│   │   ├── Enable encryption
│   │   ├── Use IAM authorization
│   │   ├── Restrict security groups
│   │   ├── Use access points
│   │   └── Least privilege access
│   │
│   ├── Operations
│   │   ├── Monitor metrics
│   │   ├── Configure backups
│   │   ├── Test restores
│   │   └── Automate deployment
│   │
│   └── Cost Management
│       ├── Use lifecycle policies
│       ├── Choose proper storage class
│       ├── Monitor idle data
│       └── Evaluate One Zone carefully
│
└── Limitations and Considerations
    ├── Linux-focused file system
    ├── NFSv4.1 protocol requirement
    ├── Latency-sensitive workloads considerations
    ├── One Zone durability trade-offs
    ├── Throughput scaling behaviors
    ├── Regional service quotas
    ├── File count and metadata considerations
    ├── Network dependency
    ├── Mount target per AZ design
    └── Cost considerations for high throughput
</pre>