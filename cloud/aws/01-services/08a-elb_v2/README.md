
<pre>
AWS Elastic Load Balancing (ELB)
│
├── 1. CORE CONCEPTS
│   │
│   ├── Elastic Load Balancer
│   │     ├── Distributes incoming traffic
│   │     ├── Improves availability
│   │     ├── Supports scaling automatically
│   │     ├── Integrates with multiple AWS services
│   │     └── Acts as a single entry point
│   │
│   ├── Load Balancing
│   │     ├── Traffic distribution
│   │     ├── Fault tolerance
│   │     ├── High availability
│   │     ├── Scalability
│   │     └── Redundancy
│   │
│   ├── Listener
│   │     ├── Checks for connection requests
│   │     ├── Uses protocol + port
│   │     ├── Routes requests
│   │     └── Applies rules/actions
│   │
│   ├── Target
│   │     ├── EC2 instances
│   │     ├── IP addresses
│   │     ├── Lambda functions
│   │     ├── Containers
│   │     └── On-premises resources
│   │
│   ├── Target Group
│   │     ├── Logical grouping of targets
│   │     ├── Health check configuration
│   │     ├── Routing destination
│   │     └── Used by listeners
│   │
│   ├── Health Checks
│   │     ├── Detect unhealthy targets
│   │     ├── Remove failed resources
│   │     ├── Continuous monitoring
│   │     └── Configurable thresholds
│   │
│   └── Cross-Zone Load Balancing
│         ├── Balances traffic across AZs
│         ├── Improves utilization
│         └── Enhances fault tolerance
│
├── 2. LOAD BALANCER TYPES
│   │
│   ├── Application Load Balancer (ALB)
│   │     │
│   │     ├── Layer 7 (HTTP/HTTPS)
│   │     ├── Content-based routing
│   │     ├── Host-based routing
│   │     ├── Path-based routing
│   │     ├── Supports WebSockets
│   │     ├── HTTP/2 support
│   │     ├── gRPC support
│   │     ├── Lambda integration
│   │     ├── Container support
│   │     └── Advanced request routing
│   │
│   ├── Network Load Balancer (NLB)
│   │     │
│   │     ├── Layer 4 (TCP/UDP/TLS)
│   │     ├── Ultra-high performance
│   │     ├── Static IP support
│   │     ├── Elastic IP support
│   │     ├── Preserves source IP
│   │     ├── Extremely low latency
│   │     ├── Millions of requests/sec
│   │     └── TLS termination support
│   │
│   ├── Gateway Load Balancer (GWLB)
│   │     │
│   │     ├── Layer 3 gateway appliance
│   │     ├── Transparent network gateway
│   │     ├── Traffic inspection
│   │     ├── Security appliance insertion
│   │     ├── Third-party virtual appliances
│   │     ├── Uses GENEVE protocol
│   │     └── Centralized security architecture
│   │
│   └── Classic Load Balancer (CLB)
│         │
│         ├── Legacy generation
│         ├── Layer 4 + Layer 7 support
│         ├── EC2-Classic support
│         ├── Basic balancing features
│         └── Older applications compatibility
│
├── 3. NETWORKING & ARCHITECTURE
│   │
│   ├── Availability Zones
│   │     ├── Multi-AZ deployment
│   │     ├── Automatic failover
│   │     └── High availability
│   │
│   ├── Subnets
│   │     ├── Public subnets
│   │     ├── Private subnets
│   │     └── AZ mapping
│   │
│   ├── VPC Integration
│   │     ├── VPC association
│   │     ├── Routing configuration
│   │     ├── Internal load balancers
│   │     └── Internet-facing load balancers
│   │
│   ├── IP Address Types
│   │     ├── IPv4
│   │     ├── Dualstack
│   │     └── IPv6
│   │
│   ├── DNS Integration
│   │     ├── Route 53 integration
│   │     ├── DNS-based access
│   │     └── Alias records
│   │
│   └── Elastic Network Interfaces (ENIs)
│         ├── Automatically managed
│         ├── Per-subnet interfaces
│         └── Scaling support
│
├── 4. LISTENERS & ROUTING
│   │
│   ├── Listener Protocols
│   │     ├── HTTP
│   │     ├── HTTPS
│   │     ├── TCP
│   │     ├── TLS
│   │     ├── UDP
│   │     └── TCP_UDP
│   │
│   ├── Listener Rules
│   │     ├── Priority-based evaluation
│   │     ├── Conditions
│   │     ├── Actions
│   │     └── Default rules
│   │
│   ├── Routing Conditions
│   │     ├── Host headers
│   │     ├── URL paths
│   │     ├── HTTP headers
│   │     ├── Query strings
│   │     ├── HTTP methods
│   │     └── Source IP
│   │
│   ├── Actions
│   │     ├── Forward
│   │     ├── Redirect
│   │     ├── Fixed response
│   │     ├── Authenticate
│   │     └── Weighted routing
│   │
│   └── Sticky Sessions
│         ├── Session persistence
│         ├── Cookie-based affinity
│         └── Stateful applications
│
├── 5. TARGET GROUPS
│   │
│   ├── Target Types
│   │     ├── Instance targets
│   │     ├── IP targets
│   │     ├── Lambda targets
│   │     └── ALB targets
│   │
│   ├── Registration
│   │     ├── Manual registration
│   │     ├── Auto Scaling integration
│   │     ├── ECS integration
│   │     └── EKS integration
│   │
│   ├── Deregistration
│   │     ├── Connection draining
│   │     ├── Graceful removal
│   │     └── Deregistration delay
│   │
│   ├── Load Balancing Algorithms
│   │     ├── Round robin
│   │     ├── Least outstanding requests
│   │     └── Flow hash
│   │
│   └── Slow Start Mode
│         ├── Gradual traffic ramp-up
│         ├── Warm-up period
│         └── Newly registered targets
│
├── 6. HEALTH CHECKS
│   │
│   ├── Health Check Configuration
│   │     ├── Protocol selection
│   │     ├── Health check path
│   │     ├── Port configuration
│   │     ├── Success codes
│   │     └── Timeouts
│   │
│   ├── Thresholds
│   │     ├── Healthy threshold
│   │     ├── Unhealthy threshold
│   │     ├── Interval
│   │     └── Timeout
│   │
│   ├── Health States
│   │     ├── Initial
│   │     ├── Healthy
│   │     ├── Unhealthy
│   │     ├── Draining
│   │     └── Unused
│   │
│   └── Failover Behavior
│         ├── Remove unhealthy targets
│         ├── Route to healthy targets
│         └── Automatic recovery
│
├── 7. SECURITY
│   │
│   ├── TLS/SSL Termination
│   │     ├── HTTPS listeners
│   │     ├── TLS listeners
│   │     ├── Offloading encryption
│   │     └── Certificate management
│   │
│   ├── AWS Certificate Manager (ACM)
│   │     ├── Managed certificates
│   │     ├── Automatic renewal
│   │     └── TLS integration
│   │
│   ├── Security Policies
│   │     ├── TLS versions
│   │     ├── Cipher suites
│   │     └── Compliance support
│   │
│   ├── Security Groups
│   │     ├── Inbound rules
│   │     ├── Outbound rules
│   │     └── Traffic filtering
│   │
│   ├── IAM Integration
│   │     ├── Access control
│   │     ├── Permissions
│   │     └── API authorization
│   │
│   ├── Authentication
│   │     ├── Amazon Cognito
│   │     ├── OIDC providers
│   │     └── User authentication
│   │
│   ├── AWS WAF Integration
│   │     ├── Web application firewall
│   │     ├── Threat protection
│   │     ├── Rate limiting
│   │     └── Bot mitigation
│   │
│   └── Shield Integration
│         ├── DDoS protection
│         ├── Shield Standard
│         └── Shield Advanced
│
├── 8. MONITORING & LOGGING
│   │
│   ├── Amazon CloudWatch
│   │     ├── Metrics
│   │     ├── Alarms
│   │     ├── Dashboards
│   │     └── Monitoring
│   │
│   ├── Common Metrics
│   │     ├── Request count
│   │     ├── Latency
│   │     ├── Healthy hosts
│   │     ├── Unhealthy hosts
│   │     ├── HTTP status codes
│   │     └── Active connections
│   │
│   ├── Access Logs
│   │     ├── Request logging
│   │     ├── Stored in S3
│   │     ├── Traffic analysis
│   │     └── Security auditing
│   │
│   ├── AWS CloudTrail
│   │     ├── API logging
│   │     ├── Audit history
│   │     └── Governance
│   │
│   └── Monitoring Integrations
│         ├── AWS X-Ray
│         ├── SIEM tools
│         └── Observability platforms
│
├── 9. SCALABILITY & PERFORMANCE
│   │
│   ├── Automatic Scaling
│   │     ├── Managed scaling
│   │     ├── Elastic capacity
│   │     └── Dynamic adjustment
│   │
│   ├── High Throughput
│   │     ├── Millions of requests
│   │     ├── High bandwidth
│   │     └── Burst handling
│   │
│   ├── Connection Handling
│   │     ├── Idle timeout
│   │     ├── Persistent connections
│   │     └── Connection multiplexing
│   │
│   ├── Performance Optimization
│   │     ├── HTTP keep-alive
│   │     ├── Connection reuse
│   │     └── Efficient routing
│   │
│   └── Zonal Shift
│         ├── Shift traffic from AZ
│         ├── Availability improvements
│         └── Resilience support
│
├── 10. INTEGRATIONS
│   │
│   ├── EC2 Auto Scaling
│   │     ├── Dynamic scaling
│   │     ├── Automatic registration
│   │     └── Health coordination
│   │
│   ├── Amazon ECS
│   │     ├── Container balancing
│   │     ├── Dynamic ports
│   │     └── Service discovery
│   │
│   ├── Amazon EKS
│   │     ├── Kubernetes ingress
│   │     ├── ALB controller
│   │     └── Container networking
│   │
│   ├── AWS Lambda
│   │     ├── Serverless targets
│   │     ├── Event-based invocation
│   │     └── ALB integration
│   │
│   ├── Route 53
│   │     ├── DNS failover
│   │     ├── Alias integration
│   │     └── Traffic routing
│   │
│   ├── Global Accelerator
│   │     ├── Global traffic optimization
│   │     ├── Static Anycast IPs
│   │     └── Low latency routing
│   │
│   └── PrivateLink
│         ├── Private connectivity
│         ├── NLB integration
│         └── Secure service access
│
├── 11. HIGH AVAILABILITY & DISASTER RECOVERY
│   │
│   ├── Multi-AZ Resilience
│   │     ├── Fault isolation
│   │     ├── Redundant infrastructure
│   │     └── Automatic recovery
│   │
│   ├── Fault Tolerance
│   │     ├── Health monitoring
│   │     ├── Traffic redistribution
│   │     └── Failure detection
│   │
│   ├── Regional Architecture
│   │     ├── Region-specific deployment
│   │     ├── Cross-region patterns
│   │     └── DR strategies
│   │
│   └── Traffic Recovery
│         ├── Fast rerouting
│         ├── Target replacement
│         └── Operational continuity
│
├── 12. COST & BILLING
│   │
│   ├── Pricing Dimensions
│   │     ├── Running hours
│   │     ├── LCUs (ALB)
│   │     ├── NLCUs (NLB)
│   │     └── GWLCUs (GWLB)
│   │
│   ├── Cost Factors
│   │     ├── Processed bytes
│   │     ├── Active connections
│   │     ├── Rule evaluations
│   │     └── New connections
│   │
│   ├── Cost Optimization
│   │     ├── Efficient routing
│   │     ├── Right-sized architecture
│   │     ├── Reduce idle resources
│   │     └── Monitoring usage
│   │
│   └── Billing Tools
│         ├── AWS Cost Explorer
│         ├── AWS Budgets
│         └── CUR reports
│
├── 13. BEST PRACTICES
│   │
│   ├── Use Multi-AZ deployments
│   ├── Enable health checks
│   ├── Use HTTPS/TLS everywhere
│   ├── Integrate with Auto Scaling
│   ├── Enable access logging
│   ├── Use WAF for web workloads
│   ├── Separate internal vs public traffic
│   ├── Use least privilege IAM
│   ├── Monitor CloudWatch metrics
│   ├── Tune idle timeout settings
│   ├── Use target groups effectively
│   ├── Use path/host-based routing
│   └── Test failover scenarios
│
├── 14. COMMON ARCHITECTURE PATTERNS
│   │
│   ├── Internet-facing Web Applications
│   │     ├── ALB + EC2
│   │     ├── ALB + ECS
│   │     └── ALB + Lambda
│   │
│   ├── Internal Microservices
│   │     ├── Internal ALB
│   │     ├── Service-to-service routing
│   │     └── East-west traffic
│   │
│   ├── High Performance TCP Applications
│   │     ├── NLB + EC2
│   │     ├── Gaming workloads
│   │     └── Financial systems
│   │
│   ├── Security Appliance Architecture
│   │     ├── GWLB insertion
│   │     ├── Central inspection VPC
│   │     └── Firewall scaling
│   │
│   ├── Hybrid Connectivity
│   │     ├── On-premises targets
│   │     ├── IP target groups
│   │     └── Direct Connect/VPN
│   │
│   └── Blue/Green Deployments
│         ├── Weighted target groups
│         ├── Canary releases
│         └── Progressive delivery
│
└── 15. TROUBLESHOOTING
    │
    ├── Unhealthy Targets
    │     ├── Security group issues
    │     ├── Incorrect health check path
    │     ├── Application failures
    │     └── Network ACL issues
    │
    ├── Connectivity Problems
    │     ├── Listener misconfiguration
    │     ├── DNS resolution issues
    │     ├── Route table problems
    │     └── Port mismatches
    │
    ├── TLS/SSL Errors
    │     ├── Invalid certificates
    │     ├── Cipher mismatch
    │     ├── Expired certificates
    │     └── TLS negotiation failure
    │
    ├── Performance Issues
    │     ├── High latency
    │     ├── Connection exhaustion
    │     ├── Backend bottlenecks
    │     └── Scaling limitations
    │
    └── Diagnostic Tools
          ├── CloudWatch metrics
          ├── Access logs
          ├── VPC Flow Logs
          ├── Reachability Analyzer
          └── CloudTrail
</pre>