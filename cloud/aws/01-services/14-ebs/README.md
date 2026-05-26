
<pre>
Amazon EBS
├── Fundamentals
│   ├── Persistent block storage for EC2
│   ├── Network-attached storage
│   ├── Designed for high availability and durability
│   ├── Data replicated within an Availability Zone
│   ├── Used as:
│   │   ├── Boot volumes
│   │   ├── Data volumes
│   │   ├── Databases
│   │   ├── File systems
│   │   ├── Containers
│   │   └── Applications
│   ├── Attached to:
│   │   └── EC2 instances
│   ├── Lifecycle independent from EC2 instance
│   └── Supports encryption and snapshots
│
├── Volume Types
│   ├── SSD Volumes
│   │   ├── General Purpose SSD (gp2)
│   │   │   ├── Balanced price/performance
│   │   │   ├── Burst capability
│   │   │   └── Legacy default SSD
│   │   │
│   │   ├── General Purpose SSD (gp3)
│   │   │   ├── Independent IOPS and throughput
│   │   │   ├── Better cost optimization
│   │   │   ├── Recommended general-purpose volume
│   │   │   └── Predictable performance
│   │   │
│   │   ├── Provisioned IOPS SSD (io1)
│   │   │   ├── High-performance workloads
│   │   │   ├── Critical databases
│   │   │   └── Supports Multi-Attach
│   │   │
│   │   └── Provisioned IOPS SSD (io2)
│   │       ├── Higher durability
│   │       ├── Mission-critical workloads
│   │       ├── SAP HANA
│   │       ├── Large databases
│   │       ├── Consistent latency
│   │       └── io2 Block Express
│   │           ├── SAN-like performance
│   │           ├── Sub-millisecond latency
│   │           ├── Very high throughput
│   │           └── High IOPS limits
│   │
│   ├── HDD Volumes
│   │   ├── Throughput Optimized HDD (st1)
│   │   │   ├── Big data
│   │   │   ├── Streaming workloads
│   │   │   ├── Data warehouses
│   │   │   └── Frequently accessed throughput-intensive workloads
│   │   │
│   │   └── Cold HDD (sc1)
│   │       ├── Lowest-cost HDD
│   │       ├── Infrequently accessed workloads
│   │       ├── Cold storage
│   │       └── Large sequential workloads
│   │
│   └── Previous Generation
│       └── Magnetic (standard)
│
├── Volume Characteristics
│   ├── Size
│   │   ├── GB to multi-TB
│   │   └── Expandable
│   │
│   ├── IOPS
│   │   ├── Input/output operations per second
│   │   ├── Determines transaction capability
│   │   └── Important for databases
│   │
│   ├── Throughput
│   │   ├── MB/s transfer rate
│   │   └── Important for streaming workloads
│   │
│   ├── Latency
│   │   ├── Time to complete operations
│   │   └── Critical for transactional systems
│   │
│   └── Durability
│       ├── Designed for high reliability
│       └── Replicated inside AZ
│
├── Volume Operations
│   ├── Create Volume
│   │   ├── Empty volume
│   │   ├── From snapshot
│   │   └── Specify:
│   │       ├── Size
│   │       ├── Type
│   │       ├── IOPS
│   │       ├── Throughput
│   │       └── Encryption
│   │
│   ├── Attach Volume
│   │   ├── Attach to EC2
│   │   ├── Same AZ requirement
│   │   ├── Device names
│   │   └── NVMe behavior on Nitro instances
│   │
│   ├── Detach Volume
│   │   ├── Safe detach recommended
│   │   ├── Unmount filesystem first
│   │   └── Avoid data corruption
│   │
│   ├── Delete Volume
│   │   ├── Permanent removal
│   │   └── Snapshots recommended before deletion
│   │
│   ├── Resize Volume
│   │   ├── Elastic Volumes
│   │   ├── Increase:
│   │   │   ├── Size
│   │   │   ├── IOPS
│   │   │   └── Throughput
│   │   └── No downtime for many workloads
│   │
│   └── Change Volume Type
│       ├── gp2 → gp3
│       ├── SSD ↔ HDD
│       └── Online modifications
│
├── Snapshots
│   ├── Point-in-time backups
│   ├── Stored in S3 internally
│   ├── Incremental backups
│   ├── Region scoped
│   ├── Used for:
│   │   ├── Backup
│   │   ├── Disaster recovery
│   │   ├── Migration
│   │   ├── Cloning
│   │   └── AMI creation
│   │
│   ├── Snapshot Operations
│   │   ├── Create snapshot
│   │   ├── Copy snapshot
│   │   ├── Share snapshot
│   │   ├── Restore snapshot
│   │   ├── Archive snapshot
│   │   └── Delete snapshot
│   │
│   ├── Fast Snapshot Restore (FSR)
│   │   ├── Reduced initialization latency
│   │   └── Immediate performance after restore
│   │
│   ├── Snapshot Archive
│   │   ├── Lower-cost tier
│   │   └── Long-term retention
│   │
│   └── Recycle Bin
│       ├── Recover deleted snapshots
│       └── Retention policies
│
├── Encryption
│   ├── AWS KMS integration
│   ├── Encryption at rest
│   ├── Encryption in transit
│   ├── Encrypt:
│   │   ├── Volumes
│   │   ├── Snapshots
│   │   └── Snapshot copies
│   ├── Customer managed keys
│   ├── AWS managed keys
│   └── Automatic encryption support
│
├── Performance Optimization
│   ├── EBS-Optimized Instances
│   │   ├── Dedicated bandwidth
│   │   └── Better storage performance
│   │
│   ├── RAID Configurations
│   │   ├── RAID 0
│   │   │   ├── Striping
│   │   │   └── Increased performance
│   │   │
│   │   ├── RAID 1
│   │   │   ├── Mirroring
│   │   │   └── Redundancy
│   │   │
│   │   └── RAID 5/6
│   │
│   ├── Initialization
│   │   ├── Lazy loading from snapshots
│   │   ├── Pre-warming historically required
│   │   └── FSR preferred
│   │
│   └── Monitoring
│       ├── CloudWatch metrics
│       ├── Volume queue length
│       ├── Burst balance
│       ├── Throughput
│       └── IOPS metrics
│
├── Multi-Attach
│   ├── Supported on io1/io2
│   ├── Attach one volume to multiple EC2 instances
│   ├── Same AZ requirement
│   ├── Cluster-aware applications
│   └── Shared storage architectures
│
├── Availability and Durability
│   ├── AZ-scoped volumes
│   ├── Snapshot cross-region copy
│   ├── Snapshot cross-account sharing
│   ├── Disaster recovery strategies
│   └── Backup automation
│
├── Integration with AWS Services
│   ├── Amazon EC2
│   ├── Amazon RDS
│   ├── Amazon ECS
│   ├── Amazon EKS
│   ├── AWS Backup
│   ├── AWS KMS
│   ├── AWS CloudTrail
│   ├── Amazon CloudWatch
│   ├── AWS Lambda
│   └── AWS Systems Manager
│
├── Monitoring and Management
│   ├── CloudWatch
│   │   ├── Metrics
│   │   ├── Alarms
│   │   └── Dashboards
│   │
│   ├── CloudTrail
│   │   ├── API auditing
│   │   └── Compliance tracking
│   │
│   ├── AWS Config
│   │   ├── Compliance rules
│   │   └── Resource tracking
│   │
│   └── EventBridge
│       └── Event-driven automation
│
├── Backup and Recovery
│   ├── Snapshot scheduling
│   ├── AWS Backup integration
│   ├── Cross-region backup
│   ├── Cross-account backup
│   ├── Point-in-time recovery patterns
│   └── Disaster recovery automation
│
├── Security
│   ├── IAM policies
│   ├── KMS permissions
│   ├── Resource-level permissions
│   ├── Encryption by default
│   ├── Secure deletion
│   └── Compliance support
│
├── Pricing Model
│   ├── Charged by:
│   │   ├── Provisioned storage
│   │   ├── IOPS
│   │   ├── Throughput
│   │   ├── Snapshot storage
│   │   └── Data transfer in some scenarios
│   │
│   ├── SSD pricing
│   ├── HDD pricing
│   ├── Snapshot archive pricing
│   └── FSR additional cost
│
├── Best Practices
│   ├── Use gp3 for general workloads
│   ├── Use io2 for critical databases
│   ├── Enable encryption by default
│   ├── Automate snapshots
│   ├── Monitor CloudWatch metrics
│   ├── Use RAID 0 for higher throughput
│   ├── Use FSR for critical restores
│   ├── Tag resources consistently
│   ├── Test recovery procedures
│   └── Optimize cost with correct volume types
│
├── Common Use Cases
│   ├── Relational databases
│   ├── NoSQL databases
│   ├── Boot disks
│   ├── Enterprise applications
│   ├── SAP workloads
│   ├── Big data analytics
│   ├── Containers
│   ├── CI/CD systems
│   ├── High-performance computing
│   └── Backup repositories
│
└── Limitations and Considerations
    ├── Volume tied to one AZ
    ├── Instance attachment limits
    ├── Multi-Attach limitations
    ├── HDD not for boot volumes
    ├── Snapshot restore initialization
    ├── Performance depends on EC2 instance type
    ├── Throughput and IOPS quotas
    └── Regional service quotas
</pre>