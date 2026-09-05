
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


**Global Architectures**
![](Pasted%20image%2020260901175026.png)

VPN
![](Pasted%20image%2020260901175405.png)

Direct  Connect
![](Pasted%20image%2020260901175453.png)

![](Pasted%20image%2020260901175602.png)

![](Pasted%20image%2020260901175611.png)

customer global architecture
![](Pasted%20image%2020260901175838.png)


**module summary**

Resources

To learn more about the material covered in this module, choose the resource links in the following table.

|Resource link|Description|
|---|---|
|[Amazon Virtual Private Cloud(opens in a new tab)](https://aws.amazon.com/vpc/)|Amazon VPC is a service to provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.|
|[Subnet(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html)|A subnet is a section of a VPC that can contain resources and is used to organize your resources. They can contain be either public or private.|
|[Internet gateway(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)|An internet gateway is a connection between a VPC and the internet. It allows public traffic from the internet to access your VPC.|
|[Virtual private gateway(opens in a new tab)](https://docs.aws.amazon.com/vpn/latest/s2svpn/how_it_works.html#VPNGateway)|A virtual private gateway is the component that allows protected internet traffic to enter into the VPC. It allows a connection between your VPC and a private network only if it is coming from an approved network.|
|[AWS Client VPN(opens in a new tab)](https://aws.amazon.com/vpn/client-vpn/)|Amazon Client VPC is a networking service you can use to connect your remote workers and on-premises networks to the cloud. It is a fully managed, elastic VPN service that automatically scales up or down based on user demand.|
|[AWS Site-to-Site VPN(opens in a new tab)](https://aws.amazon.com/vpn/site-to-site-vpn/)|AWS Site-to-Site VPN creates a secure connection between your data center or branch offices and your AWS Cloud resources.|
|[AWS PrivateLink(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/privatelink/what-is-privatelink.html)|AWS PrivateLink is a highly available, scalable technology that you can use to privately connect your VPC to services and resources as though they were in your VPC.|
|[AWS Direct Connect(opens in a new tab)](https://aws.amazon.com/directconnect/)|AWS Direct Connect is a service that provides a dedicated private connection between your data center and a VPC.|
|[Network Access Control List (network ACL)(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)|A network ACL allows or denies specific inbound or outbound traffic at the subnet level using stateless packet filtering.|
|[Security groups(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)|Security groups control the inbound and outbound traffic for a resource at the instance level using stateful packet filtering.|
|[Domain Name System (DNS)(opens in a new tab)](https://aws.amazon.com/route53/what-is-dns/)|DNS translates human readable domain names to machine readable IP addresses (for example, 192.0.2.0).|
|[Amazon Route 53(opens in a new tab)](https://aws.amazon.com/route53/)|Route 53 is a scalable and reliable DNS web service that helps developers and businesses route end users to internet applications, whether they’re hosted in AWS or elsewhere. It also supports domain registration, health checks, and advanced traffic routing policies.|
|[Amazon CloudFront(opens in a new tab)](https://aws.amazon.com/cloudfront/)|CloudFront is a web service that speeds up distribution of your web content to your users through a worldwide network of data centers called edge locations. It securely delivers content with low latency and high transfer speeds.|
|[AWS Global Accelerator(opens in a new tab)](https://aws.amazon.com/global-accelerator/)|Global Accelerator is a networking service that helps improve the availability and performance of applications for global users by routing traffic through the AWS global network. It helps improve application availability, performance, and security.|
|[Amazon Transit Gateway(opens in a new tab)](https://aws.amazon.com/transit-gateway/)|Amazon VPC Transit Gateways is a network transit hub used to interconnect VPCs and on-premises networks.|
|[NAT Gateway(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)|Network Address Translation (NAT) gateway allows instances in a private subnet to connect with services outside your VPC. External services can't initiate a connection with those instances.|
|[API Gateway(opens in a new tab)](https://aws.amazon.com/api-gateway/)|The Amazon API Gateway is an AWS service for creating, publishing, maintaining, monitoring, and securing APIs at any scale. It handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls.|

