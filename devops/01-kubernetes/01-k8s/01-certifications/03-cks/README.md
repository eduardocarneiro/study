
<pre>
CKS_Exam_Curriculum_v1.34
├── 01_Cluster_Setup [10%]
│   ├── Use Network security policies to restrict cluster level access
│   ├── Use CIS benchmark to review the security configuration of Kubernetes components
│   │   ├── etcd
│   │   ├── kubelet
│   │   ├── kubedns
│   │   └── kubeapi
│   ├── Properly set up Ingress objects with TLS
│   ├── Protect node metadata and endpoints
│   └── Verify platform binaries before deploying
│
├── 02_Cluster_Hardening [15%]
│   ├── Use Role Based Access Controls (RBAC) to minimize exposure
│   ├── Exercise caution in using service accounts
│   │   ├── Disable defaults (automountServiceAccountToken: false)
│   │   └── Minimize permissions on newly created ones
│   ├── Restrict access to Kubernetes API
│   └── Upgrade Kubernetes to avoid vulnerabilities
│
├── 03_System_Hardening [15%]
│   ├── Minimize host OS footprint (reduce attack surface)
│   ├── Using least-privilege identity and access management
│   ├── Minimize external access to the network
│   ├── Appropriately use kernel hardening tools
│   │   ├── AppArmor
│   │   └── seccomp
│   └── Ensure immutability of containers at runtime
│
├── 04_Minimize_Microservice_Vulnerabilities [20%]
│   ├── Use appropriate Pod Security Standards (PSS) & Pod Security Admission (PSA)
│   ├── Manage Kubernetes Secrets safely
│   ├── Understand and implement isolation techniques
│   │   ├── Multi-tenancy
│   │   └── Sandboxed containers (e.g., gVisor, Kata Containers, RuntimeClass)
│   └── Implement Pod-to-Pod encryption
│       ├── Cilium
│       └── Istio
│
├── 05_Supply_Chain_Security [20%]
│   ├── Minimize base image footprint
│   ├── Understand your supply chain
│   │   ├── Software Bill of Materials (SBOM)
│   │   ├── CI/CD pipelines
│   │   └── Artifact repositories
│   ├── Secure your supply chain
│   │   ├── Permitted registries
│   │   └── Sign and validate artifacts (e.g., Cosign)
│   └── Perform static analysis of user workloads and container images
│       ├── Kubesec
│       └── KubeLinter
│
└── 06_Monitoring_Logging_and_Runtime_Security [20%]
    ├── Perform behavioral analytics to detect malicious activities
    ├── Detect threats within infrastructure, apps, networks, data, users, and workloads
    ├── Investigate and identify phases of attack and bad actors within the environment
    └── Use Kubernetes audit logs to monitor access
</pre>