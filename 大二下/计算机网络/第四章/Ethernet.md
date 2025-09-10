- 4.3.1 Classic Ethernet: Physical Layer
- 4.3.2 Classic Ethernet: MAC Sublayer Protocol
- 4.3.3 Ethernet Performance
- 4.3.4 Switched Ethernet
- 4.3.5 Fast Ethernet
- 4.3.6 Gigabit Ethernet
- 4.3.7 10G Ethernet
## Physical Topology
- BUS：总线型以太网，90年代
- Star：星型以太网 -> 1. Hub: 集线器, 收到信息后转发到所有的设备(广播式) -> Switch: 交换机, 以帧为单位, 能够处理地址信息(点对点式)
#### Hub
物理上星型,逻辑上总线型
最高一个段中三个集线器
##### 命名方式
![[Pasted image 20250411132025.png]]
#### Repeater
用于两个总线相连, 一般只有两个接口, 工作是将总线传输进来的信号增强转发到另一个总线上. 可以再生信号
**用于两个以太网网络互连**

#### NIC(Network Interface Cards) -- 网卡
Tasks of NIC:
- Establishes and manages the computer’s network connection
- Encoding: translates digital computer data into signals

### 传统以太网
![[Pasted image 20250411132447.png]]
## Protocol for MAC Sublayer
### IEEE 802.3
广播式链路
- 编址是首先要做的, 每个主机都有自己的地址, 如果收到的信息不是自己的, 在网卡上就会丢掉
- 
## 高速以太网
## Gigabit 以太网
#### 10Base5
总线型
线芯: 10mm, 双绞线, 500m

#### 10Base2-Thin
总线型
#### 10BaseT
使用Hub的星型
#### Flow control -- 流量控制
##### 问题
1 Gbps的速度太快. 如果receiver太忙, 导致延迟1ms,就会有接近2000个帧放到buffer, 时间长了很有可能导致buffer不堪重负
##### 解决
发送Pause Frame给sender
![[Pasted image 20250414081526.png]]
##### Pause Frame
One end sending a special control frame to the other end telling
it to pause for some period of time
u Normal Ethernet frames, containing a type of 0x8808
u Pauses are given in unites of the minimum frame time
u For Gigabit Ethernet：512ns~33.6ms


## 10G 以太网
### 应用场景
- 高速\本地大容量交换机连接(当初)
- 数据中心, 连接高端路由\交换机\服务器
- offices间长距离\高带宽的通道
### 设计特点
- 只有全双工
- **不支持CSMA/CD**也用不到, 仅使用**交换机**
- 