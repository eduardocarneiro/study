
├── 1. IDENTITIES (Principals)
│   │
│   ├── Root User
│   │
│   ├── IAM Users
│   │     ├── Console password
│   │     ├── Access keys
│   │     ├── MFA devices
│   │     ├── Tags
│   │     ├── Permissions
│   │     └── SSH keys (CodeCommit)
│   │
│   ├── IAM Groups
│   │     ├── Attach policies
│   │     └── Organize users
│   │
│   └── IAM Roles
│         │
│         ├── Service Roles
│         │     ├── EC2 roles
│         │     ├── Lambda roles
│         │     ├── ECS task roles
│         │     ├── EKS node roles
│         │     └── Step Functions roles
│         │
│         ├── Cross-Account Roles
│         │
│         ├── Federation Roles
│         │
│         ├── Service-Linked Roles
│         │
│         └── Instance Profiles

---

# 🚀 PHASE 1 — **IDENTITIES (Principals)**

## 🎯 Goal

Understand **who is making requests in AWS** and how identities are structured.

--- 
# 🧱 1. Root User

### 📘 Definition

The **Root User** is the original identity created when you open an Amazon Web Services account.

### ⚠️ Key Characteristics

- Has **full unrestricted access**
- Cannot be limited by IAM policies
- Should be used **only for critical account-level tasks**

### 🚫 Real-world rule

> If you are using root daily, you're doing it wrong.


----
# 👤 2. IAM Users

### 📘 Definition

An **IAM User** is a **long-term identity** for a person or application.

### 🔑 Components

- **Console password** → Web login
- **Access keys** → CLI / API access
- **MFA devices** → Extra security layer
- **Tags** → Metadata (e.g., team=dev)
- **Permissions** → Defined via policies
- **SSH keys (CodeCommit)** → Git access

---

### 🧠 When to use

- Small environments
- Individual access (labs, learning)

👉 In real companies, users are often replaced by **federation (later topic)**