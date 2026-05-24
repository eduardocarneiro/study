
<pre>
AWS Application Load Balancer (ALB)
│
├── 1. CORE CONCEPTS
│   │
│   ├── Layer 7 Load Balancer
│   │     ├── Operates at HTTP/HTTPS layer
│   │     ├── Content-aware routing
│   │     ├── Intelligent request handling
│   │     └── Designed for modern applications
│   │
│   ├── Part of Elastic Load Balancing (ELB)
│   │     ├── ALB
│   │     ├── NLB (Network Load Balancer)
│   │     ├── GWLB (Gateway Load Balancer)
│   │     └── CLB (Classic Load Balancer)
│   │
│   ├── High Availability
│   │     ├── Multi-AZ deployment
│   │     ├── Automatic scaling
│   │     ├── Fault tolerance
│   │     └── AWS-managed infrastructure
│   │
│   ├── Listener
│   │     ├── Checks for connection requests
│   │     ├── Uses protocol + port
│   │     ├── HTTP
│   │     ├── HTTPS
│   │     └── Rules evaluation
│   │
│   ├── Rules
│   │     ├── Conditions
│   │     ├── Actions
│   │     ├── Priority order
│   │     └── Default rule
│   │
│   ├── Target Group
│   │     ├── Group of backend resources
│   │     ├── Routing destination
│   │     ├── Health checks
│   │     └── Independent scaling
│   │
│   ├── Targets
│   │     ├── EC2 instances
│   │     ├── IP addresses
│   │     ├── Lambda functions
│   │     └── Containers
│   │
│   └── Nodes
│         ├── ALB nodes in each AZ
│         ├── Receive traffic
│         ├── Route requests
│         └── Managed automatically
│
├── 2. LOAD BALANCER COMPONENTS
│   │
│   ├── DNS Name
│   │     ├── Automatically generated
│   │     ├── Public or internal
│   │     └── Route 53 integration
│   │
│   ├── Scheme
│   │     ├── Internet-facing
│   │     └── Internal
│   │
│   ├── IP Address Types
│   │     ├── IPv4
│   │     ├── Dualstack
│   │     └── IPv6 support
│   │
│   ├── Availability Zones
│   │     ├── Subnet mapping
│   │     ├── One subnet per AZ
│   │     └── Redundancy
│   │
│   ├── Security Groups
│   │     ├── Control inbound traffic
│   │     ├── Control outbound traffic
│   │     └── Stateful firewall
│   │
│   ├── ENIs (Elastic Network Interfaces)
│   │     ├── Created per subnet
│   │     ├── Used by ALB nodes
│   │     └── Managed automatically
│   │
│   └── Cross-Zone Load Balancing
│         ├── Enabled by default
│         ├── Even traffic distribution
│         └── Routes across AZs
│
├── 3. LISTENERS
│   │
│   ├── Listener Protocols
│   │     ├── HTTP
│   │     └── HTTPS
│   │
│   ├── Listener Ports
│   │     ├── Common: 80
│   │     ├── Common: 443
│   │     └── Custom ports supported
│   │
│   ├── HTTPS Listener Features
│   │     ├── TLS termination
│   │     ├── SSL certificates
│   │     ├── SNI support
│   │     ├── Security policies
│   │     └── Certificate selection
│   │
│   ├── Listener Rules
│   │     ├── Priority-based evaluation
│   │     ├── Conditions
│   │     ├── Actions
│   │     └── Optional transforms
│   │
│   ├── Default Listener Rule
│   │     ├── Last rule evaluated
│   │     └── No conditions
│   │
│   └── Redirect Support
│         ├── HTTP → HTTPS
│         ├── URL redirect
│         └── Host/path redirects
│
├── 4. RULES & ROUTING
│   │
│   ├── Rule Conditions
│   │     │
│   │     ├── Host-based routing
│   │     │     ├── example.com
│   │     │     └── api.example.com
│   │     │
│   │     ├── Path-based routing
│   │     │     ├── /images/*
│   │     │     ├── /api/*
│   │     │     └── /admin/*
│   │     │
│   │     ├── HTTP Header
│   │     ├── HTTP Method
│   │     ├── Query String
│   │     ├── Source IP
│   │     └── Cookie-based logic
│   │
│   ├── Rule Actions
│   │     │
│   │     ├── Forward
│   │     │     ├── Single target group
│   │     │     └── Multiple target groups
│   │     │
│   │     ├── Redirect
│   │     │     ├── HTTP redirect
│   │     │     └── HTTPS enforcement
│   │     │
│   │     ├── Fixed Response
│   │     │     ├── Custom status code
│   │     │     └── Static response body
│   │     │
│   │     └── Authenticate
│   │           ├── Cognito authentication
│   │           └── OIDC authentication
│   │
│   ├── Weighted Target Groups
│   │     ├── Blue/Green deployments
│   │     ├── Canary deployments
│   │     └── Traffic splitting
│   │
│   ├── URL Rewrite
│   ├── Host Header Rewrite
│   └── Advanced Request Routing
│
├── 5. TARGET GROUPS
│   │
│   ├── Target Types
│   │     ├── Instance
│   │     ├── IP
│   │     ├── Lambda
│   │     └── ALB
│   │
│   ├── Target Registration
│   │     ├── Register targets
│   │     ├── Deregister targets
│   │     ├── Dynamic updates
│   │     └── Auto Scaling integration
│   │
│   ├── Routing Configuration
│   │     ├── Protocol
│   │     ├── Port
│   │     ├── Protocol version
│   │     └── Health checks
│   │
│   ├── Protocol Versions
│   │     ├── HTTP/1.1
│   │     ├── HTTP/2
│   │     └── gRPC
│   │
│   ├── Sticky Sessions
│   │     ├── Session affinity
│   │     ├── ALB-generated cookies
│   │     └── Application cookies
│   │
│   ├── Deregistration Delay
│   │     ├── Connection draining
│   │     └── Graceful shutdown
│   │
│   └── Slow Start Mode
│         ├── Gradual traffic ramp-up
│         └── Useful for warming targets
│
├── 6. HEALTH CHECKS
│   │
│   ├── Automatic Health Monitoring
│   │
│   ├── Health Check Settings
│   │     ├── Protocol
│   │     ├── Port
│   │     ├── Path
│   │     ├── Timeout
│   │     ├── Interval
│   │     └── Thresholds
│   │
│   ├── Health Status
│   │     ├── Healthy
│   │     ├── Unhealthy
│   │     ├── Initial
│   │     ├── Draining
│   │     └── Unused
│   │
│   ├── Success Codes
│   │     ├── HTTP status validation
│   │     └── Custom ranges
│   │
│   ├── Fail-open Behavior
│   │     └── Routes traffic if all unhealthy
│   │
│   └── Health Check Reasons
│         ├── Timeout
│         ├── Failed response
│         ├── Connection issues
│         └── Internal errors
│
├── 7. SECURITY
│   │
│   ├── HTTPS/TLS
│   │     ├── SSL termination
│   │     ├── End-to-end encryption
│   │     └── TLS negotiation
│   │
│   ├── AWS Certificate Manager (ACM)
│   │     ├── Managed certificates
│   │     ├── Automatic renewal
│   │     └── Multiple certs
│   │
│   ├── Security Policies
│   │     ├── TLS versions
│   │     ├── Cipher suites
│   │     └── Compliance support
│   │
│   ├── Authentication
│   │     ├── Amazon Cognito
│   │     ├── OpenID Connect (OIDC)
│   │     └── User authentication at ALB
│   │
│   ├── AWS WAF Integration
│   │     ├── Web ACLs
│   │     ├── Layer 7 filtering
│   │     ├── SQL injection protection
│   │     └── DDoS mitigation
│   │
│   ├── AWS Shield
│   │     ├── Standard protection
│   │     └── Advanced protection
│   │
│   ├── Security Groups
│   └── Access Logging
│
├── 8. NETWORKING
│   │
│   ├── VPC Integration
│   │     ├── Must exist inside VPC
│   │     ├── Uses subnets
│   │     └── Private networking
│   │
│   ├── Internet-facing ALB
│   │     ├── Public IPs
│   │     ├── Internet traffic
│   │     └── Public applications
│   │
│   ├── Internal ALB
│   │     ├── Private IPs only
│   │     ├── Internal services
│   │     └── Microservices communication
│   │
│   ├── IPv6 Support
│   ├── Connection Idle Timeout
│   ├── HTTP Keepalive
│   └── Connection Management
│
├── 9. MONITORING & LOGGING
│   │
│   ├── Amazon CloudWatch
│   │     ├── Metrics
│   │     ├── Alarms
│   │     └── Dashboards
│   │
│   ├── Key Metrics
│   │     ├── RequestCount
│   │     ├── TargetResponseTime
│   │     ├── HTTPCode_ELB_4XX
│   │     ├── HTTPCode_ELB_5XX
│   │     ├── HealthyHostCount
│   │     └── UnHealthyHostCount
│   │
│   ├── Access Logs
│   │     ├── Stored in S3
│   │     ├── Request analysis
│   │     ├── Troubleshooting
│   │     └── Auditing
│   │
│   ├── AWS CloudTrail
│   │     ├── API auditing
│   │     └── Configuration tracking
│   │
│   ├── Resource Map
│   └── Monitoring Integrations
│
├── 10. CONTAINER & SERVERLESS INTEGRATION
│   │
│   ├── Amazon ECS Integration
│   │     ├── Dynamic port mapping
│   │     ├── Service discovery
│   │     └── Container routing
│   │
│   ├── Amazon EKS Integration
│   │     ├── Kubernetes ingress
│   │     ├── ALB Ingress Controller
│   │     └── AWS Load Balancer Controller
│   │
│   ├── AWS Lambda Integration
│   │     ├── Lambda targets
│   │     ├── Event-based invocation
│   │     └── Serverless architectures
│   │
│   └── Microservices Architectures
│         ├── Path routing
│         ├── Host routing
│         └── Service isolation
│
├── 11. HIGH AVAILABILITY & SCALING
│   │
│   ├── Automatic Scaling
│   │     ├── Traffic adaptation
│   │     ├── AWS-managed scaling
│   │     └── No manual intervention
│   │
│   ├── Fault Tolerance
│   │     ├── Multi-AZ operation
│   │     ├── Health-based routing
│   │     └── Automatic recovery
│   │
│   ├── Elastic Capacity
│   ├── Cross-Zone Balancing
│   └── Distributed Architecture
│
├── 12. DEPLOYMENT STRATEGIES
│   │
│   ├── Blue/Green Deployments
│   │     ├── Weighted routing
│   │     ├── Traffic shifting
│   │     └── Safe rollback
│   │
│   ├── Canary Deployments
│   │     ├── Gradual rollout
│   │     ├── Limited exposure
│   │     └── Risk reduction
│   │
│   ├── A/B Testing
│   │     ├── User segmentation
│   │     └── Experiment routing
│   │
│   └── Zero Downtime Deployments
│
├── 13. PERFORMANCE FEATURES
│   │
│   ├── HTTP/2 Support
│   │     ├── Multiplexing
│   │     ├── Header compression
│   │     └── Improved latency
│   │
│   ├── gRPC Support
│   │     ├── End-to-end HTTP/2
│   │     └── Modern APIs
│   │
│   ├── WebSocket Support
│   │     ├── Persistent connections
│   │     └── Real-time applications
│   │
│   ├── Connection Reuse
│   ├── Request Routing Optimization
│   └── Low Latency Routing
│
├── 14. USE CASES
│   │
│   ├── Web Applications
│   ├── APIs
│   ├── Microservices
│   ├── Containers
│   ├── Kubernetes
│   ├── Serverless Backends
│   ├── Multi-Tenant Applications
│   ├── SaaS Platforms
│   ├── Internal Enterprise Apps
│   └── Hybrid Architectures
│
├── 15. INTEGRATIONS
│   │
│   ├── EC2 Auto Scaling
│   ├── ECS
│   ├── EKS
│   ├── Lambda
│   ├── Route 53
│   ├── CloudFront
│   ├── AWS WAF
│   ├── Shield
│   ├── ACM
│   ├── CloudWatch
│   ├── CloudTrail
│   ├── Cognito
│   └── Global Accelerator
│
├── 16. LIMITS & QUOTAS
│   │
│   ├── Listeners per ALB
│   ├── Rules per Listener
│   ├── Target Groups
│   ├── Targets per Target Group
│   ├── Certificates
│   ├── Request Size Limits
│   └── Header Limits
│
├── 17. BEST PRACTICES
│   │
│   ├── Use Multi-AZ
│   ├── Enable HTTPS Everywhere
│   ├── Use ACM Certificates
│   ├── Configure Health Checks Properly
│   ├── Use Path-based Routing
│   ├── Enable Access Logs
│   ├── Integrate with WAF
│   ├── Use Auto Scaling
│   ├── Monitor CloudWatch Metrics
│   ├── Use Least Privilege Security Groups
│   ├── Implement Blue/Green Deployments
│   └── Optimize Idle Timeouts
│
└── 18. TROUBLESHOOTING
    │
    ├── Unhealthy Targets
    │     ├── Security group issues
    │     ├── Failed health checks
    │     ├── Application errors
    │     └── Network ACL issues
    │
    ├── HTTP Errors
    │     ├── 4XX errors
    │     ├── 5XX errors
    │     └── Backend failures
    │
    ├── SSL/TLS Problems
    │     ├── Certificate mismatch
    │     ├── Unsupported ciphers
    │     └── TLS negotiation failures
    │
    ├── Routing Problems
    │     ├── Rule priority conflicts
    │     ├── Incorrect conditions
    │     └── Wrong target group
    │
    ├── Connection Issues
    ├── Performance Bottlenecks
    ├── Logging & Diagnostics
    └── CloudWatch Analysis
</pre>