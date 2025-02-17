## **VPC**

### 基本概念

京东云私有网络(Virtual Private Cloud，下文简称VPC)，是您在京东公有云上自定义的逻辑隔离的网络空间，与您在数据中心搭建的传统网络类似，此私有网络空间由用户完全掌控，支持自定义网段划分、路由策略等。用户可以在VPC内创建和管理多种云产品，如云主机、负载均衡等，同时可配置网络内的资源连接Internet。另外，您可以通过VPN、专线接入，打通您的IDC内网和京东云网络，实现应用的混合云部署，以及应用的平滑迁移至云上。

京东云私有网络为您提供以下功能：

- 通过控制台和 API 创建VPC、自定义网段划分、IP地址、路由策略等
- 通过公网IP、NAT Instance等方式灵活访问 Internet
- 通过网络 ACL可以实现子网级别的访问控制。
- 通过安全组可以实现实例级别的访问控制。

用户在创建 VPC 时，可以按无类别域间路由块(CIDR，例如 10.0.0.0/16)的形式为 VPC 指定 IP 地址范围，也可以不预设CIDR（此时VPC的范围将随在其中创建的子网的CIDR范围而动态改变）。在创建支持IPv6 VPC时，京东云为您提供固定大小的（/56）IPv6 CIDR，您无法选择IPv6 CIDR范围，私有网络有地域属性，您无法跨地域使用VPC。不同VPC之间的IP地址块可以重叠。



### 私有网络的IP地址

您可以通过指定CIDR（无类别域间路由）实现对私有网络和子网整体IP划分，京东云VPC中用户可以使用的IP地址分为两类：

- 内网IP地址，VPC 内的资源自动分配的IP地址，范围为RFC1918约定的私网地址段。内网IP地址属于overlap IP，可用于VPC内资源之间的互相通信，无法直接进行Internet通信。
- 公网IP地址，用户可以独立申请的地址，支持与资源的动态绑定和解绑。公网IP地址是全世界唯一的公网地址，可用于资源与Internet之间的通信。



### **CIDR**

CIDR（无类别域间路由，Classless Inter-Domain Routing）是由用户指定的独立网络空间地址块，通过prefix和mask结合，实现对地址的划分。以10.1.0.0/16为例，斜杠左边的10.1.0.0为prefix，斜杠右边的16为mask。通过设定mask的大小就可以调整网络块的大小。私有网络的网络块包括的IP数为2^(32-mask)，因而10.1.0.0/16网络块最多包含65536个IP地址。

在规划CIDR时需要注意：

- 私有网络创建时可选是否指定 CIDR，若您对网络有深入了解，或对于未来网络规模发展不确定，建议您选择以无CIDR的方式创建VPC。
- 子网的 CIDR 必须是所在VPC CIDR 的一部分。
- 目前私有网络支持IPv4三个网段的内网IP：10.a.0.0/16（a属于0至255）、172.b.0.0/16（b属于16至31）、192.168.0.0/16。
- 目前VPC和子网 CIDR 的mask值支持16至28之间的整数。
- 对于支持IPv6地址的VPC，不支持自定义CIDR，京东云提供固定大小的（/56）IPV6 CIDR

关于CIDR的具体请见：https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing

## 相关参考

- [子网](https://docs.jdcloud.com/cn/virtual-private-cloud/subnet-features)
- [配置VPC](../../Operation-Guide/VPC-Configuration.md)
- [配置子网](../../Operation-Guide/Subnet-Configuration.md)
- [使用限制](https://docs.jdcloud.com/cn/virtual-private-cloud/restrictions)
- [常见问题](../../FAQ/FAQ.md)


