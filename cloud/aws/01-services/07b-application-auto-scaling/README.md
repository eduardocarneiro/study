
<pre>
AWS Application Auto Scaling
│
├── 1. CORE CONCEPTS
│   │
│   ├── Purpose
│   │   ├── Automatically adjusts scalable resources
│   │   ├── Maintains performance and availability
│   │   ├── Optimizes cost efficiency
│   │   └── Works with multiple AWS services
│   │
│   ├── Service Namespace
│   │   ├── Identifies AWS service
│   │   ├── Required for scalable targets
│   │   └── Examples:
│   │       ├── ECS
│   │       ├── DynamoDB
│   │       ├── Aurora
│   │       ├── Lambda Provisioned Concurrency
│   │       ├── SageMaker
│   │       ├── Comprehend
│   │       └── AppStream 2.0
│   │
│   ├── Scalable Target
│   │   ├── Resource registered for scaling
│   │   ├── Defines minimum capacity
│   │   ├── Defines maximum capacity
│   │   ├── Resource ID
│   │   └── Scalable dimension
│   │
│   ├── Scaling Policies
│   │   ├── Rules controlling scaling actions
│   │   ├── Dynamic scaling
│   │   ├── Scheduled scaling
│   │   └── Predictive concepts (service-dependent)
│   │
│   ├── CloudWatch Integration
│   │   ├── Uses metrics
│   │   ├── Uses alarms
│   │   ├── Monitors utilization
│   │   └── Triggers scaling activities
│   │
│   ├── Scaling Activity
│   │   ├── Scale-out activity
│   │   ├── Scale-in activity
│   │   ├── Success/failure tracking
│   │   └── Event history
│   │
│   └── Desired Capacity Management
│       ├── Maintains target performance
│       ├── Responds to workload changes
│       └── Continuously adjusts capacity
│
├── 2. SUPPORTED AWS SERVICES
│   │
│   ├── Amazon ECS
│   │   ├── Desired task count
│   │   ├── ECS services
│   │   └── Service autoscaling
│   │
│   ├── DynamoDB
│   │   ├── Read capacity units
│   │   ├── Write capacity units
│   │   ├── Global secondary indexes
│   │   └── On-demand interactions
│   │
│   ├── Aurora
│   │   ├── Aurora Replicas
│   │   ├── Reader endpoints
│   │   └── Cluster scaling
│   │
│   ├── Lambda
│   │   ├── Provisioned concurrency
│   │   └── Function concurrency scaling
│   │
│   ├── SageMaker
│   │   ├── Endpoint variants
│   │   ├── Inference components
│   │   └── Real-time inference scaling
│   │
│   ├── EMR
│   │   ├── Instance groups
│   │   └── Cluster scaling
│   │
│   ├── AppStream 2.0
│   │   ├── Fleet scaling
│   │   └── Streaming capacity
│   │
│   ├── Comprehend
│   │   ├── Endpoint inference units
│   │   └── NLP workload scaling
│   │
│   ├── Keyspaces
│   │   ├── Read throughput
│   │   └── Write throughput
│   │
│   ├── MSK
│   │   ├── Broker storage scaling
│   │   └── Kafka scaling
│   │
│   ├── ElastiCache
│   │   ├── Replication groups
│   │   └── Node groups
│   │
│   ├── Neptune
│   │   ├── Read replicas
│   │   └── Database scaling
│   │
│   └── WorkSpaces
│       ├── Provisioned throughput
│       └── Workspace pools
│
├── 3. SCALABLE TARGETS
│   │
│   ├── Registering Targets
│   │   ├── Required before scaling
│   │   ├── Defines resource boundaries
│   │   └── Enables scaling policies
│   │
│   ├── Components
│   │   ├── Resource ID
│   │   ├── Service namespace
│   │   ├── Scalable dimension
│   │   ├── Min capacity
│   │   └── Max capacity
│   │
│   ├── Resource ID Formats
│   │   ├── service/cluster/service-name
│   │   ├── table/table-name
│   │   ├── cluster:cluster-name
│   │   └── function:function-name:alias
│   │
│   ├── Min Capacity
│   │   ├── Prevents scaling below threshold
│   │   ├── Ensures availability
│   │   └── Cost baseline
│   │
│   ├── Max Capacity
│   │   ├── Prevents runaway scaling
│   │   ├── Cost protection
│   │   └── Service quota awareness
│   │
│   └── Deregistration
│       ├── Removes scaling management
│       ├── Deletes scaling policies
│       └── Stops automatic scaling
│
├── 4. DYNAMIC SCALING POLICIES
│   │
│   ├── Target Tracking Scaling
│   │   ├── Most common policy
│   │   ├── Maintains target metric value
│   │   ├── Similar to thermostat
│   │   └── AWS-managed CloudWatch alarms
│   │
│   ├── Step Scaling
│   │   ├── Uses CloudWatch alarms
│   │   ├── Scales based on thresholds
│   │   ├── Multiple scaling adjustments
│   │   └── Granular scaling behavior
│   │
│   ├── Scaling Adjustments
│   │   ├── ChangeInCapacity
│   │   ├── ExactCapacity
│   │   └── PercentChangeInCapacity
│   │
│   ├── Cooldowns
│   │   ├── Scale-out cooldown
│   │   ├── Scale-in cooldown
│   │   ├── Prevents rapid fluctuations
│   │   └── Stabilizes workloads
│   │
│   ├── Metric Sources
│   │   ├── Predefined metrics
│   │   ├── Custom CloudWatch metrics
│   │   └── Service-specific metrics
│   │
│   └── High Availability
│       ├── Automatic elasticity
│       ├── Performance optimization
│       └── Traffic adaptation
│
├── 5. TARGET TRACKING SCALING
│   │
│   ├── Concepts
│   │   ├── Metric-driven scaling
│   │   ├── Keeps metric near target value
│   │   └── Simplified scaling management
│   │
│   ├── Common Metrics
│   │   ├── ECS CPU utilization
│   │   ├── ECS memory utilization
│   │   ├── DynamoDB consumed capacity
│   │   ├── ALB request count per target
│   │   └── SageMaker invocation metrics
│   │
│   ├── Behavior
│   │   ├── Aggressive scale-out
│   │   ├── Conservative scale-in
│   │   ├── Availability prioritization
│   │   └── Automatic alarm management
│   │
│   ├── Multiple Policies
│   │   ├── Scale out if any policy requires
│   │   └── Scale in only if all agree
│   │
│   ├── Custom Metrics
│   │   ├── Business KPIs
│   │   ├── Queue depth
│   │   ├── Latency
│   │   └── Transactions per second
│   │
│   └── Best Practices
│       ├── Use stable metrics
│       ├── Avoid insufficient data
│       ├── Select proportional metrics
│       └── Test scaling behavior
│
├── 6. STEP SCALING
│   │
│   ├── Concepts
│   │   ├── Threshold-based scaling
│   │   ├── Manual adjustment control
│   │   └── Alarm-driven automation
│   │
│   ├── Step Adjustments
│   │   ├── Lower bound
│   │   ├── Upper bound
│   │   ├── Scaling adjustment
│   │   └── Metric intervals
│   │
│   ├── Alarm Integration
│   │   ├── CloudWatch alarm required
│   │   ├── Alarm actions
│   │   └── Metric breach response
│   │
│   ├── Scale-Out Example
│   │   ├── CPU > 70% → +1
│   │   ├── CPU > 85% → +3
│   │   └── CPU > 95% → +5
│   │
│   ├── Scale-In Example
│   │   ├── CPU < 30% → -1
│   │   └── CPU < 15% → -2
│   │
│   └── Use Cases
│       ├── Predictable scaling steps
│       ├── Burst handling
│       └── Advanced scaling control
│
├── 7. SCHEDULED SCALING
│   │
│   ├── Concepts
│   │   ├── Time-based scaling
│   │   ├── Predictable workloads
│   │   └── Scheduled capacity changes
│   │
│   ├── Scheduling Options
│   │   ├── One-time schedules
│   │   ├── Recurring schedules
│   │   └── Cron expressions
│   │
│   ├── Time Zones
│   │   ├── UTC default
│   │   ├── Custom time zones
│   │   └── Daylight saving considerations
│   │
│   ├── Scheduled Actions
│   │   ├── Set minimum capacity
│   │   ├── Set maximum capacity
│   │   └── Set desired capacity
│   │
│   ├── Common Use Cases
│   │   ├── Business hours scaling
│   │   ├── Weekend reduction
│   │   ├── Seasonal traffic
│   │   └── Batch processing windows
│   │
│   └── Interaction with Dynamic Scaling
│       ├── Scheduled actions set boundaries
│       ├── Dynamic scaling operates within limits
│       └── Combined elasticity model
│
├── 8. CLOUDWATCH INTEGRATION
│   │
│   ├── Metrics
│   │   ├── AWS service metrics
│   │   ├── Custom application metrics
│   │   ├── Utilization metrics
│   │   └── Performance metrics
│   │
│   ├── Alarms
│   │   ├── Threshold monitoring
│   │   ├── Alarm states
│   │   ├── Scaling triggers
│   │   └── SNS integration
│   │
│   ├── Monitoring
│   │   ├── Scaling activities
│   │   ├── Capacity trends
│   │   ├── Metric visualization
│   │   └── Operational visibility
│   │
│   ├── EventBridge Integration
│   │   ├── Scaling event notifications
│   │   ├── Automation workflows
│   │   └── Operational response
│   │
│   └── Logging
│       ├── CloudTrail integration
│       ├── API auditing
│       └── Change tracking
│
├── 9. SECURITY AND IAM
│   │
│   ├── IAM Roles
│   │   ├── Service-linked roles
│   │   ├── Permissions delegation
│   │   └── AWS-managed trust
│   │
│   ├── Service-Linked Roles
│   │   ├── Automatically created
│   │   ├── Service-specific permissions
│   │   └── Required for scaling actions
│   │
│   ├── IAM Policies
│   │   ├── RegisterScalableTarget
│   │   ├── PutScalingPolicy
│   │   ├── DeleteScalingPolicy
│   │   └── DescribeScalingActivities
│   │
│   ├── Least Privilege
│   │   ├── Restrict scaling permissions
│   │   ├── Scoped resource access
│   │   └── Controlled operations
│   │
│   ├── CloudTrail
│   │   ├── API call auditing
│   │   ├── Compliance monitoring
│   │   └── Security investigations
│   │
│   └── Cross-Service Permissions
│       ├── ECS permissions
│       ├── DynamoDB permissions
│       ├── Lambda permissions
│       └── Service integrations
│
├── 10. API AND CLI OPERATIONS
│   │
│   ├── Core API Actions
│   │   ├── RegisterScalableTarget
│   │   ├── DeregisterScalableTarget
│   │   ├── PutScalingPolicy
│   │   ├── DeleteScalingPolicy
│   │   ├── DescribeScalingPolicies
│   │   └── DescribeScalingActivities
│   │
│   ├── AWS CLI
│   │   ├── application-autoscaling namespace
│   │   ├── Automation scripting
│   │   └── Infrastructure management
│   │
│   ├── SDK Integration
│   │   ├── Python (Boto3)
│   │   ├── Java
│   │   ├── Go
│   │   ├── JavaScript
│   │   └── .NET
│   │
│   ├── Infrastructure as Code
│   │   ├── CloudFormation
│   │   ├── Terraform
│   │   ├── CDK
│   │   └── Automation pipelines
│   │
│   └── Automation
│       ├── CI/CD integration
│       ├── Scaling governance
│       └── Operational consistency
│
├── 11. BEST PRACTICES
│   │
│   ├── Metric Selection
│   │   ├── Choose utilization metrics
│   │   ├── Ensure proportionality
│   │   └── Avoid noisy metrics
│   │
│   ├── Capacity Planning
│   │   ├── Define realistic limits
│   │   ├── Understand workload patterns
│   │   └── Prevent quota exhaustion
│   │
│   ├── Availability
│   │   ├── Prioritize scale-out responsiveness
│   │   ├── Conservative scale-in
│   │   └── Protect production workloads
│   │
│   ├── Cost Optimization
│   │   ├── Reduce overprovisioning
│   │   ├── Schedule off-hours reductions
│   │   └── Optimize minimum capacity
│   │
│   ├── Testing
│   │   ├── Simulate workloads
│   │   ├── Validate alarms
│   │   ├── Observe scaling activities
│   │   └── Tune cooldowns
│   │
│   └── Monitoring
│       ├── Track scaling history
│       ├── Analyze trends
│       ├── Review CloudWatch metrics
│       └── Audit scaling events
│
└── 12. TROUBLESHOOTING
    │
    ├── Scaling Not Triggered
    │   ├── Alarm misconfiguration
    │   ├── Metric issues
    │   ├── IAM permission problems
    │   └── Target not registered
    │
    ├── Scaling Delays
    │   ├── Cooldown periods
    │   ├── Metric aggregation delays
    │   └── Service stabilization
    │
    ├── Capacity Issues
    │   ├── Max capacity reached
    │   ├── Service quotas exceeded
    │   └── Insufficient backend resources
    │
    ├── CloudWatch Problems
    │   ├── Missing metrics
    │   ├── Alarm in insufficient data
    │   └── Delayed datapoints
    │
    ├── IAM Problems
    │   ├── Missing service-linked role
    │   ├── Access denied errors
    │   └── Trust relationship issues
    │
    └── Diagnostic Tools
        ├── DescribeScalingActivities
        ├── CloudWatch alarms
        ├── CloudTrail logs
        ├── EventBridge events
        └── AWS Health Dashboard
</pre>