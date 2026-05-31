
<pre>
Openshift Container Platform 4.16
├── 01-about
│   ├── about
│   │   ├── Learn more about OpenShift Container Platform
│   │   │   ├── OpenShift Container Platform overview
│   │   │   └── Core features and capabilities
│   │   ├── Providing feedback on OpenShift Container Platform documentation
│   │   │   ├── Submitting a documentation feedback bug
│   │   │   └── Direct documentation editing
│   │   └── About OpenShift Kubernetes Engine
│   │       ├── OpenShift Kubernetes Engine overview
│   │       └── Included features and limitations
│   ├── getting-started
│   │   ├── Kubernetes overview
│   │   │   ├── What is Kubernetes?
│   │   │   └── Understanding containers and orchestration
│   │   ├── OpenShift Container Platform overview
│   │   │   ├── Architecture basics
│   │   │   └── Subscription and entitlement levels
│   │   ├── Creating and building an application using the web console
│   │   │   ├── Accessing the Developer perspective
│   │   │   └── Deploying a sample application from Git
│   │   └── Creating and building an application using the CLI
│   │       ├── Installing the oc CLI tool
│   │       └── Creating a new project and application via command line
│   ├── release-notes
│   │   └── OpenShift Container Platform 4.16 release notes
│   │       ├── New features and enhancements (such as Advanced Hosted Control Planes features)
│   │       ├── Deprecated and removed features (complete removal of OpenShift SDN)
│   │       ├── Bug fixes and known issues
│   │       └── Technology Preview features
│   ├── security-and-compliance
│   │   ├── Container security
│   │   │   ├── Core security concepts
│   │   │   └── Securing the container pipeline
│   │   ├── Configuring certificates
│   │   │   ├── Replacing the default ingress certificate
│   │   │   └── Adding custom CA certificates to the cluster
│   │   ├── Compliance Operator
│   │   │   ├── Supported compliance profiles (CIS, NIST, PCI-DSS)
│   │   │   └── Remediating non-compliant cluster settings
│   │   ├── File Integrity Operator
│   │   │   ├── Checking node file integrity
│   │   │   └── Configuring custom file integrity scans
│   │   └── Security Profiles Operator
│   │       ├── Managing Seccomp and AppArmor profiles
│   │       └── Binding profiles to workloads
│   ├── architecture
│   │   ├── OpenShift Container Platform architecture
│   │   │   ├── High-level infrastructure overview
│   │   │   └── Machine management and scaling
│   │   ├── Red Hat OpenShift Cluster Manager
│   │   │   ├── Registering clusters to Hybrid Cloud Console
│   │   │   └── Subscriptions and cluster history
│   │   └── Control plane architecture
│   │       ├── Etcd cluster state management
│   │       └── Master node components and topology (Hosted Control Planes as production standard)
│   └── support
│       ├── Support overview
│       │   ├── Opening a Red Hat support case
│       │   └── Remote health reporting (Telemetry)
│       ├── Managing your cluster resources
│       │   ├── Inspecting node and pod health
│       │   └── Gathering cluster logs for analysis
│       └── Troubleshooting
│           ├── Using the oc adm must-gather command
│           └── Troubleshooting node and networking failures
├── 02-install
│   ├── install-overview
│   │   └── Overview content for installing OpenShift Container Platform
│   │       ├── Choosing an installation type (IPI vs UPI)
│   │       └── Platform requirements and prerequisites
│   ├── disconnected-installation-mirroring
│   │   └── Mirroring the installation container images
│   │       ├── Creating a mirror registry in a disconnected network
│   │       └── Mirroring the OpenShift release images using oc-mirror v2 (enhanced performance)
│   ├── installing-on-alibaba
│   │   └── Installing OpenShift Container Platform on Alibaba Cloud
│   │       ├── Preparing Alibaba Cloud credentials and resources
│   │       └── Deploying a cluster with installer-provisioned infrastructure
│   ├── installing-on-aws
│   │   └── Installing OpenShift Container Platform on Amazon Web Services
│   │       ├── Installing a cluster on AWS into an existing VPC
│   │       └── Customizing AWS compute and control plane machine types
│   ├── installing-on-azure
│   │   └── Installing OpenShift Container Platform on Azure
│   │       ├── Deploying an IPI cluster on Microsoft Azure
│   │       └── Configuring private cluster endpoints on Azure
│   ├── installing-on-google-cloud
│   │   └── Installing OpenShift Container Platform on Google Cloud
│   │       ├── Deploying an installer-provisioned cluster on GCP
│   │       └── Shared VPC installations on Google Cloud
│   ├── installing-on-nutanix
│   │   └── Installing OpenShift Container Platform on Nutanix
│   │       ├── Creating the installation configuration file
│   │       └── Running the installer for Nutanix environments
│   ├── assisted-installer-for-openshift-container-platform
│   │   └── Assisted Installer User Guide
│   │       ├── Creating a cluster configuration via console
│   │       └── Generating and booting the Discovery ISO
│   ├── installing-an-on-premise-cluster-with-the-agent-based-installer
│   │   └── Installing an on-premise OpenShift Container Platform cluster with the Agent-based Installer
│   │       ├── Creating the agent-config.yaml and install-config.yaml
│   │       └── Generating the custom bootable boot image
│   ├── installing-on-a-single-node
│   │   └── Installing OpenShift Container Platform on a single node
│   │       ├── Single-node OpenShift (SNO) architecture and resource limits
│   │       └── Installing SNO using the Assisted Installer or ISO
│   ├── installing-on-bare-metal
│   │   └── Installing OpenShift Container Platform on bare metal
│   │       ├── Preparing user-provisional bare metal infrastructure
│   │       └── Creating the ignition files and installing nodes manually
│   ├── deploying-installer-provisioned-clusters-on-bare-metal
│   │   └── Deploying installer-provisioned OpenShift Container Platform clusters on bare metal
│   │       ├── Configuring the provisioning network and BMC details
│   │       └── Deploying bare metal clusters using the Metal3 Operator
│   └── installing-on-vmware-vsphere
│       └── Installing OpenShift Container Platform on VMware vSphere
│           ├── Installing a cluster on vSphere with installer-provisioned infrastructure (IPI)
│           └── Installing a cluster on vSphere with user-provisioned infrastructure (UPI)
├── 03-update-and-migrate
│   ├── updating-clusters
│   │   └── Updating OpenShift Container Platform clusters
│   │       ├── Updating a cluster using the web console
│   │       ├── Updating a cluster using the CLI
│   │       └── Understanding the OpenShift Update Graph and conditional updates
│   └── migrating-clusters
│       └── Migration Toolkit for Containers documentation
│           ├── Installing the Migration Toolkit for Containers (MTC)
│           └── Migrating workloads from OCP 3 to OCP 4 or between OCP 4 clusters
├── 04-configure-networking
│   ├── networking-overview
│   │   └── Red Hat OpenShift networking overview
│   │       ├── Understanding OpenShift software-defined networking (OVN-Kubernetes mandatory)
│   │       └── Migrating from legacy OpenShift SDN to OVN-Kubernetes
│   ├── cluster-network-operators
│   │   └── Cluster Network Operator configurations
│   │       ├── Modifying Cluster Network Operator (CNO) custom resources
│   │       └── Managing proxy and firewall configurations for the network
│   ├── ovn-kubernetes
│   │   └── About OVN-Kubernetes default network provider
│   │       ├── Hybrid networking with OVN-Kubernetes
│   │       └── Configuring egress IPs, egress firewalls, and IPsec encryption
│   ├── routes
│   │   └── Configuring and managing cluster routes
│   │       ├── Creating secure routes (Edge, Passthrough, Re-encryption)
│   │       └── Customizing route timeouts and annotations
│   ├── ingress-controller
│   │   └── Configuring Ingress Controller routing
│   │       ├── Scaling and tuning the Ingress Controller
│   │       └── Sharding the Ingress Controller using route selectors
│   └── network-plugins
│       └── Configuring various third-party and hardware network plugins
│           ├── Configuring Single Root I/O Virtualization (SR-IOV)
│           └── Using NMState to manage node network configurations
├── 05-configure-storage
│   ├── storage-overview
│   │   └── Configuring and expanding cluster storage
│   │       ├── Understanding persistent volume (PV) and PVC concepts
│   │       └── Managing storage classes
│   ├── persistent-storage
│   │   └── Configuring persistent storage options
│   │       ├── Configuring storage with AWS EBS / Azure Disk / GCP PD
│   │       └── Configuring storage using NFS or Local Storage Operator
│   ├── dynamic-provisioning
│   │   └── Dynamic provisioning configuration
│   │       ├── Setting a default storage class for automatic provisioning
│   │       └── Configuring volume resizing and expansion
│   └── container-storage-interface
│       └── CSI (Container Storage Interface) plugin overview
│           ├── Managing CSI inline volumes
│           └── Configuring CSI volume snapshots, clones, and Secrets Store CSI Driver integration
├── 06-authentication-and-authorization
│   ├── understanding-authentication
│   │   └── Configuring identity providers and user authentication
│   │       ├── Configuring HTPasswd identity provider for local accounts
│   │       └── Configuring OAuth and external OpenID Connect (OIDC) / LDAP
│   ├── rbac
│   │   └── Using Role-Based Access Control to secure cluster tasks
│   │       ├── Creating cluster roles and local role bindings
│   │       └── Default cluster roles overview
│   └── controlling-resource-access
│       └── Restricting API access and project creation
│           ├── Configuring project request templates
│           └── Restricting service account token creation and usage
├── 07-develop-applications
│   ├── serverless
│   │   └── Create and deploy serverless, event-driven applications using OpenShift Serverless
│   │       ├── Installing OpenShift Serverless Operator
│   │       └── Serving and routing Knative Services
│   ├── building-applications
│   │   └── Creating and managing applications on OpenShift Container Platform
│   │       ├── Using Source-to-Image (S2I) to build code directly
│   │       └── Configuring application deployment strategies (Rolling, Recreate)
│   ├── images
│   │   └── Creating and managing images and imagestreams in OpenShift Container Platform
│   │       ├── Using image streams to track container registry changes
│   │       └── Configuring the internal cluster image registry
│   ├── sandboxed-containers-support-for-openshift
│   │   └── OpenShift sandboxed containers guide
│   │       ├── Installing OpenShift sandboxed containers (Kata Containers)
│   │       └── Running isolated workloads inside dedicated microVMs
│   ├── operators
│   │   └── Working with Operators in OpenShift Container Platform
│   │       ├── Installing applications via OperatorHub
│   │       └── Controlling Operator lifecycles and subscription channels
│   └── specialized-hardware-and-driver-enablement
│       └── Learn about hardware enablement on OpenShift Container Platform
│           ├── Deploying the Node Tuning Operator
│           └── Enabling GPU workloads using the NVIDIA GPU Operator
├── 08-observability-and-logging
│   ├── monitoring
│   │   └── Monitoring cluster metrics and performance
│   │       ├── Enabling monitoring for user-defined projects
│   │       └── Configuring Prometheus alerts and managing Silences
│   ├── cluster-logging
│   │   └── Deploying and managing Red Hat OpenShift Logging
│   │       ├── Deploying the OpenShift Logging and Vector operators
│   │       └── Forwarding cluster logs to external systems (Elasticsearch, Kafka, Splunk) via Vector Engine exclusively
│   └── network-observability
│       └── Monitoring network traffic flows and bottlenecks
│           ├── Installing the Network Observability Operator
│           └── Visualizing flow logs using the web console network traffic dashboard
├── 09-virtualization
│   ├── openshift-virtualization-overview
│   │   └── Introduction to OpenShift Virtualization
│   │       ├── Understanding KVM and QEMU integration in pods
│   │       └── Core components (virt-launcher, virt-handler, virt-api)
│   ├── installing-virtualization
│   │   └── Installing and configuring OpenShift Virtualization Operator
│   │       ├── Preparing nodes for virtualization workloads (nested virtualization)
│   │       └── Deploying the OpenShift Virtualization custom resource
│   └── managing-virtual-machines
│       └── Creating, running, and managing Virtual Machines within containers
│           ├── Creating VMs from operating system templates
│           └── Implementing live migration for Virtual Machines across nodes
├── 10-ci-cd-and-gitops
│   ├── pipelines
│   │   └── CI/CD workflows using OpenShift Pipelines (Tekton)
│   │       ├── Installing the OpenShift Pipelines Operator
│   │       └── Creating cloud-native CD tasks, pipelines, and event triggers
│   └── gitops
│       └── Declarative cluster management using OpenShift GitOps (Argo CD)
│           ├── Installing the OpenShift GitOps Operator
│           └── Deploying multi-cluster and application states from Git repositories
└── 11-api-reference
    ├── kubernetes-api
    │   └── Comprehensive reference for standard Kubernetes API endpoints
    │       ├── Core v1 API (Pods, Services, Namespaces, ConfigMaps)
    │       └── Apps v1 API (Deployments, StatefulSets, DaemonSets)
    └── openshift-api
        └── Core custom resource definitions (CRDs) and API endpoints for OpenShift
            ├── Route and Ingress OpenShift specific APIs
            └── SecurityContextConstraints (SCC) and Build APIs reference
</pre>