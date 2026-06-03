
<pre>
CKA-Exam-v1.35-Mental-Map
├── 🛠️ 01-Troubleshooting [30%]
│   ├── 📦 Application-Failures
│   │   ├── Pod-Logs-and-Events
│   │   ├── Container-Exit-Codes
│   │   └── Init-Containers-Troubleshooting
│   ├── 🧠 Control-Plane-Failures
│   │   ├── Kube-Apiserver
│   │   ├── Etcd-Cluster-Health
│   │   ├── Kube-Scheduler
│   │   └── Kube-Controller-Manager
│   ├── 💻 Node-and-Worker-Failures
│   │   ├── Kubelet-Systemd-Status
│   │   ├── Container-Runtime-CRI
│   │   └── Resource-Pressure (Disk/Memory/CPU)
│   └── 🌐 Networking-Issues
│       ├── CoreDNS-Resolution
│       ├── Kube-Proxy-Rules
│       └── CNI-Plugin-Status
│
├── 🏗️ 02-Cluster-Architecture-Installation-Configuration [25%]
│   ├── 🔐 Role-Based-Access-Control (RBAC)
│   │   ├── ServiceAccounts
│   │   ├── Roles-and-RoleBindings (Namespace)
│   │   └── ClusterRoles-and-ClusterRoleBindings (Cluster-wide)
│   ├── 🚀 Cluster-Installation-Kubeadm
│   │   ├── Control-Plane-Initialization (Kubeadm-Init)
│   │   └── Worker-Node-Provisioning (Kubeadm-Join)
│   ├── 🔧 Cluster-Maintenance-Upgrades
│   │   ├── Node-Draining (Drain-and-Uncordon)
│   │   └── Control-Plane-and-Kubeadm-Upgrades
│   ├── 💾 Etcd-Management
│   │   ├── Etcdctl-Snapshot-Backup
│   │   └── Etcdctl-Snapshot-Restore
│   └── 📦 Manifest-and-Package-Management
│       ├── Helm-Basics
│       └── Kustomize-Basics
│
├── 🌐 03-Services-and-Networking [20%]
│   ├── 🛡️ NetworkPolicies
│   │   ├── Ingress-Traffic-Isolation
│   │   └── Egress-Traffic-Isolation
│   ├── 🔌 Services-and-Endpoints
│   │   ├── ClusterIP (Internal)
│   │   ├── NodePort (External-Port)
│   │   ├── LoadBalancer (Cloud-Provider)
│   │   └── Endpoints-and-EndpointSlices
│   ├── 🛣️ Ingress-and-Gateway-API
│   │   ├── Ingress-Controllers-and-Rules
│   │   └── Gateway-API-Primitives
│   └── 🔍 DNS-and-Connectivity
│       ├── CoreDNS-Configuration
│       └── Pod-to-Pod-and-Pod-to-Service-Routing
│
├── 📦 04-Workloads-and-Scheduling [15%]
│   ├── 🔄 Deployments-and-Rollouts
│   │   ├── Rolling-Updates-and-Rollbacks
│   │   └── Manual-Scaling
│   ├── 🔑 ConfigMaps-and-Secrets
│   │   ├── Environment-Variable-Injection
│   │   └── Volume-Mount-Injection
│   ├── 🩺 Pod-Self-Healing
│   │   ├── Liveness-Probes
│   │   ├── Readiness-Probes
│   │   └── Startup-Probes
│   └── 🎯 Scheduling-Primitives
│       ├── Resource-Requests-and-Limits
│       ├── NodeSelector-and-Node-Affinity
│       └── Taints-and-Tolerations
│
└── 💾 05-Storage [10%]
    ├── 📁 PersistentVolumes (PV)
    │   ├── Storage-Capacities-and-Plugins
    │   └── Reclaim-Policies (Retain/Delete)
    ├── 📥 PersistentVolumeClaims (PVC)
    │   ├── Access-Modes (RWO/RWX/ROX)
    │   └── Claim-Binding-to-PV
    ├── 🏢 StorageClasses
    │   └── Dynamic-Volume-Provisioning
    └── 🔌 Pod-Storage-Integration
        └── Mounting-PVCs-as-Volumes
</pre>