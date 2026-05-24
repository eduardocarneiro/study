
<pre>
AWS Gateway Load Balancer (GWLB)
│
├── 1. CORE CONCEPTS
│   │
│   ├── Layer 3 Load Balancer
│   │     ├── Operates at OSI Layer 3 (Network Layer)
│   │     ├── Handles IP packets
│   │     ├── Transparent traffic inspection
│   │     └── Supports all IP-based traffic
│   │
│   ├── Virtual Appliance Load Balancing
│   │     ├── Firewalls
│   │     ├── IDS/IPS
│   │     ├── Deep Packet Inspection
│   │     ├── Traffic Monitoring
│   │     └── Security Appliances
│   │
│   ├── Gateway + Load Balancer Combination
│   │     ├── Single entry point
│   │     ├── Traffic distribution
│   │     ├── Appliance scaling
│   │     └── Transparent routing
│   │
│   ├── GENEVE Protocol
│   │     ├── Port 6081
│   │     ├── Encapsulation protocol
│   │     ├── Carries original packets
│   │     └── Appliance communication
│   │
│   ├── Flow Stickiness
│   │     ├── 5-tuple stickiness (default)
│   │     ├── 3-tuple stickiness
│   │     ├── 2-tuple stickiness
│   │     └── Session consistency
│   │
│   └── Appliance Transparency
│         ├── Applications unaware of inspection
│         ├── No app changes required
│         ├── Inline traffic inspection
│         └── Centralized security architecture
│
├── 2. ARCHITECTURE COMPONENTS
│   │
│   ├── Gateway Load Balancer
│   │     ├── Traffic distribution engine
│   │     ├── Health monitoring
│   │     ├── Appliance scaling integration
│   │     └── High availability
│   │
│   ├── Target Groups
│   │     ├── EC2 appliance instances
│   │     ├── IP targets
│   │     ├── Health checks
│   │     └── Registered appliances
│   │
│   ├── GWLB Endpoints (GWLBE)
│   │     ├── Powered by PrivateLink
│   │     ├── Cross-VPC connectivity
│   │     ├── Private traffic routing
│   │     └── Service consumption model
│   │
│   ├── Service Provider VPC
│   │     ├── Hosts appliances
│   │     ├── Contains GWLB
│   │     ├── Security inspection layer
│   │     └── Shared services architecture
│   │
│   ├── Service Consumer VPC
│   │     ├── Application workloads
│   │     ├── Uses GWLB endpoints
│   │     ├── Routes traffic to inspection
│   │     └── Multiple VPC support
│   │
│   └── Route Tables
│         ├── Traffic steering
│         ├── Inspection routing
│         ├── East-west traffic control
│         └── North-south traffic control
│
├── 3. TRAFFIC FLOW
│   │
│   ├── Inbound Inspection
│   │     ├── Internet → Appliance → Application
│   │     ├── Firewall inspection
│   │     ├── Threat detection
│   │     └── Packet filtering
│   │
│   ├── Outbound Inspection
│   │     ├── Application → Appliance → Internet
│   │     ├── Egress filtering
│   │     ├── Data inspection
│   │     └── Compliance enforcement
│   │
│   ├── East-West Inspection
│   │     ├── VPC-to-VPC inspection
│   │     ├── Internal segmentation
│   │     ├── Lateral movement control
│   │     └── Multi-tier validation
│   │
│   ├── Traffic Encapsulation
│   │     ├── Original packet preserved
│   │     ├── GENEVE header added
│   │     ├── Appliance processing
│   │     └── Decapsulation on return
│   │
│   └── Symmetric Flows
│         ├── Same appliance handles flow
│         ├── Stateful inspection support
│         ├── Session persistence
│         └── Connection tracking
│
├── 4. LISTENERS
│   │
│   ├── Layer 3 Listener
│   │     ├── Listens to all IP traffic
│   │     ├── All ports supported
│   │     ├── No protocol-specific rules
│   │     └── Transparent forwarding
│   │
│   ├── Default Listener
│   │     ├── One listener per GWLB
│   │     ├── Forwards to target group
│   │     ├── No advanced routing
│   │     └── Simple architecture
│   │
│   └── Listener Actions
│         ├── Forward traffic
│         ├── Route to appliance group
│         ├── Maintain flow affinity
│         └── Preserve sessions
│
├── 5. TARGET GROUPS
│   │
│   ├── Supported Target Types
│   │     ├── EC2 instances
│   │     └── IP addresses
│   │
│   ├── Health Checks
│   │     ├── Appliance health monitoring
│   │     ├── TCP/HTTP/HTTPS checks
│   │     ├── Automatic failover
│   │     └── Unhealthy target removal
│   │
│   ├── Appliance Registration
│   │     ├── Manual registration
│   │     ├── Auto Scaling integration
│   │     ├── Dynamic scaling
│   │     └── Fleet management
│   │
│   ├── Flow Stickiness Modes
│   │     ├── 5-tuple
│   │     │     ├── Source IP
│   │     │     ├── Destination IP
│   │     │     ├── Source port
│   │     │     ├── Destination port
│   │     │     └── Protocol
│   │     │
│   │     ├── 3-tuple
│   │     │     ├── Source IP
│   │     │     ├── Destination IP
│   │     │     └── Protocol
│   │     │
│   │     └── 2-tuple
│   │           ├── Source IP
│   │           └── Destination IP
│   │
│   └── Target Failover
│         ├── Health-based rerouting
│         ├── Appliance redundancy
│         ├── Cross-AZ recovery
│         └── High availability
│
├── 6. GWLB ENDPOINTS (GWLBE)
│   │
│   ├── PrivateLink Integration
│   │     ├── Private connectivity
│   │     ├── No public internet
│   │     ├── Secure service consumption
│   │     └── VPC endpoint model
│   │
│   ├── Endpoint Deployment
│   │     ├── One per subnet/AZ
│   │     ├── Consumer VPC deployment
│   │     ├── Route table integration
│   │     └── Transparent gateway
│   │
│   ├── Cross-Account Access
│   │     ├── Shared security services
│   │     ├── Centralized inspection
│   │     ├── Multi-account architecture
│   │     └── AWS Organizations integration
│   │
│   ├── Endpoint Routing
│   │     ├── Route table next hop
│   │     ├── Appliance service insertion
│   │     ├── Traffic steering
│   │     └── Inspection enforcement
│   │
│   └── Multi-VPC Security
│         ├── Shared inspection layer
│         ├── Central firewall model
│         ├── Hub-and-spoke design
│         └── Transit architectures
│
├── 7. HIGH AVAILABILITY & SCALING
│   │
│   ├── Multi-AZ Deployment
│   │     ├── Availability Zone redundancy
│   │     ├── Fault tolerance
│   │     ├── Appliance distribution
│   │     └── Resilient inspection
│   │
│   ├── Elastic Scaling
│   │     ├── Automatic scaling
│   │     ├── Traffic-based growth
│   │     ├── Dynamic capacity
│   │     └── Appliance fleet expansion
│   │
│   ├── Auto Scaling Integration
│   │     ├── EC2 Auto Scaling groups
│   │     ├── Appliance automation
│   │     ├── Capacity management
│   │     └── Self-healing infrastructure
│   │
│   ├── Cross-Zone Load Balancing
│   │     ├── Optional feature
│   │     ├── Inter-AZ distribution
│   │     ├── Better balancing
│   │     └── Higher resilience
│   │
│   └── Failure Recovery
│         ├── Automatic rerouting
│         ├── Health-based recovery
│         ├── Appliance replacement
│         └── Minimal downtime
│
├── 8. NETWORKING CHARACTERISTICS
│   │
│   ├── IP Address Types
│   │     ├── IPv4
│   │     └── Dualstack (IPv4 + IPv6)
│   │
│   ├── MTU Support
│   │     ├── Supports up to 8500 bytes
│   │     ├── Jumbo frames
│   │     ├── GENEVE overhead
│   │     └── Appliance MTU considerations
│   │
│   ├── Idle Timeouts
│   │     ├── TCP default: 350 seconds
│   │     ├── TCP configurable
│   │     ├── UDP default: 120 seconds
│   │     └── Flow expiration
│   │
│   ├── Asymmetric Routing
│   │     ├── Limited support
│   │     ├── Not recommended
│   │     ├── Stateful inspection impact
│   │     └── Performance implications
│   │
│   └── Network ACL Considerations
│         ├── Endpoint subnet rules
│         ├── Inspection path validation
│         ├── Traffic allowance
│         └── Cross-subnet routing
│
├── 9. SECURITY USE CASES
│   │
│   ├── Centralized Firewall
│   │     ├── Shared firewall VPC
│   │     ├── Multi-account protection
│   │     ├── Central policy management
│   │     └── Consistent inspection
│   │
│   ├── Intrusion Detection & Prevention
│   │     ├── IDS deployment
│   │     ├── IPS deployment
│   │     ├── Threat analysis
│   │     └── Attack mitigation
│   │
│   ├── Deep Packet Inspection
│   │     ├── Traffic analysis
│   │     ├── Payload inspection
│   │     ├── Application visibility
│   │     └── Compliance monitoring
│   │
│   ├── Network Segmentation
│   │     ├── East-west control
│   │     ├── Micro-segmentation
│   │     ├── Security zoning
│   │     └── Traffic isolation
│   │
│   └── Hybrid Connectivity Inspection
│         ├── Direct Connect inspection
│         ├── VPN inspection
│         ├── On-premises traffic control
│         └── Hybrid security enforcement
│
├── 10. INTEGRATIONS
│   │
│   ├── AWS Marketplace
│   │     ├── Third-party appliances
│   │     ├── Security vendors
│   │     ├── Managed solutions
│   │     └── Partner integrations
│   │
│   ├── EC2 Auto Scaling
│   │     ├── Appliance scaling
│   │     ├── Elastic capacity
│   │     ├── Automated recovery
│   │     └── Fleet management
│   │
│   ├── AWS Transit Gateway
│   │     ├── Centralized inspection
│   │     ├── Multi-VPC routing
│   │     ├── Hub-and-spoke networking
│   │     └── Enterprise architectures
│   │
│   ├── AWS PrivateLink
│   │     ├── GWLB endpoints
│   │     ├── Cross-VPC services
│   │     ├── Secure connectivity
│   │     └── Private service exposure
│   │
│   ├── CloudWatch
│   │     ├── Metrics
│   │     ├── Monitoring
│   │     ├── Alarms
│   │     └── Operational visibility
│   │
│   └── Infrastructure as Code
│         ├── CloudFormation
│         ├── Terraform
│         ├── CDK
│         └── Automated deployment
│
├── 11. MONITORING & OPERATIONS
│   │
│   ├── CloudWatch Metrics
│   │     ├── Healthy hosts
│   │     ├── Traffic volume
│   │     ├── Active flows
│   │     └── Error monitoring
│   │
│   ├── Access & Flow Logs
│   │     ├── Traffic visibility
│   │     ├── Troubleshooting
│   │     ├── Security analysis
│   │     └── Audit requirements
│   │
│   ├── Health Monitoring
│   │     ├── Appliance availability
│   │     ├── Failure detection
│   │     ├── Recovery tracking
│   │     └── Fleet health status
│   │
│   └── Operational Management
│         ├── Appliance lifecycle
│         ├── Scaling operations
│         ├── Configuration updates
│         └── Maintenance automation
│
├── 12. LIMITATIONS & CONSIDERATIONS
│   │
│   ├── Appliance Responsibility
│   │     ├── AWS manages load balancing
│   │     ├── Customer manages appliances
│   │     ├── Vendor compatibility required
│   │     └── Security responsibility shared
│   │
│   ├── GENEVE Requirement
│   │     ├── Appliances must support GENEVE
│   │     ├── Port 6081 required
│   │     ├── Encapsulation awareness
│   │     └── Vendor integration needed
│   │
│   ├── Stateful Inspection Challenges
│   │     ├── Requires symmetric routing
│   │     ├── Session consistency needed
│   │     ├── Flow affinity important
│   │     └── Asymmetric routing risks
│   │
│   ├── MTU Constraints
│   │     ├── Encapsulation overhead
│   │     ├── Jumbo frame planning
│   │     ├── Fragmentation unsupported
│   │     └── PMTUD limitations
│   │
│   └── Cost Considerations
│         ├── GWLB pricing
│         ├── Endpoint pricing
│         ├── Appliance licensing
│         └── Cross-AZ traffic charges
│
├── 13. BEST PRACTICES
│   │
│   ├── Multi-AZ Architecture
│   │     ├── Deploy appliances in all AZs
│   │     ├── Endpoint redundancy
│   │     ├── HA design
│   │     └── Fault isolation
│   │
│   ├── Centralized Security VPC
│   │     ├── Shared inspection services
│   │     ├── Simplified management
│   │     ├── Consistent policy enforcement
│   │     └── Enterprise scalability
│   │
│   ├── Auto Scaling Appliances
│   │     ├── Dynamic fleet sizing
│   │     ├── Avoid bottlenecks
│   │     ├── Elastic inspection
│   │     └── Capacity optimization
│   │
│   ├── Route Table Design
│   │     ├── Explicit inspection paths
│   │     ├── Avoid asymmetric routing
│   │     ├── Validate failover routes
│   │     └── Separate inspection subnets
│   │
│   ├── Monitor Appliance Health
│   │     ├── CloudWatch alarms
│   │     ├── Health check validation
│   │     ├── Capacity monitoring
│   │     └── Traffic anomaly detection
│   │
│   └── Validate MTU Settings
│         ├── Account for GENEVE overhead
│         ├── End-to-end MTU consistency
│         ├── Avoid packet drops
│         └── Test jumbo frames
│
└── 14. COMPARISON WITH OTHER ELB TYPES
    │
    ├── GWLB vs ALB
    │     ├── GWLB → Layer 3
    │     ├── ALB → Layer 7
    │     ├── GWLB → Security appliances
    │     └── ALB → HTTP/HTTPS apps
    │
    ├── GWLB vs NLB
    │     ├── GWLB → Traffic inspection
    │     ├── NLB → Fast TCP/UDP balancing
    │     ├── GWLB → GENEVE encapsulation
    │     └── NLB → Direct forwarding
    │
    ├── GWLB vs AWS Network Firewall
    │     ├── GWLB → Framework/platform
    │     ├── Network Firewall → Managed firewall service
    │     ├── GWLB → Bring your own appliance
    │     └── Network Firewall → AWS-managed inspection
    │
    └── GWLB vs Transit Gateway
          ├── GWLB → Security inspection
          ├── TGW → Network connectivity
          ├── GWLB → Appliance insertion
          └── TGW → Routing hub
</pre>