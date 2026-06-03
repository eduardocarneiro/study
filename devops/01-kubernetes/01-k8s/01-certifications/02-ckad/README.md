
<pre>
# ☸️ CKAD v1.35 Exam Curriculum Mental Map

```text
CKAD_Curriculum_v1.35
├── 1. Application Design and Build [20%]
│   ├── DB-01: Define, build and modify container images
│   │   ├── Dockerfile instructions (FROM, RUN, COPY, ENV, EXPOSE)
│   │   ├── Multi-stage builds for optimizing image size
│   │   ├── Inspecting, tagging, and modifying existing images
│   │   └── Pushing images to local or remote registries
│   ├── DB-02: Choose and use the right workload resource
│   │   ├── Deployments (creation, scaling, and state management)
│   │   ├── DaemonSets (ensuring node-level background pods)
│   │   ├── CronJobs & Jobs (completions, parallelism, activeDeadlineSeconds)
│   │   ├── StatefulSets (unique network/storage identity basics)
│   │   └── ReplicaSets (underlying scaling mechanisms)
│   ├── DB-03: Understand multi-container Pod design patterns
│   │   ├── Sidecar containers (logging, proxies, data synchronization)
│   │   ├── Init containers (sequential execution, single vs. multiple init)
│   │   └── Ambassador/Adapter patterns (networking and data transformation)
│   └── DB-04: Utilize persistent and ephemeral volumes
│       ├── EmptyDir (ephemeral pod-lifetime storage)
│       ├── PersistentVolumes (PV) and PersistentVolumeClaims (PVC)
│       ├── StorageClasses (dynamic volume provisioning)
│       └── Volume mounts and subPaths inside container file systems
│
├── 2. Application Deployment [20%]
│   ├── AD-01: Implement common deployment strategies
│   │   ├── Blue/Green deployments (traffic switching via service selectors)
│   │   └── Canary deployments (gradual routing to a subset of pods)
│   ├── AD-02: Understand Deployments and rolling updates
│   │   ├── Rolling updates configuration (maxSurge, maxUnavailable)
│   │   ├── Managing deployment history (rollout history, undo, pause, resume)
│   │   └── Recreate deployment strategy
│   ├── AD-03: Use the Helm package manager to deploy existing packages
│   │   ├── Helm CLI basics (helm install, upgrade, rollback, uninstall, list)
│   │   └── Overriding default values using --set or values.yaml files
│   └── AD-04: Kustomize
│       ├── Creating kustomization.yaml files
│       ├── Defining bases and overlays for development/production
│       └── Using Resource generators (configMapGenerator, secretGenerator)
│
├── 3. Application Observability and Maintenance [15%]
│   ├── OM-01: Understand API deprecations
│   │   ├── Identifying deprecated APIs in manifest files
│   │   └── Migrating manifests to updated apiVersions (e.g., extensions/v1beta1 → apps/v1)
│   ├── OM-02: Implement probes and health checks
│   │   ├── LivenessProbes (restarting unhealthy containers)
│   │   ├── ReadinessProbes (controlling traffic routing to pods)
│   │   ├── StartupProbes (protecting slow-starting legacy apps)
│   │   └── Probe mechanisms (exec commands, httpGet requests, tcpSocket checks)
│   ├── OM-03: Use built-in CLI tools to monitor Kubernetes applications
│   │   ├── Resource usage monitoring via `kubectl top` (pods, nodes)
│   │   ├── Event stream auditing via `kubectl get events` or `kubectl describe`
│   │   └── Advanced formatting with `kubectl get` (-o wide, custom-columns, jsonpath)
│   ├── OM-04: Utilize container logs
│   │   ├── Stream-fetching via `kubectl logs` (-f for streaming, -p for previous container)
│   │   └── Multi-container logging using the `-c` container flag
│   └── OM-05: Debugging in Kubernetes
│       ├── Troubleshooting application states (CrashLoopBackOff, ImagePullBackOff)
│       ├── Remote shell execution using `kubectl exec -it`
│       ├── Temporary cluster investigations using `kubectl debug` (ephemeral containers)
│       └── Node management interactions (`kubectl cordon`, `kubectl drain`)
│
├── 4. Application Environment, Configuration and Security [25%]
│   ├── CS-01: Discover and use resources that extend Kubernetes
│   │   ├── Custom Resource Definitions (CRDs) concept and utility
│   │   └── Operators pattern (automating human operational knowledge)
│   ├── CS-02: Understand authentication, authorization and admission control
│   │   ├── Role-Based Access Control (RBAC): Roles vs. ClusterRoles
│   │   ├── Attaching bindings: RoleBindings vs. ClusterRoleBindings
│   │   ├── Validating access permissions using `kubectl auth can-i`
│   │   └── Admission Controllers (Mutating and Validating webhooks overview)
│   ├── CS-03: Understand requests, limits, quotas
│   │   ├── Setting container-level resource requests and limits (CPU, Memory)
│   │   ├── Enforcing namespace bounds via LimitRanges
│   │   ├── Defining structural namespace ceilings via ResourceQuotas
│   │   └── Troubleshooting OOMKilled (Out Of Memory) and CPU throttling events
│   ├── CS-04: Understand ConfigMaps
│   │   ├── Creating ConfigMaps from literals, files, or directories
│   │   └── Consuming ConfigMaps as environment variables or mounted volumes
│   ├── CS-05: Create and consume Secrets
│   │   ├── Creating generic, docker-registry, and TLS secrets
│   │   ├── Mounting Secrets securely into container filesystems
│   │   └── Decoding secret strings manually (base64 --decode)
│   ├── CS-06: Understand ServiceAccounts
│   │   ├── Creating and assigning ServiceAccounts to specific Pods
│   │   └── Managing opt-in automated API token mounting (automountServiceAccountToken)
│   └── CS-07: Understand Application Security
│       ├── Implementing container-level `securityContext` definitions
│       ├── Modifying Linux kernel capabilities (`add`/`drop`)
│       └── Configuring safe identities (`runAsUser`, `runAsGroup`, `allowPrivilegeEscalation`)
│
└── 5. Services and Networking [20%]
    ├── SN-01: Demonstrate basic understanding of NetworkPolicies
    │   ├── Creating isolation rules via ingress (incoming) and egress (outgoing) parameters
    │   └── Utilizing selectors (podSelector, namespaceSelector, ipBlock)
    ├── SN-02: Provide and troubleshoot access to applications via services
    │   ├── Defining core Service types (ClusterIP, NodePort, LoadBalancer, ExternalName)
    │   ├── Mapping application entrypoints using `kubectl expose`
    │   ├── Resolving CoreDNS service names internally within namespaces
    │   └── Debugging mismatched endpoints (`kubectl get endpoints`)
    └── SN-03: Use Ingress rules to expose applications
        ├── Constructing path-based and host-based routing rules
        ├── Securing endpoints using TLS certificates termination
        └── Basic validation of underlying Ingress Controller routes
</pre>