
<pre>
AWS Network Load Balancer (NLB)
│
├── 1. CORE CONCEPTS
│   │
│   ├── Layer 4 Load Balancer
│   │     ├── Operates at TCP/UDP/TLS level
│   │     ├── Extremely high performance
│   │     ├── Ultra-low latency
│   │     ├── Millions of requests per second
│   │     └── Static IP support
│   │
│   ├── Regional Service
│   │     ├── Spans multiple AZs
│   │     ├── Fault tolerant
│   │     └── Highly available
│   │
│   ├── Flow Hash Routing
│   │     ├── Based on:
│   │     │     ├── Protocol
│   │     │     ├── Source IP
│   │     │     ├── Source Port
│   │     │     ├── Destination IP
│   │     │     └── Destination Port
│   │     └── Ensures connection consistency
│   │
│   ├── Static IP Addresses
│   │     ├── One per Availability Zone
│   │     ├── Elastic IP support
│   │     └── Predictable endpoints
│   │
│   ├── Targets
│   │     ├── EC2 instances
│   │     ├── IP addresses
│   │     ├── Application Load Balancers
│   │     └── Containers / Pods
│   │
│   └── Listener-Based Traffic Distribution
│         ├── Front-end listener
│         ├── Protocol handling
│         └── Target group forwarding
│
├── 2. ARCHITECTURE COMPONENTS
│   │
│   ├── Load Balancer
│   │     ├── Internet-facing
│   │     ├── Internal
│   │     ├── Multi-AZ deployment
│   │     └── DNS endpoint
│   │
│   ├── Listeners
│   │     ├── TCP
│   │     ├── TLS
│   │     ├── UDP
│   │     └── TCP_UDP
│   │
│   ├── Target Groups
│   │     ├── Protocol-specific
│   │     ├── Port mapping
│   │     ├── Health checks
│   │     └── Routing destination
│   │
│   ├── Targets
│   │     ├── Instance targets
│   │     ├── IP targets
│   │     └── ALB targets
│   │
│   ├── Availability Zones
│   │     ├── Cross-zone balancing
│   │     ├── Zone affinity
│   │     └── Fault isolation
│   │
│   └── Elastic Network Interfaces (ENIs)
│         ├── Created per subnet
│         ├── Managed by AWS
│         └── Used for traffic entry points
│
├── 3. LISTENERS
│   │
│   ├── TCP Listener
│   │     ├── Pass-through TCP traffic
│   │     ├── No TLS termination
│   │     └── End-to-end encryption possible
│   │
│   ├── TLS Listener
│   │     ├── TLS termination
│   │     ├── Certificate management
│   │     ├── Security policies
│   │     └── SNI support
│   │
│   ├── UDP Listener
│   │     ├── Stateless traffic
│   │     ├── DNS workloads
│   │     ├── Gaming workloads
│   │     └── Streaming workloads
│   │
│   ├── TCP_UDP Listener
│   │     ├── Combined protocol handling
│   │     └── Shared port support
│   │
│   └── Listener Configuration
│         ├── Port definition
│         ├── Protocol selection
│         ├── Certificates
│         └── Default actions
│
├── 4. TARGET GROUPS
│   │
│   ├── Target Types
│   │     ├── Instance
│   │     ├── IP
│   │     └── ALB
│   │
│   ├── Routing Configuration
│   │     ├── Protocol
│   │     ├── Port
│   │     ├── Health checks
│   │     └── Stickiness
│   │
│   ├── Health Checks
│   │     ├── TCP
│   │     ├── HTTP
│   │     ├── HTTPS
│   │     ├── Configurable thresholds
│   │     └── Success/failure detection
│   │
│   ├── Connection Handling
│   │     ├── Long-lived TCP support
│   │     ├── Flow persistence
│   │     └── High throughput optimization
│   │
│   └── Deregistration
│         ├── Connection draining
│         ├── Graceful shutdown
│         └── Deregistration delay
│
├── 5. NETWORKING FEATURES
│   │
│   ├── Static IP Support
│   │     ├── Elastic IP association
│   │     ├── Allowlist compatibility
│   │     └── Firewall-friendly
│   │
│   ├── Source IP Preservation
│   │     ├── Client IP visible to targets
│   │     ├── Native preservation
│   │     └── No proxy translation
│   │
│   ├── IPv4 and IPv6
│   │     ├── Dualstack support
│   │     ├── IPv6 clients
│   │     └── Mixed environments
│   │
│   ├── Cross-Zone Load Balancing
│   │     ├── Even distribution
│   │     ├── Optional feature
│   │     └── Inter-AZ traffic considerations
│   │
│   ├── PrivateLink Integration
│   │     ├── Endpoint services
│   │     ├── Private connectivity
│   │     └── Service provider architectures
│   │
│   └── Hybrid Connectivity
│         ├── On-premises integration
│         ├── VPN support
│         ├── Direct Connect
│         └── Hybrid cloud architectures
│
├── 6. SECURITY FEATURES
│   │
│   ├── TLS Termination
│   │     ├── SSL/TLS offloading
│   │     ├── ACM integration
│   │     ├── IAM certificate support
│   │     └── Security policy selection
│   │
│   ├── Security Groups
│   │     ├── NLB security groups support
│   │     ├── Inbound filtering
│   │     └── Outbound filtering
│   │
│   ├── Access Control
│   │     ├── VPC-level isolation
│   │     ├── Subnet control
│   │     └── Target-level security
│   │
│   ├── PrivateLink Security
│   │     ├── Private service exposure
│   │     ├── Controlled consumer access
│   │     └── Internal-only services
│   │
│   └── Compliance
│         ├── Encryption in transit
│         ├── Audit logging
│         ├── Secure architectures
│         └── Regulatory support
│
├── 7. HIGH AVAILABILITY & SCALING
│   │
│   ├── Automatic Scaling
│   │     ├── Handles traffic spikes
│   │     ├── No pre-warming required
│   │     └── Managed capacity
│   │
│   ├── Multi-AZ Redundancy
│   │     ├── Fault tolerance
│   │     ├── AZ isolation
│   │     └── Redundant nodes
│   │
│   ├── Health-Based Failover
│   │     ├── Removes unhealthy targets
│   │     ├── Automatic recovery
│   │     └── Continuous monitoring
│   │
│   ├── Connection Resilience
│   │     ├── Long-lived connections
│   │     ├── Persistent TCP sessions
│   │     └── Stable throughput
│   │
│   └── Zonal Architecture
│         ├── Independent scaling per AZ
│         ├── Static zonal IPs
│         └── Availability optimization
│
├── 8. MONITORING & OBSERVABILITY
│   │
│   ├── Amazon CloudWatch
│   │     ├── ActiveFlowCount
│   │     ├── ProcessedBytes
│   │     ├── HealthyHostCount
│   │     ├── UnHealthyHostCount
│   │     └── NewFlowCount
│   │
│   ├── Access Logs
│   │     ├── Connection logging
│   │     ├── TLS information
│   │     ├── Stored in S3
│   │     └── Traffic auditing
│   │
│   ├── AWS CloudTrail
│   │     ├── API activity logging
│   │     ├── Configuration auditing
│   │     └── Security investigations
│   │
│   ├── Health Monitoring
│   │     ├── Target health visibility
│   │     ├── Route health checks
│   │     └── Failure diagnostics
│   │
│   └── Metrics & Alarms
│         ├── Threshold monitoring
│         ├── Notifications
│         └── Automated remediation
│
├── 9. INTEGRATIONS
│   │
│   ├── Amazon EC2
│   │     ├── Instance targets
│   │     └── Auto Scaling integration
│   │
│   ├── Amazon ECS
│   │     ├── Containerized workloads
│   │     ├── Dynamic port mapping
│   │     └── Service load balancing
│   │
│   ├── Amazon EKS
│   │     ├── Kubernetes services
│   │     ├── Pod IP targets
│   │     └── Ingress architectures
│   │
│   ├── AWS PrivateLink
│   │     ├── Endpoint services
│   │     └── Private service publishing
│   │
│   ├── AWS Global Accelerator
│   │     ├── Global entry points
│   │     ├── Traffic acceleration
│   │     └── Improved latency
│   │
│   └── AWS Certificate Manager (ACM)
│         ├── TLS certificates
│         ├── Automatic renewal
│         └── Secure listener support
│
├── 10. USE CASES
│   │
│   ├── High-Performance TCP Applications
│   │     ├── Financial systems
│   │     ├── Trading platforms
│   │     └── Real-time systems
│   │
│   ├── Gaming Platforms
│   │     ├── UDP traffic
│   │     ├── Real-time sessions
│   │     └── Low latency networking
│   │
│   ├── IoT Platforms
│   │     ├── Massive connection scaling
│   │     ├── MQTT traffic
│   │     └── Device communication
│   │
│   ├── Hybrid Architectures
│   │     ├── On-premises targets
│   │     ├── Private connectivity
│   │     └── Multi-environment deployments
│   │
│   ├── TLS Offloading
│   │     ├── Certificate centralization
│   │     ├── Backend simplification
│   │     └── Performance optimization
│   │
│   └── Private Services
│         ├── AWS PrivateLink
│         ├── Internal APIs
│         └── SaaS provider architectures
│
├── 11. BEST PRACTICES
│   │
│   ├── Architecture Design
│   │     ├── Use Multi-AZ deployments
│   │     ├── Separate target groups
│   │     └── Design for failure
│   │
│   ├── Performance Optimization
│   │     ├── Enable cross-zone carefully
│   │     ├── Tune health checks
│   │     └── Optimize backend scaling
│   │
│   ├── Security
│   │     ├── Use TLS listeners
│   │     ├── Restrict access
│   │     ├── Rotate certificates
│   │     └── Apply least privilege
│   │
│   ├── Monitoring
│   │     ├── Configure alarms
│   │     ├── Analyze access logs
│   │     └── Monitor unhealthy targets
│   │
│   ├── Networking
│   │     ├── Plan subnet capacity
│   │     ├── Use static IPs when needed
│   │     └── Validate routing paths
│   │
│   └── Operations
│         ├── Use Infrastructure as Code
│         ├── Automate deployments
│         ├── Test failover regularly
│         └── Implement blue/green deployments
│
└── 12. COMPARISON WITH OTHER LOAD BALANCERS
    │
    ├── Application Load Balancer (ALB)
    │     ├── Layer 7
    │     ├── HTTP/HTTPS only
    │     ├── Content-based routing
    │     └── Microservices/web apps
    │
    ├── Network Load Balancer (NLB)
    │     ├── Layer 4
    │     ├── TCP/UDP/TLS
    │     ├── Ultra-high performance
    │     ├── Static IPs
    │     └── Low latency workloads
    │
    ├── Gateway Load Balancer (GWLB)
    │     ├── Layer 3 + Layer 4
    │     ├── Security appliances
    │     ├── Transparent traffic inspection
    │     └── Firewall architectures
    │
    └── Classic Load Balancer (CLB)
          ├── Legacy service
          ├── Basic Layer 4/7 support
          └── Older generation ELB
</pre>