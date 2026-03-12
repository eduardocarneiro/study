---

---

-------
# 📊 Estratégia para passar na prova

Use este fluxo:

1) Identificar palavra chave  
2) Identificar categoria (storage / compute / security)  
3) Eliminar serviços que não pertencem à categoria  
4) Escolher opção managed

Tempo médio por questão:

```
20 – 30 segundos
```

--------
# 🧠 SUPER REGRA (APROVAÇÃO)

Sempre pergunte:

O que a AWS quer?  
  
1) serverless  
2) managed  
3) escalável  
4) menos manutenção

A alternativa que segue essas 4 regras geralmente é a correta.


----
# 🎯 MÉTODO PARA ELIMINAR 70% DAS ALTERNATIVAS

## 1️⃣ Elimine serviços que NÃO combinam com o problema

Exemplo típico:

Se a pergunta fala de:

**HPC / baixa latência**

✔ provável

- Placement Group (cluster)
- Elastic Fabric Adapter
- EC2 optimized network

❌ eliminar

- S3
- CloudFront
- DynamoDB
    

## 2️⃣ Procure palavras-chave da AWS

| Palavra na questão | Resposta provável           |
| ------------------ | --------------------------- |
| low latency HPC    | **Placement Group cluster** |
| durable storage    | **S3**                      |
| archive barato     | **Glacier**                 |
| shared file Linux  | **EFS**                     |
| Windows file share | **FSx Windows**             |
| streaming data     | **Kinesis**                 |
| ETL                | **Glue**                    |
| events             | **EventBridge**             |
| queue              | **SQS**                     |

Isso sozinho elimina **metade das opções**.

## 3️⃣ Regra de ouro da prova

A AWS ama:

✔ **Managed services**  
✔ **Serverless**  
✔ **Low operational overhead**

Então quase sempre:

❌ EC2 manual  
✔ serviço gerenciado


--------
# 🎯 Como eliminar **70% das alternativas erradas**

A prova da AWS é **muito previsível**.

Existem **5 padrões que eliminam a maioria das respostas erradas.**


------

# 🔎 REGRA 1 — “Least Operational Overhead”

Se a questão diz:
- **least operational overhead**
- **fully managed**
- **serverless**
    
👉 escolha **serviço gerenciado**

Exemplo:

ERRADO ❌

```
EC2 + script
```

CERTO ✅

```
Lambda  
S3 lifecycle  
DynamoDB
```

Serviços que **quase sempre são resposta**:

- AWS Lambda
- Amazon S3 
- Amazon DynamoDB


# 🔎 REGRA 2 — Alta disponibilidade

Se aparece:
- **high availability** 
- **fault tolerant**

elimine tudo que não usa **Multi-AZ**

Exemplo

ERRADO ❌

```
Single AZ  
Single instance
```
CERTO ✅

```
Multi-AZ  
Auto Scaling  
Load Balancer
```

Serviços comuns:

- Elastic Load Balancing
- Amazon EC2 Auto Scaling
- Amazon RDS

# 🔎 REGRA 3 — Custo otimizado

Se diz:

- **most cost-effective**
- **lowest cost**
    
Elimine:

❌ soluções enterprise caras

Exemplo:

ERRADO ❌

```
Direct Connect  
EC2 cluster  
Aurora Global
```

CERTO ✅

```
S3  
CloudFront  
Spot  
Lifecycle
```


# 🔎 REGRA 4 — Escalabilidade

Se diz:

- **millions of users**
- **global users**
- **massive traffic**
    
A resposta quase sempre envolve:

- Amazon CloudFront
- Amazon SQS
- Amazon DynamoDB

Arquitetura típica:

```
CloudFront  
↓  
ALB  
↓  
Auto Scaling  
↓  
DynamoDB
```

# 🔎 REGRA 5 — Segurança

Se fala:

- SQL injection
- XSS
- bots

A resposta quase sempre é
- AWS WAF
    
Se for DDoS
- AWS Shield

-------------
# ⚡ Técnica final (usada por arquitetos AWS)

Quando você vê a pergunta:

1️⃣ Leia **a última frase primeiro**

Exemplo:

```
Which solution is MOST cost-effective?
```

Isso já elimina **metade das opções**.

---

2️⃣ Procure palavras-chave

|Palavra|Serviço|
|---|---|
|serverless|Lambda|
|event|EventBridge|
|queue|SQS|
|stream|Kinesis|
|shared filesystem|EFS|
|block storage|EBS|
|object storage|S3|

---

3️⃣ Elimine arquitetura complexa

Se existir opção:

```
EC2 + scripts + custom scaling
```

Quase sempre está errada.

----------
# 🚀 Dica de ouro para o SAA-C03

A maioria das questões se resume a **10 serviços principais**:

Memorize estes:

- Amazon EC2
- Amazon S3
- Amazon RDS
- Amazon DynamoDB
- AWS Lambda
- Amazon CloudFront
- Amazon SQS
- AWS WAF
- Amazon EFS
- Amazon VPC

**90% da prova gira em torno deles.**

-----

# 🎯 Padrões que aparecem MUITO no exame

Memorize isso:

| Problema                      | Resposta AWS        |
| ----------------------------- | ------------------- |
| Arquivos compartilhados       | EFS                 |
| Arquivos grandes distribuídos | S3                  |
| Latência global               | CloudFront          |
| Fila entre sistemas           | SQS                 |
| Eventos                       | EventBridge         |
| API serverless                | API Gateway         |
| Autenticação corporativa      | IAM Identity Center |
| Proteção web                  | WAF                 |
| DDoS                          | Shield              |
| SQL altamente disponível      | RDS Multi-AZ        |
| Read scaling                  | Read Replica        |
| Multi-region DB               | Aurora Global       |

-----------

🧠 MAPA MENTAL COMPLETO — SAA-C03

```
AWS Solutions Architect Associate
│
├── 1. Identity & Security
│   ├── IAM
│   │   ├── Users
│   │   ├── Groups
│   │   ├── Roles
│   │   └── Policies
│   │
│   ├── Federation
│   │   ├── SAML
│   │   ├── Active Directory
│   │   └── AWS IAM Identity Center
│   │
│   ├── Secrets
│   │   ├── Secrets Manager
│   │   └── Parameter Store
│   │
│   └── Encryption
│       ├── KMS
│       ├── SSE-S3
│       ├── SSE-KMS
│       └── SSE-C
│
├── 2. Compute
│   ├── EC2
│   │   ├── On-Demand
│   │   ├── Reserved
│   │   ├── Spot
│   │   └── Placement Groups
│   │
│   ├── Auto Scaling
│   │   ├── Target Tracking
│   │   ├── Step Scaling
│   │   └── Scheduled Scaling
│   │
│   ├── Containers
│   │   ├── ECS
│   │   ├── Fargate
│   │   └── EKS
│   │
│   └── Serverless
│       └── Lambda
│
├── 3. Storage
│   ├── S3
│   │   ├── Standard
│   │   ├── IA
│   │   ├── Intelligent Tiering
│   │   ├── Glacier
│   │   └── Glacier Deep Archive
│   │
│   ├── File Storage
│   │   ├── EFS
│   │   └── FSx
│   │
│   └── Block Storage
│       └── EBS
│
├── 4. Databases
│   ├── RDS
│   │   ├── Multi-AZ
│   │   ├── Read Replica
│   │   └── IAM Authentication
│   │
│   ├── Aurora
│   │   ├── Aurora Serverless
│   │   └── Aurora Global DB
│   │
│   ├── DynamoDB
│   │   ├── Streams
│   │   ├── Global Tables
│   │   └── DAX
│   │
│   └── Analytics
│       ├── Athena
│       └── Redshift
│
├── 5. Networking
│   ├── VPC
│   │   ├── Subnets
│   │   ├── Route Tables
│   │   ├── IGW
│   │   ├── NAT Gateway
│   │   └── Endpoints
│   │
│   ├── Connectivity
│   │   ├── VPN
│   │   ├── Direct Connect
│   │   └── Peering
│   │
│   └── Load Balancing
│       ├── ALB
│       ├── NLB
│       └── GWLB
│
├── 6. Integration
│   ├── SQS
│   ├── SNS
│   ├── EventBridge
│   └── Step Functions
│
├── 7. Edge Services
│   ├── CloudFront
│   ├── WAF
│   └── Shield
│
└── 8. Monitoring
    ├── CloudWatch
    ├── X-Ray
    └── CloudTrail
```