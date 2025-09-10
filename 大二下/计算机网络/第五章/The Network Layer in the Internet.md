# The Network Layer in the Internet

![image-20250512082526935](E:\mywork\mindgraghs\main_\大二下\计算机网络\第五章\tcpip模型.png)

## IP -- Internet Protocol

### Design requirements

 accommodate differences in constituting networks

- Different addressing schemes:
  - **using a global address**—IP地址 -> 虚拟逻辑地址
- Different maximum packet size -> **分片-重装**(Fragmentation and Re-assembly
- Different network access mechanism
- Different timeouts
- Different transmission modes (connection-oriented,connectionless)
- Error control
- Flow control

### 特点

- The most-widely used Internetworking protocol
- A connectionless network-layer protocol.
- Based on datagram routing. 
- IP provides best-effort service, unreliable !!
- Routing in IP is a mixture of hierarchical, distance vector and link state routing algorithms.

## Packet format

#### IP header -- *会考*

![image-20250512085139708](C:\Users\郭学琦\AppData\Roaming\Typora\typora-user-images\image-20250512085139708.png)

##### 第一行

- ==IHL*4== 表示header占的字节数,  IHL 有4位, 故整个header的字节数位20-60
- Total Length -> 包含header与data的全部长度, 单位为字节

##### 第二行

- Identification(16 bits): 如果收到的两个片的Id号相同, 说明是同一个包
- NU: 未定义
- DF -> Don't Fragment -- 不准分片

- MF -> More Fragment -- 标记该包是不是最后一个包, 0是最后一个, 1不是
- Fragment offset -> ==要*8==表示该片距离整个数据包头部的偏移量, 接收方根据该值重新组装各片. 偏移量一定是8的倍数

##### 第三行

- TTL -> 包在网络中的生存时间
- Protocol field(8bits) -> 说明上层协议是什么

## IP Addressing -- IP 地址

演化过程: 分类 -> 无类

### IPv4 地址

==点分十进制== 

### Classful IP Addressing -- 分类地址

- A类网
- B类网
- C类网

![image-20250516135248658](E:\mywork\mindgraghs\main_\大二下\image-20250516135248658.png)

### Network address

保留网络号部分，上下的主机号为0

==IPv4表示为点分十进制, 后来表示为前缀表示法==

可以通过**IP地址与掩码与一下**得到 -- 掩码（default mask）

![image-20250516135958147](E:\mywork\mindgraghs\main_\image-20250516135958147.png)

### 特殊的IP地址

- 全1，即255.255.255.255 -> 表示*本网本主机*，只能用作源地址

- **主机号**全1，广播地址

  ![image-20250516140200873](E:\mywork\mindgraghs\main_\image-20250516140200873.png)

### Subnet -- 子网

将主机号拿出几位分几个子网

#### Subnet Mask -- 子网掩码

网络号＋子网号设为1, 主机号为0 为子网掩码，得到子网的网络号同样是IP地址与子网掩码与一下

![image-20250516141049491](E:\mywork\mindgraghs\main_\image-20250516141049491.png)

### Supernet -- 超网

将连续的多个C类网连在一起组成一个大网

指明网络号的长度。

![image-20250516142445092](E:\mywork\mindgraghs\main_\image-20250516142445092.png)

### Classless Address -- 无类别地址

#### CIDR(Classless Inter Domain Routing) -- 无类别区间选路

特点:

- 网络可以任意大
- 地址表示为前缀表示 -- 不同长度的网络号能够更灵活分配网络号

注意==块与块之间不能有重叠，可以有空隙==

##### 路由聚合

将多个网络号相同的位置取出作为这几个王共同的网络号

但是这样导致**地址空间被放大**

**解决**

==最长匹配原则==

如果一个网络号可以匹配路由表中的多项，选择**最长的网络号**，因为它更详细

### Routing Table -- 路由表

一个数组，元素为 -- IP地址、网络掩码、outgoing line、下一跳

#### 路由方法

- 网络定义路由 -- 地址前缀小于等于31，只说明去哪一个网络
- 目的主机路由 -- 地址的前缀为32，明确主机是谁
- Default routing -- 默认路由 -> 路由表不会记录下所有网络的网络号。只记录自己需要的，剩下的全部发送到default 路由。default号为0.0.0.0，这样所有的网络号均能匹配上

交付方式：

- 直接投递 -- 通信双方在同一个网络内
- 间接投递 -- 不同网内的主机相互通信，彼此的下一跳都是路由器

### NAT: Network Address Translation

问题: IP地址太少了

解决办法:

==使用私有IP地址==

- 10.0.0.0
- 172.16.0.0
- 192.168.0.0

**NAT技术可以将私网地址转换为公网地址转发**

##### 出包

NAT转换公网IP与私网IP

##### 入包

记录端口号(传输层)

![image-20250519092602929](E:\mywork\mindgraghs\main_\image-20250519092602929.png)

---

## IPv6

