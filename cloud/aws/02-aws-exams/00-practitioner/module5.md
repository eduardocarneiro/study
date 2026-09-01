
![](Pasted%20image%2020260831210749.png)


**introduction**
![](Pasted%20image%2020260831210932.png)

![](Pasted%20image%2020260831211339.png)

**organizing aws cloud resources**
![](Pasted%20image%2020260831211743.png)

![](Pasted%20image%2020260831211934.png)


**more ways to connect to the aws cloud**
![](Pasted%20image%2020260831220735.png)

![](Pasted%20image%2020260831220837.png)

![](Pasted%20image%2020260831221839.png)


**subnets, security groups, and network access control lists**
![](Pasted%20image%2020260831222621.png)

![](Pasted%20image%2020260901165504.png)

![](Pasted%20image%2020260901165518.png)

![](Pasted%20image%2020260901165630.png)
**Stateless packet filtering**

Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound.

Recall the previous example of a traveler who wants to enter into a different country. This is similar to sending a request out from an Amazon EC2 instance and to the internet.

![](Pasted%20image%2020260901165901.png)
**Note:** If you have multiple Amazon EC2 instances within the same VPC, you can associate them with the same security group or use different security groups for each instance.

**Stateful packet filtering**

Security groups perform stateful packet filtering. They remember previous decisions made for incoming packets.

Consider the same example of sending a request out from an Amazon EC2 instance to the internet. When a packet response for that request returns to the instance, the security group remembers your previous request. The security group allows the response to proceed, regardless of inbound security group rules.

| Feature            | Security Groups                                                       | Network ACLs                                                 |
| ------------------ | --------------------------------------------------------------------- | ------------------------------------------------------------ |
| **Scope**          | Instance level (attached to EC2 instances)                            | Subnet level (associated with subnets)                       |
| **State**          | Stateful (remembers state)                                            | Stateless (doesn't remember state)                           |
| **Rule types**     | Only allow type rules                                                 | Both allow and deny type rules                               |
| **Return traffic** | Return traffic is automatically allowed if inbound traffic is allowed | Return traffic must be implicitly allowed in both directions |
| **Uses**           | Fine-grained control of traffic for individual EC2 instances          | Broad control of traffic in and out of subnets               |


**Amazon VPC Demo**

![](Pasted%20image%2020260901172411.png)

**global architectures**

![](Pasted%20image%2020260901172457.png)

![](Pasted%20image%2020260901172611.png)

![](Pasted%20image%2020260901174139.png)

![](Pasted%20image%2020260901174743.png)



**module summary**