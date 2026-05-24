
<pre>
AWS Amazon Route 53
│
├── 1. CORE CONCEPTS
│   │
│   ├── Managed DNS Service
│   ├── Domain Registration
│   ├── DNS Routing
│   ├── Health Checking
│   ├── Traffic Management
│   ├── Highly Available DNS
│   ├── Global Service
│   ├── Authoritative DNS
│   ├── Public Hosted Zones
│   ├── Private Hosted Zones
│   ├── Resolver Service
│   └── DNS Failover
│
├── 2. DNS FUNDAMENTALS
│   │
│   ├── Domain Names
│   ├── Fully Qualified Domain Names (FQDN)
│   ├── DNS Hierarchy
│   │   ├── Root Domain
│   │   ├── Top-Level Domain (TLD)
│   │   └── Subdomains
│   │
│   ├── DNS Resolution
│   │   ├── Recursive Query
│   │   ├── Iterative Query
│   │   ├── Resolver
│   │   └── Authoritative Name Server
│   │
│   ├── DNS Propagation
│   ├── TTL (Time To Live)
│   ├── Name Servers (NS)
│   └── SOA Records
│
├── 3. HOSTED ZONES
│   │
│   ├── Public Hosted Zone
│   │   ├── Internet-facing DNS
│   │   ├── Public Domains
│   │   └── Global Resolution
│   │
│   ├── Private Hosted Zone
│   │   ├── Internal DNS
│   │   ├── VPC Association
│   │   ├── Hybrid DNS
│   │   └── Internal Applications
│   │
│   ├── Hosted Zone Management
│   │   ├── Create Hosted Zone
│   │   ├── Update Records
│   │   ├── Delete Hosted Zone
│   │   └── Delegation
│   │
│   └── Cross-Account Association
│
├── 4. DNS RECORD TYPES
│   │
│   ├── A Record
│   │   └── Maps domain to IPv4
│   │
│   ├── AAAA Record
│   │   └── Maps domain to IPv6
│   │
│   ├── CNAME Record
│   │   └── Alias one domain to another
│   │
│   ├── Alias Record
│   │   ├── AWS-specific extension
│   │   ├── Zone Apex Support
│   │   ├── No Additional Charge
│   │   └── Targets AWS Resources
│   │
│   ├── MX Record
│   │   └── Mail Servers
│   │
│   ├── TXT Record
│   │   ├── SPF
│   │   ├── DKIM
│   │   └── Domain Verification
│   │
│   ├── SRV Record
│   ├── PTR Record
│   ├── CAA Record
│   ├── NS Record
│   └── SOA Record
│
├── 5. ROUTING POLICIES
│   │
│   ├── Simple Routing
│   │   └── Single Resource
│   │
│   ├── Weighted Routing
│   │   ├── Traffic Distribution
│   │   ├── Percentage-based Routing
│   │   └── A/B Testing
│   │
│   ├── Latency-based Routing
│   │   ├── Lowest Latency
│   │   ├── Region-aware Routing
│   │   └── Global Applications
│   │
│   ├── Failover Routing
│   │   ├── Active-Passive
│   │   ├── Health Checks
│   │   └── Disaster Recovery
│   │
│   ├── Geolocation Routing
│   │   ├── User Location
│   │   ├── Country-based Routing
│   │   └── Localized Content
│   │
│   ├── Geoproximity Routing
│   │   ├── Traffic Bias
│   │   ├── AWS Regions
│   │   └── Route 53 Traffic Flow
│   │
│   ├── Multi-Value Answer Routing
│   │   ├── Multiple Healthy Endpoints
│   │   ├── Basic Load Distribution
│   │   └── Health-aware Responses
│   │
│   └── IP-based Routing
│       ├── CIDR Collections
│       └── Client IP Routing
│
├── 6. HEALTH CHECKS
│   │
│   ├── Endpoint Monitoring
│   ├── DNS Failover Integration
│   ├── Automated Recovery
│   │
│   ├── Health Check Types
│   │   ├── HTTP
│   │   ├── HTTPS
│   │   ├── TCP
│   │   ├── String Matching
│   │   └── Calculated Health Checks
│   │
│   ├── Monitoring Features
│   │   ├── Request Interval
│   │   ├── Failure Threshold
│   │   ├── CloudWatch Metrics
│   │   └── Alarm Integration
│   │
│   ├── Health Checker Locations
│   └── Regional Health Monitoring
│
├── 7. ROUTE 53 RESOLVER
│   │
│   ├── DNS Resolution for VPCs
│   ├── Recursive DNS Service
│   ├── Hybrid DNS Architectures
│   │
│   ├── Resolver Endpoints
│   │   ├── Inbound Endpoints
│   │   ├── Outbound Endpoints
│   │   └── ENI-based Architecture
│   │
│   ├── Resolver Rules
│   │   ├── Forwarding Rules
│   │   ├── System Rules
│   │   ├── Conditional Forwarding
│   │   └── Domain-based Resolution
│   │
│   ├── DNS Firewall
│   │   ├── Domain Filtering
│   │   ├── Threat Protection
│   │   ├── Allow Lists
│   │   ├── Block Lists
│   │   └── Managed Domain Lists
│   │
│   └── Resolver Query Logging
│
├── 8. DOMAIN REGISTRATION
│   │
│   ├── Register Domains
│   ├── Transfer Domains
│   ├── Renew Domains
│   ├── WHOIS Management
│   ├── Auto Renewal
│   ├── Privacy Protection
│   ├── TLD Support
│   └── DNSSEC Support
│
├── 9. TRAFFIC FLOW
│   │
│   ├── Visual Traffic Policies
│   ├── Policy Records
│   ├── Advanced Routing Logic
│   ├── Versioned Configurations
│   ├── Policy Management
│   ├── Geographic Decision Trees
│   ├── Complex Failover
│   └── Multi-Region Architectures
│
├── 10. DNSSEC
│   │
│   ├── DNS Security Extensions
│   ├── DNS Spoofing Protection
│   ├── Data Integrity
│   │
│   ├── DNSSEC for Domains
│   │   ├── Signing Hosted Zones
│   │   ├── KSK (Key Signing Key)
│   │   ├── ZSK (Zone Signing Key)
│   │   └── Chain of Trust
│   │
│   ├── Registrar Integration
│   └── Cryptographic Validation
│
├── 11. INTEGRATION WITH AWS SERVICES
│   │
│   ├── Elastic Load Balancing
│   │   ├── ALB
│   │   ├── NLB
│   │   └── GLB
│   │
│   ├── Amazon CloudFront
│   ├── Amazon S3
│   ├── API Gateway
│   ├── AWS Global Accelerator
│   ├── Elastic Beanstalk
│   ├── EC2 Instances
│   ├── ECS / EKS Services
│   ├── VPC Interface Endpoints
│   └── AWS App Runner
│
├── 12. SECURITY
│   │
│   ├── IAM Integration
│   ├── Resource-level Permissions
│   ├── Route 53 Resolver DNS Firewall
│   ├── DNSSEC
│   ├── CloudTrail Logging
│   ├── Least Privilege Access
│   ├── Query Logging
│   └── Access Control Policies
│
├── 13. MONITORING & LOGGING
│   │
│   ├── Amazon CloudWatch
│   │   ├── Metrics
│   │   ├── Alarms
│   │   └── Dashboards
│   │
│   ├── Route 53 Metrics
│   │   ├── Health Check Status
│   │   ├── DNS Query Volume
│   │   └── Resolver Metrics
│   │
│   ├── Query Logging
│   ├── Resolver Query Logs
│   ├── CloudTrail Events
│   └── Operational Visibility
│
├── 14. HIGH AVAILABILITY & DISASTER RECOVERY
│   │
│   ├── Global Distributed DNS
│   ├── Highly Available Name Servers
│   ├── Multi-Region Failover
│   ├── Active-Active Architectures
│   ├── Active-Passive Architectures
│   ├── Health-based Failover
│   ├── DR Automation
│   └── Low-latency Resolution
│
├── 15. COST MODEL
│   │
│   ├── Hosted Zones Pricing
│   ├── DNS Queries Pricing
│   ├── Health Check Charges
│   ├── Resolver Endpoint Pricing
│   ├── Traffic Flow Charges
│   ├── Domain Registration Fees
│   └── Query Logging Costs
│
├── 16. BEST PRACTICES
│   │
│   ├── Use Alias Records for AWS Resources
│   ├── Configure Health Checks
│   ├── Use Failover Routing
│   ├── Minimize DNS TTL for Dynamic Systems
│   ├── Enable DNSSEC
│   ├── Use Private Hosted Zones for Internal Apps
│   ├── Centralize Hybrid DNS
│   ├── Monitor Resolver Logs
│   ├── Use Weighted Routing for Deployments
│   └── Implement Least Privilege IAM
│
├── 17. COMMON USE CASES
│   │
│   ├── Global Web Applications
│   ├── Multi-Region Applications
│   ├── Disaster Recovery
│   ├── Blue/Green Deployments
│   ├── Hybrid Cloud DNS
│   ├── Internal Service Discovery
│   ├── Multi-cloud DNS
│   ├── Domain Registration
│   ├── Geo-targeted Applications
│   └── Centralized DNS Management
│
└── 18. LIMITATIONS & CONSIDERATIONS
    │
    ├── DNS Caching Behavior
    ├── TTL Impact
    ├── Eventual DNS Propagation
    ├── Resolver Endpoint Scaling
    ├── Health Check Regionality
    ├── Query-based Pricing
    ├── Alias Record Constraints
    ├── DNSSEC Complexity
    └── Routing Policy Design Considerations
</pre>