
## 协议层次架构--protocol Hierarchies
**分层设计: Networks are organized by stack of layers**
*Network architecture->A set of layers and protocol*
Why?
- reduce design complexity->每一层都是再底层架构起来的
- 每一层网络都只提供与上层的特定服务,而避免让上层解析packet的具体封装信息
- 对等层靠协议(protocol)来保证可以相互通信
- **上下相邻层存在接口,下层为相邻上层提供服务**,上层对下层传输数据
- **只有最底层才是通过实际介质来通信的**,数据从上往下走,用户端(主机)处于最上层,上两层叫做虚拟通信.
##### 一般分五层:
![[Pasted image 20250228142140.png]]
![[Pasted image 20250228142429.png]]
*数据流是U型结构传输*
每向下一层,数据封装本层的信息--head--,跟本层的协议相关, 只有最后一层不加头和尾, 如果要分片, 在第三层分, 第二层会加尾.
![[Pasted image 20250228143539.png]]

>数据的传输效率是最开始传输的数据大小除以最底层传输的数据大小
---
### Virtual Communication of 5 Layers
- Layer 5 -> A message ,M, is produced by an application process and given to layer 4 for transmission


## Design Issue for the Layers
## Service
Services: Connection-oriented(面向连接的服务, 下层对紧邻的上层) and Connectionless.
connection: 两个客户端附带资源的链路叫连接(connection)
**面向连接的服务都包括three phrase**:
- connection establishment: negotiation(发送请求,询问是否能连接,如果能,能给多大资源->带宽)
- data transmission(ordered, 有顺序的传输包, 因为路径已经确定了)->只需要第一个包带上目的ID, 后面的包只需要连接符即可
- connection release
**无连接的服务**: 只有数据传输阶段(垃圾电子邮件, 不请求是否连接, 直接发送数据, 所有的包都需要带上目的ID)->不一定有顺序, 但是更快

> [!可靠与否]
> 面向连接的服务可靠性比无连接的更好, 但并不是完全可靠.
> 可靠与否是看协议有没有纠错功能, 与是否连接无关

![[Pasted image 20250303084251.png]]
### Reliability
- Error detection and error correction(检错纠错)
- Routing: ot find a path through a network(选择路由)
### Network evolution
- Protocol layering: 隐藏封装细节和问题
- Addressing or naming: identifying sender and receivers
- Internetworking
- Scalability
### Resource allocation
- Statistical multiplexing(统计复用: 按需分配)
- Flow Control
## Service Primitives(服务原语): Interfaces and services
上下层通过原语相互交流
### SAP: Service Access Point
n 层的服务访问点(SAP)是为n+1层提供服务的接口,上一层可以通过该服务访问点访问下一层的服务.
## 协议与服务的关系
**服务是指某一层向他的上一层提供的一组原语(操作)**
Protocol: 
- 语法: 协议的消息格式
- 语义: 消息字段区某个值的含义
- 同步:事件发生的顺序




