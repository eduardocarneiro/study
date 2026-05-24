
<pre>
AWS VPC
│
├── 1. CORE CONCEPTS
│   │
│   ├── Virtual Private Cloud (VPC)
│   │     ├── Logically isolated network
│   │     ├── Regional service
│   │     ├── IPv4 and IPv6 support
│   │     ├── Multi-AZ architecture
│   │     └── CIDR-based networking
│   │
│   ├── CIDR Blocks
│   │     ├── IPv4 CIDR
│   │     ├── IPv6 CIDR
│   │     ├── Primary CIDR
│   │     ├── Secondary CIDR
│   │     └── CIDR planning
│   │
│   ├── Subnets
│   │     ├── Public subnet
│   │     ├── Private subnet
│   │     ├── Isolated subnet
│   │     ├── Availability Zone mapping
│   │     ├── Auto-assign public IP
│   │     └── IPv6 subnet support
│   │
│   ├── Elastic Network Interfaces (ENI)
│   │     ├── Primary private IP
│   │     ├── Secondary private IPs
│   │     ├── Elastic IP association
│   │     ├── Security Groups
│   │     └── Attachment to EC2/services
│   │
│   ├── IP Addressing
│   │     ├── Private IPv4
│   │     ├── Public IPv4
│   │     ├── Elastic IPs
│   │     ├── IPv6 addressing
│   │     └── BYOIP
│   │
│   └── Route Tables
│         ├── Main route table
│         ├── Custom route tables
│         ├── Route propagation
│         ├── Static routes
│         └── Longest prefix match
│
├── 2. INTERNET CONNECTIVITY
│   │
│   ├── Internet Gateway (IGW)
│   │     ├── Public internet access
│   │     ├── VPC attachment
│   │     ├── Route table integration
│   │     └── IPv4/IPv6 support
│   │
│   ├── Egress-Only Internet Gateway
│   │     ├── IPv6 outbound-only access
│   │     └── Prevent inbound IPv6 traffic
│   │
│   ├── NAT Gateway
│   │     ├── Managed NAT service
│   │     ├── Private subnet outbound access
│   │     ├── Public NAT Gateway
│   │     ├── Elastic IP requirement
│   │     └── AZ-specific deployment
│   │
│   ├── NAT Instance
│   │     ├── EC2-based NAT
│   │     ├── Manual management
│   │     ├── Custom configurations
│   │     └── Legacy architecture
│   │
│   └── Elastic IP Addresses
│         ├── Static public IPv4
│         ├── Account quotas
│         └── Remapping
│
├── 3. VPC SECURITY
│   │
│   ├── Security Groups
│   │     ├── Stateful firewall
│   │     ├── Allow rules only
│   │     ├── Inbound rules
│   │     ├── Outbound rules
│   │     ├── SG referencing
│   │     └── ENI-level protection
│   │
│   ├── Network ACLs (NACLs)
│   │     ├── Stateless firewall
│   │     ├── Allow and deny rules
│   │     ├── Subnet-level protection
│   │     ├── Ordered rule evaluation
│   │     └── Ephemeral ports
│   │
│   ├── VPC Flow Logs
│   │     ├── Network traffic capture
│   │     ├── CloudWatch Logs
│   │     ├── Amazon S3
│   │     ├── IAM integration
│   │     └── Traffic analysis
│   │
│   ├── Traffic Mirroring
│   │     ├── Packet inspection
│   │     ├── Security monitoring
│   │     ├── IDS/IPS integration
│   │     └── ENI traffic copy
│   │
│   └── Reachability Analyzer
│         ├── Connectivity analysis
│         ├── Network path validation
│         └── Troubleshooting
│
├── 4. VPC CONNECTIVITY
│   │
│   ├── VPC Peering
│   │     ├── Private VPC-to-VPC communication
│   │     ├── Cross-account peering
│   │     ├── Cross-region peering
│   │     ├── Non-transitive routing
│   │     └── Route table updates
│   │
│   ├── AWS Transit Gateway
│   │     ├── Hub-and-spoke networking
│   │     ├── Centralized routing
│   │     ├── Multi-account connectivity
│   │     ├── Multi-VPC connectivity
│   │     ├── VPN integration
│   │     └── Direct Connect integration
│   │
│   ├── Site-to-Site VPN
│   │     ├── IPSec tunnels
│   │     ├── Customer Gateway
│   │     ├── Virtual Private Gateway
│   │     ├── BGP routing
│   │     └── Redundant tunnels
│   │
│   ├── AWS Direct Connect
│   │     ├── Dedicated private connection
│   │     ├── Hybrid cloud networking
│   │     ├── DX Gateway
│   │     └── Private/Public VIF
│   │
│   ├── Virtual Private Gateway (VGW)
│   │     ├── VPN endpoint
│   │     ├── Route propagation
│   │     └── Legacy VPN architecture
│   │
│   ├── PrivateLink
│   │     ├── Private service access
│   │     ├── Interface Endpoints
│   │     ├── Endpoint Services
│   │     ├── Consumer/provider model
│   │     └── No internet traversal
│   │
│   └── VPC Sharing
│         ├── AWS Organizations integration
│         ├── Shared subnets
│         ├── Centralized networking
│         └── Resource ownership separation
│
├── 5. VPC ENDPOINTS
│   │
│   ├── Gateway Endpoints
│   │     ├── Amazon S3
│   │     ├── DynamoDB
│   │     ├── Route table integration
│   │     └── No NAT/IGW required
│   │
│   ├── Interface Endpoints
│   │     ├── AWS PrivateLink
│   │     ├── ENI-based endpoints
│   │     ├── Private DNS
│   │     ├── Security Groups
│   │     └── AWS service connectivity
│   │
│   └── Gateway Load Balancer Endpoints
│         ├── Appliance insertion
│         ├── Transparent traffic routing
│         └── Security appliance integration
│
├── 6. ROUTING & TRAFFIC CONTROL
│   │
│   ├── Route Tables
│   │     ├── Subnet association
│   │     ├── Static routes
│   │     ├── Propagated routes
│   │     └── Route priorities
│   │
│   ├── Route Propagation
│   │     ├── VPN propagation
│   │     ├── Transit Gateway propagation
│   │     └── Dynamic routing
│   │
│   ├── Prefix Lists
│   │     ├── Managed prefix lists
│   │     ├── Customer-managed lists
│   │     └── Reusable CIDR definitions
│   │
│   └── Traffic Engineering
│         ├── Centralized egress
│         ├── Inspection VPC
│         ├── Shared services VPC
│         └── Multi-tier architectures
│
├── 7. DNS & NAME RESOLUTION
│   │
│   ├── Route 53 Resolver
│   │     ├── Recursive DNS
│   │     ├── Hybrid DNS
│   │     ├── Inbound endpoints
│   │     ├── Outbound endpoints
│   │     └── Conditional forwarding
│   │
│   ├── VPC DNS Features
│   │     ├── DNS hostnames
│   │     ├── DNS resolution
│   │     ├── AmazonProvidedDNS
│   │     └── Private DNS
│   │
│   ├── Private Hosted Zones
│   │     ├── Internal DNS zones
│   │     ├── Multi-VPC association
│   │     └── Route 53 integration
│   │
│   └── DHCP Option Sets
│         ├── Domain names
│         ├── DNS servers
│         └── NTP servers
│
├── 8. LOAD BALANCING IN VPC
│   │
│   ├── Application Load Balancer (ALB)
│   │     ├── Layer 7
│   │     ├── HTTP/HTTPS
│   │     ├── Host/path routing
│   │     └── Target groups
│   │
│   ├── Network Load Balancer (NLB)
│   │     ├── Layer 4
│   │     ├── TCP/UDP/TLS
│   │     ├── Static IP support
│   │     └── High performance
│   │
│   ├── Gateway Load Balancer (GWLB)
│   │     ├── Security appliance insertion
│   │     ├── Transparent bump-in-the-wire
│   │     └── Appliance scaling
│   │
│   └── Target Types
│         ├── Instance targets
│         ├── IP targets
│         ├── Lambda targets
│         └── ALB targets
│
├── 9. HIGH AVAILABILITY & DESIGN
│   │
│   ├── Multi-AZ Architecture
│   │     ├── Redundant subnets
│   │     ├── NAT Gateway per AZ
│   │     ├── Distributed workloads
│   │     └── Failure isolation
│   │
│   ├── Multi-Region Networking
│   │     ├── Inter-region peering
│   │     ├── Global Transit Gateway
│   │     └── Disaster recovery
│   │
│   ├── Hybrid Architecture
│   │     ├── On-premises integration
│   │     ├── Direct Connect
│   │     ├── VPN backup
│   │     └── Enterprise connectivity
│   │
│   └── Network Segmentation
│         ├── Environment isolation
│         ├── Production vs Development
│         ├── Shared services
│         └── Security boundaries
│
├── 10. MONITORING & TROUBLESHOOTING
│   │
│   ├── VPC Flow Logs
│   │     ├── ACCEPT/REJECT traffic
│   │     ├── CloudWatch Insights
│   │     └── Security auditing
│   │
│   ├── Reachability Analyzer
│   │     ├── Path simulation
│   │     ├── Routing validation
│   │     └── Connectivity debugging
│   │
│   ├── Network Access Analyzer
│   │     ├── Security posture validation
│   │     ├── Network policy analysis
│   │     └── Compliance checks
│   │
│   ├── CloudWatch Metrics
│   │     ├── NAT Gateway metrics
│   │     ├── Transit Gateway metrics
│   │     └── Endpoint monitoring
│   │
│   └── AWS Config
│         ├── Resource compliance
│         ├── Configuration history
│         └── Drift detection
│
├── 11. IPv6 NETWORKING
│   │
│   ├── IPv6 CIDR Assignment
│   │     ├── Amazon-provided IPv6
│   │     ├── BYOIPv6
│   │     └── Dual-stack VPC
│   │
│   ├── Dual-Stack Architecture
│   │     ├── IPv4 + IPv6
│   │     ├── Hybrid communication
│   │     └── Gradual migration
│   │
│   ├── IPv6 Internet Access
│   │     ├── Internet Gateway
│   │     ├── Egress-only IGW
│   │     └── Global addressing
│   │
│   └── IPv6 Routing
│         ├── IPv6 route tables
│         ├── Prefix assignments
│         └── Stateless addressing
│
├── 12. INTEGRATION WITH AWS SERVICES
│   │
│   ├── Amazon EC2
│   │     ├── ENIs
│   │     ├── Placement groups
│   │     └── Security Groups
│   │
│   ├── Amazon EKS
│   │     ├── Pod networking
│   │     ├── CNI integration
│   │     ├── Secondary IP allocation
│   │     └── Private clusters
│   │
│   ├── Amazon ECS
│   │     ├── awsvpc mode
│   │     ├── Task ENIs
│   │     └── Service networking
│   │
│   ├── AWS Lambda
│   │     ├── Lambda in VPC
│   │     ├── Hyperplane ENIs
│   │     └── Private resource access
│   │
│   ├── Amazon RDS
│   │     ├── DB subnet groups
│   │     ├── Private databases
│   │     └── Multi-AZ deployment
│   │
│   ├── Amazon S3
│   │     ├── Gateway endpoints
│   │     ├── Private access
│   │     └── VPC endpoint policies
│   │
│   └── AWS Organizations
│         ├── Shared networking
│         ├── Multi-account architecture
│         └── Centralized governance
│
└── 13. BEST PRACTICES
    │
    ├── CIDR Planning
    │     ├── Avoid overlapping CIDRs
    │     ├── Future growth planning
    │     └── Regional consistency
    │
    ├── High Availability
    │     ├── Multi-AZ NAT
    │     ├── Redundant VPN tunnels
    │     └── Fault isolation
    │
    ├── Security
    │     ├── Least privilege SGs
    │     ├── Private subnets
    │     ├── Centralized inspection
    │     └── Flow Logs enabled
    │
    ├── Cost Optimization
    │     ├── Minimize NAT traffic
    │     ├── Use Gateway Endpoints
    │     ├── Shared Transit Gateway
    │     └── Centralized networking
    │
    ├── Scalability
    │     ├── Transit Gateway over peering
    │     ├── Shared services model
    │     └── Modular architecture
    │
    └── Operational Excellence
          ├── Infrastructure as Code
          ├── Automated compliance
          ├── Tagging strategy
          └── Continuous monitoring
</pre>