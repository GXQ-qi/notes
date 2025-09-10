### 设置数据链路层的原因
0. 向网络层提供一个定义良好的接口
1. Error Control: 解决相邻两点之间传输可靠性与高效性问题 -> 只有一条信道, 无其它设备. -> 可能出现传输误码\丢失..., 数据链路层查错纠错
2. Flow Control: 防止接收方收到超过处理能力的数据 -> 超过接收方CPU处理能力且内存满时, 接收方会直接丢掉多出的信息.
3. Broadcast channel: addressing, media access control(介质访问控制)
## Position and Functions
![[数据链路层示意图.png]]
### Functions
**数据链路层从网络层获得数据包，然后将这些数据包装（encapsulation）成帧（frame）**
每个帧包含一个帧头、一个有效载荷（数据包）以及一个帧尾
![[数据链路层功能示意图.png]]
整体功能: 
- Error Control: Dealing with transmission errors -> [[Error Detection and Correction]]
- Flow Control: Slow receivers not swamped by fast senders -> [[Flow control]]
- Framing -> [[Framing]]

#### Encapsulation(封装)
发送方将收到的Frame(帧)去掉头和尾, 接收方将受到的Packet封装成Frame
![[封装成帧示意图.png]]
#### hop-to-hop communication
![[数据链路层逐跳通信.png]]
#### Adapters Communication
##### Sending Side
- encapsulates network packet in a frame
- adds error checking bits, reliable transfer, flow control
##### Receiving Side
- looks for errors, reliable transfer, flow control
- extract packet, passes to receiving node
##### adapter--网卡
![[网卡.png]]
## Services
#### Connectionless services -- 无连接服务
##### unacknowledged -- 无确认的
- no ack, no logic connection
- Most LANs use such services
##### acknowledged -- 有确认的
接收方发送Ack/Nak给接收方来告知是否正确收到发送方的内容
#### connection-oriented service -- 面向连接的服务
##### 有确认的
A connection established, frames are numbered,
reliable transmission guaranteed
eg. ATM