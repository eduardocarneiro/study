
<pre>
├── 1. IDENTITIES (Principals)
│   │
│   ├── Root User → <a href="#root-user">here</a>
│   │
│   ├── IAM Users → <a href="#iam-users">here</a>
│   │     ├── Console password
│   │     ├── Access keys
│   │     ├── MFA devices
│   │     ├── Tags
│   │     ├── Permissions
│   │     └── SSH keys (CodeCommit)
│   │
│   ├── IAM Groups → <a href="#iam-groups">here</a>
│   │     ├── Attach policies
│   │     └── Organize users
│   │
│   └── IAM Roles → <a href="#iam-roles">here</a>
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


<h1 id="iam-groups">👥 3. IAM Groups</h1>

### 📘 Definition

A **Group** is a collection of IAM Users.

### 🎯 Purpose

- Assign permissions **once**
- Apply to **multiple users**

### ✅ Example

```
Group: adminsPolicy: AdministratorAccessUsers: user01-admin, user02-admin
```


### 🧠 Key rule

> You attach permissions to **groups, not users** (best practice)


<h1 id="iam-roles">🎭 4. IAM Roles</h1>
### 📘 Definition

A **Role** is an identity that is **assumed temporarily**.

### 🔥 Key difference vs User

| User                 | Role                       |
| -------------------- | -------------------------- |
| Permanent            | Temporary                  |
| Has credentials      | Uses temporary credentials |
| Assigned to a person | Assumed by entities        |

### 📦 Types (intro level)

- **Service Roles** → Used by AWS services (EC2, Lambda)
- **Cross-account Roles** → Access between accounts
- **Federation Roles** → External identities
- **Service-linked Roles** → Auto-created by AWS
- **Instance Profiles** → Roles attached to EC2

### 🧠 Real-world insight

> Roles are the **most important concept in IAM**

---
### 🔧 **Service Roles**
📘 Definition

A Service Role is a role assumed by an AWS service to perform actions on your behalf.
🧠 Mental model

    “I (user) allow AWS service X to act for me”

📦 Examples

  *  EC2 accessing S3
  *  Lambda writing logs to CloudWatch
  *  ECS pulling images from ECR

🔄 Flow (important)

 1.   You create a role
 2. You attach permissions (policy)
 3. You allow a service to assume it (trust policy)
 4. The service uses it automatically

🔥 Real example

`EC2 → Role → S3`

No access keys needed.

⚠️ Key insight

    This replaces hardcoded credentials → critical security concept

---
### 🌐 **Cross-Account Roles**

### 📘 Definition

A role that allows **one AWS account to access another AWS account**


### 🧠 Mental model

> “Account A trusts Account B”


### 🔄 Flow

1. Account A creates a role
2. Trust policy allows Account B
3. Account B assumes the role via STS


### 📦 Example

```
Company Account (A)   ↑   | AssumeRole   ↓Dev Account (B)
```


### ⚠️ Key concept

- Uses:
    - `sts:AssumeRole`
- Requires:
    - **Trust Policy**


### 🔥 Real-world use

- Multi-account architecture
- Central security account
- CI/CD pipelines accessing other accounts

---
## 🔐 3. Federation Roles

### 📘 Definition

Roles used by **external identity providers** (IdP)

### 🧠 Mental model

> “Login outside AWS → get temporary access inside AWS”


### 📦 Identity Providers

- Active Directory
- Okta
- Azure AD
- Google
- GitHub (OIDC)

### 🔄 Flow

1. User logs in to external system
2. IdP authenticates user
3. AWS trusts IdP
4. User assumes role via:
    - SAML
    - OIDC


### 🔥 Example

```
User → Okta → AWS Role → Access AWS
```


### ⚠️ Key insight

> No IAM users needed → **enterprise standard**

---

## 🖥️ 5. Instance Profiles

### 📘 Definition

A container for a role that is attached to an EC2 instance

### 🤯 Important (confusing part)

> EC2 **does not attach a role directly**  
> It attaches an **Instance Profile**

### 🧠 Mental model

```
EC2 → Instance Profile → Role → Permissions
```


### 🔄 Flow

1. Create role
2. AWS automatically creates instance profile
3. Attach to EC2
4. EC2 gets temporary credentials

### 🔥 Real example

```
EC2 → S3 (without access keys)
```

### ⚠️ Key insight

> Instance Profile = bridge between EC2 and IAM Role

---

# 🧠 🔥 COMPARISON (THIS IS GOLD)

|Type|Used by|Purpose|Credentials|
|---|---|---|---|
|Service Role|AWS service|Act on your behalf|Temporary|
|Cross-account|Another account|Access between accounts|Temporary|
|Federation|External users|SSO login|Temporary|
|Service-linked|AWS service|Internal AWS operations|Managed|
|Instance Profile|EC2|Attach role to EC2|Temporary|
