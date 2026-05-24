
<pre>
AWS AMAZON CLOUDFRONT
│
├── 1. CORE CONCEPTS
│   │
│   ├── Content Delivery Network (CDN)
│   │   ├── Global edge network
│   │   ├── Low-latency content delivery
│   │   ├── Distributed caching
│   │   ├── High availability
│   │   └── DDoS resilience
│   │
│   ├── Edge Locations
│   │   ├── Global Points of Presence (PoPs)
│   │   ├── Cached content storage
│   │   ├── Request termination
│   │   ├── TLS offloading
│   │   └── User proximity optimization
│   │
│   ├── Regional Edge Caches
│   │   ├── Larger cache layer
│   │   ├── Between origin and edge
│   │   ├── Improves cache hit ratio
│   │   └── Reduces origin load
│   │
│   ├── Origin
│   │   ├── Source of content
│   │   ├── S3 bucket
│   │   ├── EC2 instance
│   │   ├── Elastic Load Balancer
│   │   ├── MediaPackage
│   │   ├── MediaStore
│   │   └── Custom HTTP server
│   │
│   ├── Distribution
│   │   ├── Main CloudFront configuration
│   │   ├── Defines origins
│   │   ├── Defines behaviors
│   │   ├── Security policies
│   │   ├── Cache settings
│   │   └── Domain configuration
│   │
│   ├── Cache
│   │   ├── Stores objects at edges
│   │   ├── TTL-based expiration
│   │   ├── Reduces latency
│   │   ├── Reduces origin requests
│   │   └── Improves scalability
│   │
│   ├── Viewer
│   │   ├── End user/client
│   │   ├── Browser
│   │   ├── Mobile app
│   │   ├── API consumer
│   │   └── Streaming client
│   │
│   └── Request/Response Flow
│       ├── Viewer request
│       ├── Edge cache lookup
│       ├── Cache hit
│       ├── Cache miss
│       ├── Origin fetch
│       ├── Cache population
│       └── Response delivery
│
├── 2. DISTRIBUTION TYPES
│   │
│   ├── Web Distribution
│   │   ├── Static websites
│   │   ├── Dynamic applications
│   │   ├── APIs
│   │   ├── Downloads
│   │   └── SPA applications
│   │
│   ├── Streaming Distribution
│   │   ├── Video delivery
│   │   ├── Live streaming
│   │   ├── On-demand streaming
│   │   ├── HLS
│   │   ├── MPEG-DASH
│   │   └── Smooth streaming
│   │
│   └── Protocol Support
│       ├── HTTP
│       ├── HTTPS
│       ├── HTTP/2
│       ├── HTTP/3
│       ├── WebSocket
│       ├── gRPC
│       └── QUIC
│
├── 3. ORIGINS
│   │
│   ├── Amazon S3 Origins
│   │   ├── Static website hosting
│   │   ├── Private content
│   │   ├── Origin Access Control (OAC)
│   │   ├── Origin Access Identity (OAI)
│   │   └── Bucket policy integration
│   │
│   ├── Custom Origins
│   │   ├── EC2
│   │   ├── On-premises servers
│   │   ├── External web servers
│   │   ├── ALB
│   │   ├── NLB
│   │   └── Hybrid architectures
│   │
│   ├── Media Origins
│   │   ├── AWS Elemental MediaPackage
│   │   ├── AWS Elemental MediaStore
│   │   ├── Live video workflows
│   │   └── VOD workflows
│   │
│   ├── Origin Groups
│   │   ├── Failover origins
│   │   ├── High availability
│   │   ├── Primary origin
│   │   ├── Secondary origin
│   │   └── Health-based failover
│   │
│   └── Origin Shield
│       ├── Centralized caching layer
│       ├── Reduces origin load
│       ├── Improves cache hit ratio
│       ├── Multi-CDN optimization
│       └── Regional protection
│
├── 4. CACHE BEHAVIORS
│   │
│   ├── Path Patterns
│   │   ├── URL-based routing
│   │   ├── /images/*
│   │   ├── /api/*
│   │   ├── /videos/*
│   │   └── Ordered matching
│   │
│   ├── Cache Policies
│   │   ├── TTL settings
│   │   ├── Header forwarding
│   │   ├── Cookie forwarding
│   │   ├── Query string handling
│   │   └── Cache key customization
│   │
│   ├── Origin Request Policies
│   │   ├── Forward headers
│   │   ├── Forward cookies
│   │   ├── Forward query strings
│   │   └── Control origin requests
│   │
│   ├── Response Headers Policies
│   │   ├── Security headers
│   │   ├── CORS headers
│   │   ├── Custom headers
│   │   └── Browser behavior control
│   │
│   ├── Allowed HTTP Methods
│   │   ├── GET
│   │   ├── HEAD
│   │   ├── OPTIONS
│   │   ├── PUT
│   │   ├── POST
│   │   ├── PATCH
│   │   └── DELETE
│   │
│   └── Compression
│       ├── Gzip
│       ├── Brotli
│       ├── Automatic compression
│       └── Reduced bandwidth usage
│
├── 5. CACHING
│   │
│   ├── Cache Keys
│   │   ├── URL path
│   │   ├── Query strings
│   │   ├── Headers
│   │   ├── Cookies
│   │   └── Device-specific caching
│   │
│   ├── Time To Live (TTL)
│   │   ├── Minimum TTL
│   │   ├── Default TTL
│   │   ├── Maximum TTL
│   │   └── Expiration management
│   │
│   ├── Cache-Control Headers
│   │   ├── max-age
│   │   ├── s-maxage
│   │   ├── no-cache
│   │   ├── no-store
│   │   └── must-revalidate
│   │
│   ├── Cache Invalidation
│   │   ├── Remove cached objects
│   │   ├── Wildcard invalidations
│   │   ├── Versioned file strategy
│   │   └── Deployment updates
│   │
│   ├── Cache Hit Ratio
│   │   ├── Performance metric
│   │   ├── Origin offloading
│   │   ├── Optimization target
│   │   └── Cost efficiency
│   │
│   └── Stale Content Handling
│       ├── stale-while-revalidate
│       ├── stale-if-error
│       ├── Resiliency improvements
│       └── Availability optimization
│
├── 6. SECURITY
│   │
│   ├── HTTPS/TLS
│   │   ├── SSL/TLS certificates
│   │   ├── AWS Certificate Manager (ACM)
│   │   ├── Custom certificates
│   │   ├── TLS versions
│   │   └── HTTPS redirection
│   │
│   ├── AWS Shield Integration
│   │   ├── DDoS protection
│   │   ├── Standard protection
│   │   ├── Shield Advanced
│   │   └── Edge protection
│   │
│   ├── AWS WAF Integration
│   │   ├── Web ACLs
│   │   ├── Rate limiting
│   │   ├── Bot protection
│   │   ├── IP filtering
│   │   └── OWASP protections
│   │
│   ├── Signed URLs
│   │   ├── Restricted access
│   │   ├── Time-limited access
│   │   ├── Secure downloads
│   │   └── Premium content delivery
│   │
│   ├── Signed Cookies
│   │   ├── Multiple file access
│   │   ├── Session-based authorization
│   │   ├── Streaming authorization
│   │   └── Protected applications
│   │
│   ├── Geo Restriction
│   │   ├── Country blocking
│   │   ├── Country allow lists
│   │   ├── Licensing restrictions
│   │   └── Regional compliance
│   │
│   ├── Field-Level Encryption
│   │   ├── Sensitive data protection
│   │   ├── Encryption at edge
│   │   ├── Secure data transit
│   │   └── Compliance support
│   │
│   └── Origin Security
│       ├── Private origins
│       ├── OAC/OAI protection
│       ├── Security groups
│       ├── Custom headers
│       └── Mutual TLS
│
├── 7. EDGE COMPUTING
│   │
│   ├── CloudFront Functions
│   │   ├── Lightweight edge code
│   │   ├── Viewer request processing
│   │   ├── Viewer response processing
│   │   ├── Header manipulation
│   │   ├── URL rewrites
│   │   └── Authentication logic
│   │
│   ├── Lambda@Edge
│   │   ├── Serverless edge execution
│   │   ├── Viewer request events
│   │   ├── Viewer response events
│   │   ├── Origin request events
│   │   ├── Origin response events
│   │   └── Advanced customization
│   │
│   ├── Edge Use Cases
│   │   ├── Authentication
│   │   ├── Redirects
│   │   ├── A/B testing
│   │   ├── Dynamic personalization
│   │   ├── SEO optimization
│   │   └── Security filtering
│   │
│   └── Event Lifecycle
│       ├── Viewer request
│       ├── Origin request
│       ├── Origin response
│       └── Viewer response
│
├── 8. DOMAIN & DNS INTEGRATION
│   │
│   ├── Alternate Domain Names (CNAMEs)
│   │   ├── Custom domains
│   │   ├── www.example.com
│   │   ├── cdn.example.com
│   │   └── Multi-domain support
│   │
│   ├── Route 53 Integration
│   │   ├── Alias records
│   │   ├── DNS routing
│   │   ├── Apex domain support
│   │   └── Health-aware architectures
│   │
│   ├── SSL Certificate Validation
│   │   ├── ACM certificates
│   │   ├── DNS validation
│   │   ├── HTTPS enablement
│   │   └── Certificate management
│   │
│   └── Multi-Domain Architectures
│       ├── Shared distributions
│       ├── Multi-tenant platforms
│       ├── SaaS applications
│       └── Domain segregation
│
├── 9. STREAMING & MEDIA DELIVERY
│   │
│   ├── Live Streaming
│   │   ├── Real-time video delivery
│   │   ├── MediaPackage integration
│   │   ├── Low latency streaming
│   │   └── Global distribution
│   │
│   ├── Video On Demand (VOD)
│   │   ├── Cached media delivery
│   │   ├── Large file optimization
│   │   ├── Adaptive bitrate streaming
│   │   └── Scalable playback
│   │
│   ├── Supported Formats
│   │   ├── HLS
│   │   ├── MPEG-DASH
│   │   ├── CMAF
│   │   └── Smooth Streaming
│   │
│   └── Media Security
│       ├── DRM integration
│       ├── Signed URLs
│       ├── Geo restrictions
│       └── Secure playback
│
├── 10. PERFORMANCE OPTIMIZATION
│   │
│   ├── Latency Reduction
│   │   ├── Edge caching
│   │   ├── TCP optimization
│   │   ├── Persistent connections
│   │   └── HTTP/3 support
│   │
│   ├── Origin Optimization
│   │   ├── Connection reuse
│   │   ├── Keep-alive
│   │   ├── Origin Shield
│   │   └── Reduced backend load
│   │
│   ├── Dynamic Content Acceleration
│   │   ├── API acceleration
│   │   ├── Dynamic site optimization
│   │   ├── Low-latency routing
│   │   └── Global performance
│   │
│   ├── Large Object Delivery
│   │   ├── Range GET requests
│   │   ├── Parallel downloads
│   │   ├── Resume downloads
│   │   └── Efficient file transfer
│   │
│   └── Performance Metrics
│       ├── Cache hit ratio
│       ├── Latency
│       ├── Error rates
│       ├── Origin response time
│       └── Throughput
│
├── 11. LOGGING & MONITORING
│   │
│   ├── Access Logs
│   │   ├── Viewer request logging
│   │   ├── S3 log storage
│   │   ├── Request analytics
│   │   └── Troubleshooting
│   │
│   ├── Real-Time Logs
│   │   ├── Near real-time visibility
│   │   ├── Kinesis integration
│   │   ├── Streaming analytics
│   │   └── Security analysis
│   │
│   ├── CloudWatch Metrics
│   │   ├── Requests
│   │   ├── Bytes transferred
│   │   ├── Error rates
│   │   ├── Cache hit ratio
│   │   └── Monitoring dashboards
│   │
│   ├── CloudWatch Alarms
│   │   ├── Error thresholds
│   │   ├── Traffic anomalies
│   │   ├── Availability monitoring
│   │   └── Automated notifications
│   │
│   └── AWS X-Ray Integration
│       ├── Distributed tracing
│       ├── Request visibility
│       ├── Performance debugging
│       └── Application insights
│
├── 12. COST MODEL
│   │
│   ├── Data Transfer Out
│   │   ├── Regional pricing
│   │   ├── Internet delivery costs
│   │   ├── Edge location pricing
│   │   └── Volume discounts
│   │
│   ├── HTTP/HTTPS Requests
│   │   ├── Request pricing
│   │   ├── Regional differences
│   │   └── API request costs
│   │
│   ├── Invalidation Requests
│   │   ├── Free tier invalidations
│   │   ├── Additional invalidation cost
│   │   └── Cache management tradeoffs
│   │
│   ├── Edge Compute Pricing
│   │   ├── CloudFront Functions cost
│   │   ├── Lambda@Edge cost
│   │   ├── Execution duration
│   │   └── Invocation pricing
│   │
│   └── Cost Optimization
│       ├── High cache hit ratio
│       ├── Compression
│       ├── Optimized TTLs
│       ├── Origin Shield usage
│       └── Efficient invalidations
│
├── 13. HIGH AVAILABILITY & RESILIENCY
│   │
│   ├── Global Infrastructure
│   │   ├── Worldwide edge network
│   │   ├── Redundant PoPs
│   │   ├── Automatic failover
│   │   └── Traffic resilience
│   │
│   ├── Origin Failover
│   │   ├── Multi-origin redundancy
│   │   ├── Health-based failover
│   │   ├── Active-passive setup
│   │   └── Fault tolerance
│   │
│   ├── DDoS Resilience
│   │   ├── AWS Shield
│   │   ├── Edge absorption
│   │   ├── Traffic filtering
│   │   └── Global protection
│   │
│   └── Disaster Recovery
│       ├── Multi-region origins
│       ├── Cached content availability
│       ├── DNS failover integration
│       └── Business continuity
│
├── 14. INTEGRATIONS
│   │
│   ├── Amazon S3
│   ├── Route 53
│   ├── AWS WAF
│   ├── AWS Shield
│   ├── ACM
│   ├── Lambda@Edge
│   ├── CloudWatch
│   ├── Kinesis
│   ├── API Gateway
│   ├── Elastic Load Balancing
│   ├── Media Services
│   ├── Cognito
│   ├── ECS/EKS
│   └── AWS Global Accelerator
│
├── 15. COMMON ARCHITECTURE PATTERNS
│   │
│   ├── Static Website Hosting
│   │   ├── S3 + CloudFront
│   │   ├── HTTPS everywhere
│   │   ├── Global caching
│   │   └── Low-cost hosting
│   │
│   ├── Dynamic Web Application
│   │   ├── CloudFront + ALB
│   │   ├── EC2/ECS/EKS backend
│   │   ├── API acceleration
│   │   └── WAF protection
│   │
│   ├── Secure Content Delivery
│   │   ├── Signed URLs
│   │   ├── Private S3 origin
│   │   ├── DRM workflows
│   │   └── Geo restrictions
│   │
│   ├── Multi-Region Application
│   │   ├── Multiple origins
│   │   ├── Failover groups
│   │   ├── Global resilience
│   │   └── Route 53 integration
│   │
│   ├── API Delivery
│   │   ├── CloudFront + API Gateway
│   │   ├── JWT validation
│   │   ├── Edge authentication
│   │   └── DDoS protection
│   │
│   └── Video Streaming Platform
│       ├── MediaPackage origin
│       ├── Edge caching
│       ├── Adaptive bitrate streaming
│       └── Global media delivery
│
└── 16. BEST PRACTICES
    │
    ├── Use HTTPS Everywhere
    ├── Protect Origins with OAC/OAI
    ├── Optimize Cache Policies
    ├── Use Versioned Static Assets
    ├── Minimize Invalidations
    ├── Enable Compression
    ├── Use WAF + Shield
    ├── Monitor Cache Hit Ratio
    ├── Use Origin Shield for Scale
    ├── Configure Proper TTLs
    ├── Use Signed URLs for Private Content
    ├── Restrict Geographic Access When Needed
    ├── Use CloudFront Functions for Lightweight Logic
    ├── Use Lambda@Edge for Advanced Processing
    ├── Centralize Logging & Monitoring
    ├── Design Multi-Origin Failover
    ├── Optimize Dynamic Content Delivery
    └── Regularly Review Cost & Performance Metrics
</pre>