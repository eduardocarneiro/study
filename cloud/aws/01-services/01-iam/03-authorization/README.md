
<pre>
├── 3. AUTHORIZATION (POLICIES)
│   │
│   ├── Policy Types
│   │     │
│   │     ├── Identity-based policies
│   │     │     ├── AWS Managed Policies
│   │     │     ├── Customer Managed Policies
│   │     │     └── Inline Policies
│   │     │
│   │     ├── Resource-based policies
│   │     │     ├── S3 Bucket Policies
│   │     │     ├── Lambda Resource Policies
│   │     │     ├── KMS Key Policies
│   │     │     ├── SNS Topic Policies
│   │     │     └── SQS Queue Policies
│   │     │
│   │     ├── Permissions Boundaries
│   │     │
│   │     ├── Session Policies
│   │     │
│   │     ├── Service Control Policies (SCP)
│   │     │
│   │     └── Resource Control Policies (RCP)
│   │
│   ├── Policy Structure
│   │     │
│   │     ├── Version
│   │     ├── Statement
│   │     │
│   │     ├── Effect
│   │     │     ├── Allow
│   │     │     └── Deny
│   │     │
│   │     ├── Action
│   │     │
│   │     ├── Resource
│   │     │
│   │     ├── Principal
│   │     │
│   │     └── Condition
│   │
│   └── Policy Conditions
│         │
│         ├── String conditions
│         ├── Numeric conditions
│         ├── Date conditions
│         ├── Boolean conditions
│         ├── IP conditions
│         ├── ARN conditions
│         └── Tag conditions
</pre>

---



# 🔐 PHASE 3 — AUTHORIZATION (POLICIES)

## 🎯 Goal

Understand how Amazon Web Services decides:

> “What are you allowed to do?”

This is the **core of IAM**.

If authentication answers:

```
Who are you?
```

Authorization answers:

```
What can you do?
```

## 🧠 BIG PICTURE

AWS authorization is based on:

```
JSON Policies
```

Policies define:

- WHO
- can do WHAT
- on WHICH resource
- under WHICH conditions

# 🧩 POLICY TYPES

## 👤 1. Identity-Based Policies

### 📘 Definition

Policies attached to:

- Users
- Groups
- Roles

### 🧠 **Mental model**

```
Identity → gets permissions
```

### 🌎 **AWS Managed Policies**

### 📘 Definition

Policies created and maintained by AWS.

### 📦 **Examples**

- `AdministratorAccess`
- `ReadOnlyAccess`
- `AmazonS3ReadOnlyAccess`

### ✅ **Advantages**

- Easy to use
- Maintained by AWS

### ⚠️ **Disadvantages**

- Often too broad
- Less control

### 🛠️ **Customer Managed Policies**

### 📘 **Definition**

Policies YOU create and manage.

### 🧠 **Best practice**

> Preferred in production

### 🔥 **Example**

Allow only:

- `s3:GetObject`
- specific bucket

### 📎 **Inline Policies**

### 📘 Definition

Policy embedded directly into:

- one user
- one role
- one group

### ⚠️ **Important**

Inline policies:

- cannot be reused
- tightly coupled to identity

### 🧠 **Mental model**

```
Managed Policy = reusableInline Policy = one-to-one
```

### 📦 **Identity-Based Policy Example**

``` JSON
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "*"
    }
  ]
}
```