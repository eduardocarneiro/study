<pre>
├── 1. IDENTITIES (Principals)
│   │
│   ├── <a href="#root-user">Root User</a>
│   │
│   ├── [IAM Users](#iam-users)
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

</pre>

---

# 🚀 PHASE 1 — **IDENTITIES (Principals)**

## 🎯 Goal

Understand **who is making requests in AWS** and how identities are structured.

<h1 id="root-user">🧱 1. Root User</h1>

### 📘 Definition

The **Root User** is the original identity created when you open an Amazon Web Services account.

### ⚠️ Key Characteristics

- Has **full unrestricted access**
- Cannot be limited by IAM policies
- Should be used **only for critical account-level tasks**

### 🚫 Real-world rule

> If you are using root daily, you're doing it wrong.


 <h1 id="iam--users">👤 2. IAM Users</h1>
 
### 📘 Definition

An **IAM User** is a **long-term identity** for a person or application.

### 🔑 Components

- **Console password** → Web login
- **Access keys** → CLI / API access
- **MFA devices** → Extra security layer
- **Tags** → Metadata (e.g., team=dev)
- **Permissions** → Defined via policies
- **SSH keys (CodeCommit)** → Git access


### 🧠 When to use

- Small environments
- Individual access (labs, learning)

👉 In real companies, users are often replaced by **federation (later topic)**


# 👥 3. IAM Groups


### 📘 Definition

A **Group** is a collection of IAM Users.

### 🎯 Purpose

- Assign permissions **once**
- Apply to **multiple users**

### ✅ Example

```
Group: adminsPolicy: AdministratorAccessUsers: eduardo-admin, sarah-admin
```


### 🧠 Key rule

> You attach permissions to **groups, not users** (best practice)


# 🎭 4. IAM Roles


### 📘 Definition

A **Role** is an identity that is **assumed temporarily**.

### 🔥 Key difference vs User

|User|Role|
|---|---|
|Permanent|Temporary|
|Has credentials|Uses temporary credentials|
|Assigned to a person|Assumed by entities|

### 📦 Types (intro level)

- **Service Roles** → Used by AWS services (EC2, Lambda)
- **Cross-account Roles** → Access between accounts
- **Federation Roles** → External identities
- **Service-linked Roles** → Auto-created by AWS
- **Instance Profiles** → Roles attached to EC2

### 🧠 Real-world insight

> Roles are the **most important concept in IAM**

