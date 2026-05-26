
<pre>
AWS Amazon S3
│
├── 1. Fundamentals
│   ├── Object Storage
│   │   ├── Stores data as objects
│   │   ├── Objects = Data + Metadata + Key
│   │   ├── Flat structure (no real folders)
│   │   └── Unlimited objects per bucket
│   │
│   ├── Buckets
│   │   ├── Globally unique name
│   │   ├── Region-specific
│   │   ├── Container for objects
│   │   ├── Naming rules
│   │   └── Bucket quotas
│   │
│   ├── Objects
│   │   ├── Max size = 5 TB
│   │   ├── Metadata
│   │   ├── Object keys
│   │   ├── ETags
│   │   ├── Tags
│   │   └── Storage classes
│   │
│   ├── Data Consistency
│   │   ├── Strong read-after-write
│   │   ├── Strong overwrite consistency
│   │   └── Strong delete consistency
│   │
│   └── S3 URLs
│       ├── Virtual-hosted-style
│       ├── Path-style (legacy)
│       └── Static website endpoint
│
├── 2. Storage Classes
│   ├── S3 Standard
│   │   ├── Frequently accessed data
│   │   ├── Multi-AZ
│   │   └── Low latency
│   │
│   ├── S3 Intelligent-Tiering
│   │   ├── Automatic tier movement
│   │   ├── Cost optimization
│   │   ├── Frequent tier
│   │   ├── Infrequent tier
│   │   ├── Archive Instant Access
│   │   ├── Archive Access
│   │   └── Deep Archive Access
│   │
│   ├── S3 Standard-IA
│   │   ├── Infrequent access
│   │   ├── Lower cost
│   │   └── Retrieval fee
│   │
│   ├── S3 One Zone-IA
│   │   ├── Single AZ storage
│   │   ├── Lower cost
│   │   └── Less resilient
│   │
│   ├── S3 Glacier Instant Retrieval
│   │   ├── Archive workloads
│   │   ├── Millisecond retrieval
│   │   └── Low-cost storage
│   │
│   ├── S3 Glacier Flexible Retrieval
│   │   ├── Minutes to hours retrieval
│   │   ├── Expedited retrieval
│   │   ├── Standard retrieval
│   │   └── Bulk retrieval
│   │
│   ├── S3 Glacier Deep Archive
│   │   ├── Lowest-cost storage
│   │   ├── Long-term retention
│   │   └── Hours retrieval time
│   │
│   └── S3 on Outposts
│       ├── On-premises object storage
│       └── AWS Outposts integration
│
├── 3. Security & Access Control
│   ├── IAM Policies
│   │   ├── Identity-based policies
│   │   ├── Allow/Deny actions
│   │   └── Resource permissions
│   │
│   ├── Bucket Policies
│   │   ├── Resource-based policy
│   │   ├── Cross-account access
│   │   ├── Public access control
│   │   └── Conditional permissions
│   │
│   ├── ACLs (Legacy)
│   │   ├── Bucket ACLs
│   │   ├── Object ACLs
│   │   └── Canonical users
│   │
│   ├── Block Public Access
│   │   ├── Block public ACLs
│   │   ├── Ignore public ACLs
│   │   ├── Block public bucket policies
│   │   └── Restrict public buckets
│   │
│   ├── Object Ownership
│   │   ├── Bucket owner enforced
│   │   ├── ACLs disabled
│   │   └── Simplified permissions
│   │
│   ├── Access Points
│   │   ├── Application-specific access
│   │   ├── Unique hostnames
│   │   ├── Simplified permissions
│   │   └── VPC-restricted access
│   │
│   ├── Multi-Region Access Points
│   │   ├── Global endpoint
│   │   ├── Traffic routing
│   │   ├── Multi-region resilience
│   │   └── Failover support
│   │
│   ├── VPC Endpoints
│   │   ├── Private connectivity
│   │   ├── Gateway endpoints
│   │   └── Interface endpoints
│   │
│   ├── Encryption
│   │   ├── Server-Side Encryption (SSE)
│   │   │   ├── SSE-S3
│   │   │   ├── SSE-KMS
│   │   │   └── SSE-C
│   │   │
│   │   ├── Client-Side Encryption
│   │   └── Encryption in transit (TLS)
│   │
│   └── AWS KMS Integration
│       ├── Customer managed keys
│       ├── Key rotation
│       └── Audit logging
│
├── 4. Data Management
│   ├── Versioning
│   │   ├── Preserve object versions
│   │   ├── Delete markers
│   │   ├── Recovery protection
│   │   └── MFA Delete
│   │
│   ├── Lifecycle Rules
│   │   ├── Transition actions
│   │   ├── Expiration actions
│   │   ├── Storage class movement
│   │   └── Automated archival
│   │
│   ├── Object Lock
│   │   ├── WORM protection
│   │   ├── Governance mode
│   │   ├── Compliance mode
│   │   └── Retention periods
│   │
│   ├── Replication
│   │   ├── Same-Region Replication (SRR)
│   │   ├── Cross-Region Replication (CRR)
│   │   ├── Replication Time Control (RTC)
│   │   └── Metadata replication
│   │
│   ├── Batch Operations
│   │   ├── Bulk object actions
│   │   ├── Copy operations
│   │   ├── Tagging operations
│   │   └── Lambda integration
│   │
│   ├── Inventory
│   │   ├── Object reports
│   │   ├── CSV/ORC/Parquet output
│   │   └── Audit support
│   │
│   ├── Storage Lens
│   │   ├── Organization-wide metrics
│   │   ├── Usage insights
│   │   └── Cost optimization
│   │
│   └── Object Tagging
│       ├── Key-value tags
│       ├── Lifecycle filtering
│       ├── Access management
│       └── Cost allocation
│
├── 5. Data Transfer & Upload
│   ├── Multipart Upload
│   │   ├── Parallel uploads
│   │   ├── Resume uploads
│   │   └── Large object optimization
│   │
│   ├── Presigned URLs
│   │   ├── Temporary access
│   │   ├── Secure sharing
│   │   └── Time-limited permissions
│   │
│   ├── S3 Transfer Acceleration
│   │   ├── Edge location upload
│   │   ├── Faster global transfer
│   │   └── CloudFront edge network
│   │
│   ├── AWS DataSync
│   │   ├── Automated transfers
│   │   ├── On-premises integration
│   │   └── Data migration
│   │
│   ├── AWS Snow Family
│   │   ├── Snowcone
│   │   ├── Snowball
│   │   ├── Snowmobile
│   │   └── Offline transfers
│   │
│   └── Upload Methods
│       ├── Console upload
│       ├── AWS CLI
│       ├── SDKs
│       ├── REST API
│       └── AWS Transfer Family
│
├── 6. Hosting & Analytics
│   ├── Static Website Hosting
│   │   ├── Website endpoints
│   │   ├── Index documents
│   │   ├── Error documents
│   │   └── Public content hosting
│   │
│   ├── Event Notifications
│   │   ├── Object-created events
│   │   ├── Object-removed events
│   │   ├── Lambda integration
│   │   ├── SNS integration
│   │   └── SQS integration
│   │
│   ├── Query in Place
│   │   ├── S3 Select
│   │   ├── Glacier Select
│   │   └── SQL-like queries
│   │
│   ├── Athena Integration
│   │   ├── SQL queries on S3
│   │   ├── Serverless analytics
│   │   └── Data lake architecture
│   │
│   ├── Redshift Integration
│   │   ├── COPY command
│   │   ├── Spectrum
│   │   └── Data warehouse integration
│   │
│   └── Lake Formation
│       ├── Centralized governance
│       ├── Data catalog
│       └── Secure analytics
│
├── 7. Monitoring & Logging
│   ├── CloudWatch Metrics
│   │   ├── Bucket metrics
│   │   ├── Request metrics
│   │   └── Storage metrics
│   │
│   ├── Server Access Logging
│   │   ├── Request logs
│   │   ├── Access auditing
│   │   └── Usage analysis
│   │
│   ├── CloudTrail
│   │   ├── API activity logging
│   │   ├── Governance
│   │   └── Compliance auditing
│   │
│   ├── EventBridge
│   │   ├── Event-driven automation
│   │   └── Workflow orchestration
│   │
│   └── AWS Config
│       ├── Resource compliance
│       ├── Drift detection
│       └── Configuration history
│
├── 8. Performance Optimization
│   ├── Prefix Partitioning
│   │   ├── Automatic scaling
│   │   ├── High request rates
│   │   └── Optimized prefixes
│   │
│   ├── Request Rate Performance
│   │   ├── PUT/COPY/POST/DELETE
│   │   ├── GET/HEAD
│   │   └── Parallelization
│   │
│   ├── Byte-Range Fetches
│   │   ├── Partial downloads
│   │   └── Large file optimization
│   │
│   ├── Caching
│   │   ├── CloudFront integration
│   │   ├── Edge caching
│   │   └── Reduced latency
│   │
│   └── Performance Guidelines
│       ├── Retry strategies
│       ├── Timeout handling
│       ├── Horizontal scaling
│       └── Connection reuse
│
├── 9. Cost Optimization
│   ├── Storage Class Optimization
│   ├── Lifecycle Policies
│   ├── Intelligent-Tiering
│   ├── Request Cost Reduction
│   ├── Compression
│   ├── Storage Lens Recommendations
│   ├── Reserved Capacity (Glacier)
│   └── Cost Allocation Tags
│
├── 10. Compliance & Durability
│   ├── Durability
│   │   ├── 11 nines durability
│   │   ├── Multi-AZ redundancy
│   │   └── Self-healing infrastructure
│   │
│   ├── Availability
│   │   ├── SLA guarantees
│   │   └── Regional resilience
│   │
│   ├── Compliance Programs
│   │   ├── HIPAA
│   │   ├── PCI DSS
│   │   ├── FedRAMP
│   │   ├── GDPR
│   │   └── ISO certifications
│   │
│   └── Data Protection
│       ├── Backup strategies
│       ├── Replication
│       ├── Immutable storage
│       └── Encryption
│
├── 11. Integration with AWS Services
│   ├── Amazon CloudFront
│   ├── AWS Lambda
│   ├── Amazon EC2
│   ├── Amazon EBS Snapshots
│   ├── Amazon Athena
│   ├── AWS Glue
│   ├── AWS Backup
│   ├── Amazon Macie
│   ├── AWS IAM
│   ├── AWS Organizations
│   ├── AWS Config
│   └── AWS CloudTrail
│
├── 12. Common Use Cases
│   ├── Backup and Restore
│   ├── Data Archiving
│   ├── Static Website Hosting
│   ├── Media Hosting
│   ├── Data Lakes
│   ├── Disaster Recovery
│   ├── Log Storage
│   ├── Big Data Analytics
│   ├── Application Assets
│   └── Software Distribution
│
└── 13. Best Practices
    ├── Enable Versioning
    ├── Block Public Access
    ├── Use Least Privilege
    ├── Enable Encryption
    ├── Configure Lifecycle Policies
    ├── Use Replication
    ├── Monitor with CloudWatch
    ├── Use Access Points
    ├── Optimize Storage Classes
    ├── Enable Logging
    ├── Protect with Object Lock
    └── Automate Compliance Checks
</pre>