
<pre>
Hyperledger_Besu_Certified_Professional_Study_Guide/
│
├── Domain_1_Networking_(26%)
│   ├── 1.1_Peer_Discovery_and_Topology
│   │   ├── Discovery Protocols (Node Discovery v4 & v5, enode URLs)
│   │   ├── Bootnodes (Network bootstrapping, --bootnodes flag, lifecycle)
│   │   ├── Network Topologies (static-nodes.json vs dynamic discovery)
│   │   └── P2P Communication (Port 30303 TCP/UDP, --max-peers, --p2p-host)
│   │
│   ├── 1.2_RPC_and_Connectivity
│   │   ├── API Protocols (JSON-RPC, WebSockets, GraphQL endpoints)
│   │   ├── Endpoint Security (--rpc-http-cors-origins, allowlists, JWT)
│   │   ├── APIs Namespaces (eth, net, web3, admin, txpool, perm, ibft, qbft)
│   │   └── Load Balancing & HA (Multi-node RPC, Ingress/Route Sticky Sessions)
│   │
│   └── 1.3_Node_Synchronization
│       ├── Syncing Mechanisms (Full Sync, Fast Sync, Snap Sync)
│       ├── State Propagation (Block propagation, transaction pool sync)
│       └── Chain ID Configuration (--network-id)
│
├── Domain_2_Besu_Core_Concepts_(24%)
│   ├── 2.1_Ethereum_and_Blockchain_Fundamentals
│   │   ├── Ethereum Protocol Implementation (EVM specifications)
│   │   ├── Blockchain Trilemma (Decentralization, Security, Scalability)
│   │   └── Gas and Fees (Computation limits, EIP-1559 Base & Priority fees)
│   │
│   ├── 2.2_Node_Types_and_Architecture
│   │   ├── Validator Nodes (Block signing, subnet isolation)
│   │   ├── RPC Nodes (Horizontal scaling, API access layer)
│   │   ├── Bootnodes (Routing nodes, discovery endpoints)
│   │   └── Archive vs Full Nodes (Data retention strategies, state pruning)
│   │
│   └── 2.3_Network_Initialization
│       ├── The Genesis File (genesis.json syntax and components)
│       ├── Chain Configuration (Hard fork blocks, block period, alloc)
│       └── Mining and Sealing (--miner-enabled, --miner-coinbase)
│
├── Domain_3_Transactions_and_Storage_(14%)
│   ├── 3.1_Data_Structures_&_State_Management
│   │   ├── World State (Accounts, balances, nonces, smart contract code)
│   │   ├── Patricia Merkle Trees (Cryptographic state verification)
│   │   └── Transaction Lifecycle (Broadcast, txpool, EVM execution, block sealing)
│   │
│   └── 3.2_Storage_Engines_&_Performance
│       ├── Database Types (Bonsai Tries vs Forest Tries)
│       ├── RocksDB Configuration (--data-storage-format, pruning flags)
│       └── Token Standards (ERC-20, ERC-721, ERC-1155 state alterations)
│
├── Domain_4_Cryptography_(10%)
│   ├── 4.1_Encryption_and_Hashing
│   │   ├── Symmetric vs Asymmetric Cryptography (Node communication & integrity)
│   │   └── Hashing Algorithms (Keccak-256 for hashes and addresses)
│   │
│   └── 4.2_Keys_and_Signatures
│       ├── ECDSA (SECP256k1 curve for keys and address derivation)
│       ├── Transaction Signing (RLP encoding, v, r, s components)
│       └── Key Management System (HashiCorp Vault, AWS KMS, External Secrets Operator)
│
├── Domain_5_Permissioning_and_Privacy_(10%)
│   ├── 5.1_On-Chain_and_Local_Permissioning
│   │   ├── Node Permissioning (permissions_config.toml vs smart contracts)
│   │   ├── Account Permissioning (EOA transaction & deployment restrictions)
│   │   └── Enterprise Governance (Dynamic adjustments using perm API namespace)
│   │
│   └── 5.2_Privacy_Architecture
│       ├── Private Transactions (Tessera orchestration and coupling)
│       ├── Privacy Groups (Restricted Private Groups & Flexible Private Groups)
│       └── Off-Chain World State (Isolated state transitions, cryptographic anchors)
│
├── Domain_6_Execution_Engine_and_Consensus_(8%)
│   ├── 6.1_Consensus_Mechanisms
│   │   ├── Proof of Authority (PoA core mechanics for corporate setups)
│   │   ├── IBFT 2.0 (Immediate finality, voting mechanics, F faulty nodes tolerance)
│   │   ├── QBFT (Enhanced BFT algorithm, validator rotation, robustness updates)
│   │   └── Clique (Round-robin block creation, dev setups)
│   │
│   └── 6.2_Validator_Management
│       ├── Voting Protocol (propose and discard via JSON-RPC APIs)
│       └── Epoch Transition (Resetting validator lists during block epochs)
│
└── Domain_7_Monitoring_and_Production_Operations_(8%)
    ├── 7.1_Metrics_Collection
    │   ├── Prometheus Integration (--metrics-enabled, --metrics-host/port)
    │   └── Grafana Dashboards (Block height, peers, CPU/Memory, disk I/O, JVM, txpool)
    │
    ├── 7.2_Troubleshooting_and_Log Management
    │   ├── Log Configurations (--logging flag: INFO, DEBUG, TRACE)
    │   ├── Common Errors (Disconnections, forks, genesis mismatch, gas exhaustion)
    │   └── GitOps Delivery (Red Hat OpenShift GitOps, ArgoCD, parameterized Helm Charts)
    └── Recommended_Free_Hands-on_Resource
        └── Linux Foundation Course (Besu Essentials: Creating a Private Blockchain Network - LFS176x)

7 directories, 46 topics
</pre>

## references:
* https://training.linuxfoundation.org/certification/besu-certified-professional/
