
<pre>
├── 2. AUTHENTICATION → <a href="#authentication">here</a>
│   │
│   ├── Console login → <a href="#console-login">here</a>
│   │
│   ├── Access keys → <a href="#access-keys">here</a>
│   │     ├── Access Key ID
│   │     └── Secret Access Key
│   │
│   ├── Temporary credentials → <a href="#temporary-credentials">here</a>
│   │
│   └── Multi-Factor Authentication (MFA) → <a href="#mfa">here</a>
│         ├── Virtual MFA
│         ├── Hardware MFA
│         ├── FIDO2 security keys
│         └── U2F keys
</pre>

---




<h1 id="authentication">🔐 PHASE 2 — AUTHENTICATION</h1>

## 🎯 Goal

Understand **how identities authenticate to AWS**.

This phase answers:

> “How does AWS verify who you are?”

## 🧠 BIG PICTURE

Authentication in Amazon Web Services is about proving identity before authorization happens.

## 🔄 Authentication vs Authorization

| Concept        | Question           |
| -------------- | ------------------ |
| Authentication | “Who are you?”     |
| Authorization  | “What can you do?” |



---
<h1 id="console-login">🖥️ 1. Console Login</h1>

## 📘 Definition

Authentication to the AWS web console using:

- Account ID / Alias
- Username
- Password
- MFA (optional but recommended)

## 🔄 Flow

```
User → Login Page → Username/Password → MFA → AWS Console
```

## 📦 Types of console login

### Root Login

```
Email + Password
```

⚠️ Full account access

### IAM User Login

```
Account ID + IAM Username + Password
```

Preferred over root.

### Federated Login

```
Okta / Azure AD / Google → AWS
```

Enterprise standard.

## 🧠 Important concepts

## Account Alias

Instead of:

```
123456789012.signin.aws.amazon.com
```

You can use:

```
my-company.signin.aws.amazon.com
```

## Password Policy

IAM supports:

- Minimum length
- Symbols
- Rotation
- Expiration

## ⚠️ Common mistake

> Leaving console access enabled for programmatic-only users



---
<h1 id="access-keys">🔑 2. Access Keys</h1>
## 📘 Definition

Access keys are long-term credentials used for:

- AWS CLI
- SDKs
- APIs
- Terraform
- Automation

## 🧩 Components

## 🪪 Access Key ID

Public identifier.

Example:

```
AKIAIOSFODNN7EXAMPLE
```

## 🔐 Secret Access Key

Private secret used for signing requests.

Example:

```
wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

## 🧠 Mental model

```
Username = Access Key 
IDPassword = Secret Access Key
```

## 🔄 Flow

```
CLI/SDK → Signed Request → AWS validates signature
```

## ⚠️ CRITICAL SECURITY CONCEPT

## Access Keys are dangerous because:

- Long-term credentials
- Often hardcoded
- Frequently leaked to GitHub

## 🚫 Best practice

> Prefer Roles + Temporary Credentials over Access Keys

## 🔥 Real-world example

## Bad

```
aws_access_key_id="AKIA..."aws_secret_access_key="SECRET..."
```
Hardcoded inside application.

## Good

```
EC2 Role → Temporary Credentials
```

## 🧠 Important operational concepts

## Key Rotation

Rotate keys periodically.

## Multiple Keys

A user can have:

```
Maximum: 2 active access keys
```

Useful for rotation.

## CLI Credential Location

Linux/macOS:

```
~/.aws/credentials
```



---
<h1 id="temporary-credentials">⏳ 3. Temporary Credentials</h1>
## 📘 Definition

Short-lived credentials generated dynamically via:

- IAM Roles
- STS
- Federation

## 🧠 This is the modern AWS security model

Instead of:

```
Permanent credentials
```

AWS prefers:

```
Ephemeral credentials
```

# 📦 Components

Temporary credentials contain:

- Access Key ID
- Secret Access Key
- Session Token

## 🤯 New concept: Session Token

Temporary credentials require:

```
Session Token
```

This proves the credentials are temporary.

## 🔄 Flow

```
User/Service → AssumeRole → STS → Temporary Credentials
```

## 📦 Real examples

|Service|Uses Temporary Credentials|
|---|---|
|EC2 Role|Yes|
|Lambda Role|Yes|
|EKS IRSA|Yes|
|AWS SSO|Yes|
## ⚠️ Key insight

> Roles do NOT have passwords or access keys

They generate temporary credentials dynamically.



---
<h1 id="mfa">🔐 4. Multi-Factor Authentication (MFA)</h1>
## 📘 Definition

MFA adds:

```
Something you know
+
Something you have
```

## 🧠 Mental model

```
Password alone = weak
Password + MFA = strong
```

## 📦 MFA TYPES

## 📱 Virtual MFA

## Examples

- Google Authenticator
- Authy
- Microsoft Authenticator

## 🔄 Flow

```
Login → Enter TOTP Code → Access granted
```

🧠 Most common MFA type

## 🔑 Hardware MFA

## 📘 Definition

Physical device generating authentication codes.

## 📦 Examples

- RSA tokens
- Dedicated OTP devices

## 🧠 Used in:

- High-security environments
- Compliance-heavy companies

## 🛡️ FIDO2 Security Keys

## 📘 Definition

Modern phishing-resistant hardware authentication.

## 📦 Examples

- YubiKey
- Titan Security Key

## 🔥 Key advantage

Resistant to:

- Phishing
- Credential replay

## 🧠 Enterprise-grade MFA

Preferred for:

- Admin access
- Privileged accounts

## 🔐 U2F Keys

## 📘 Definition

Older standard for hardware-based MFA.

## 🧠 Relationship

```
U2F → predecessor of FIDO2
```

## 🧠 AUTHENTICATION FLOW (VERY IMPORTANT)

```
1. Identity provides credentials
2. AWS validates identity
3. MFA validation (optional)
4. Authentication succeeds
5. Authorization evaluation begins
```

## 🧠 WHAT YOU JUST LEARNED

|Topic|Learned|
|---|---|
|Console Login|Human access|
|Access Keys|Programmatic access|
|Temporary Credentials|Secure ephemeral access|
|MFA|Strong authentication|
|STS Identity|Identity validation|
## ⚠️ COMMON MISTAKES

- Hardcoding access keys
- No MFA on admin users
- Sharing access keys
- Using root access keys
- Long-lived credentials in CI/CD

## 🔥 CERTIFICATION-LEVEL INSIGHT

## AWS best practice:

```
Humans → Federation + MFA
Applications → Roles
Avoid → Long-term Access Keys
```



---
# 🧪 🔥 PRACTICAL EXERCISE (ESSENTIAL)

## 🎯 Goal

Practice ALL authentication methods together.

🛠️ LAB

## 1. Create IAM User

```
Name: auth-lab-user
```

Enable:

- Console access

## 2. Enable MFA

Choose:

- Virtual MFA

Test login with MFA.

## 3. Create Access Keys

IAM → User → Security Credentials

Create:

```
Access Key ID
Secret Access Key
```

## 4. Configure AWS CLI

Run:

```
aws configure
```

Provide:

- Access Key
- Secret Key
- Region

## 5. Test Authentication

Run:

```
aws sts get-caller-identity
```

## 🧠 Analyze the result

You will see:

- Account ID
- ARN
- Authenticated identity

## 6. Compare with Temporary Credentials (optional advanced)

Attach role to EC2 and run:

```
aws sts get-caller-identity
```

Notice:

- Different ARN
- Assumed role identity

