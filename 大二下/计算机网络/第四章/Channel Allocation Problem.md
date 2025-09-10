#MACSublayer #计算机网络
### Random multiple access
- ALOHA
- CSMA
### Controlled multiple access -- 受控分配
- centralized: polling(轮询) -> 通过发命令询问有没有问题, 没有被询问到不能接入信道                                ![[轮询分配方法.png]]
- decentralized: token(令牌) -> 令牌是特殊的*控制信息* -> 令牌在令牌环上转动, 拿到令牌的机器可以发送数据, 令牌用完就放回环中![[令牌分配.png]]
## Assumptions of Dynamic Allocation --(动态信道分配)
#### 情景假设
1. Independent Traffic: independent and single user system
2. Single channel
3. Observable Collisions
4. Time assumption: - Continuous time(连续时间) - Slotted time(分时隙)
5. Carrier sense assumption: - Carrier sense - No carrier sense
# 4.2 Multiple Access Protocols -- MAC
## ALOHA
### Pure ALOHA
#### Basic idea
- 想发就发, 不在意同时刻下是否有人正在发送
- 如果收到要发送ACK
- 收不到就重传
### Performance Analysis
效率很低
![[Pasted image 20250331091719.png]]
2t的脆弱期 -- t 是一帧的发送时延
### Slotted ALOHA(时隙/分槽ALOHA)
将信道分为不同的时隙, 只有在时隙的开始才能够发送数据,否则不可以传输
![[Pasted image 20250331092346.png]]
#### 效率
![[Pasted image 20250331092307.png]]
脆弱期是t
## Carrier Sense Multiple Access Protocols==(CSMA)== -- 载波监听多路访问
### Basic Idea
通过监听信道有无信号确定是否能发送 -- 发前监听
但是要求Propagation delay 远小于 Transmission delay
- 如果信道空闲, 一定概率(设定值p)下发送
- 若信道占线, 等待
- 等待ACK, 若没收到说明冲突了, 重发
### 效率
#### Vulnerable Period
只要一方发送的信号占据了信道, 其他方就不会发送.
但是若信号发送出去还没有占据整个信道, 另一方检测到信道为空并发送了信号, 二者冲突
这种情况下, 脆弱期为信号**端到端的传播时延**(Propagation delay) -- τ
效率提高很多
### Nonpersistant & Persistent CSMA
- 非坚持: 信道忙时, 等待一个==随机时间==重新监听
- 坚持: 信道忙时, 一直等待直到信道空闲 -> - 1-persistent: 信道空闲直接发送; 2-persistent: 随机概率p下发送帧
![[坚持与非坚持CSMA.png]]
### CSMA/CD (Collision Detection) -- 带冲突检测的载波监听多点接入
#### Basic idea
- 载波监听 -- 继承的功能
- Collision detection -- 冲突检测: 发送方检测自己再发送的过程中是否有冲突信号, 若检测到, 立即停下, 然后发送一个jam信号
- backoff -- 退避: 发送jam后, 等待一个random时间重新发送

> [! 无确认的无连接服务]
> 因为以太网的信道是可靠的, 帧发送失败大概率是冲突造成的, 由于发送方自己检测是否有冲突, 所以不需要接收方返回ack

- 如何检测? -> 边发边收, 若发送出去的信号与收到的信号一样; 到要求接收的信号功率要足够高, 信号编码要能区分叠加态(无线通信用不了)
- 接收时间? -> ==2τ时间==内没有冲突, 说明发送方已经占据整个信道
- 重传等待时间? -> Binary Exponential Backoff Algorithm ![[二进制指数退避.png]]
- 
## 总结

> [! 评价MAC协议的指标]
> - **低负载**下的**时延**
> - **高负载**下的**吞吐量**

![[Pasted image 20250407083534.png]]
![[Pasted image 20250407090351.png]]
## Wireless LAN Protocols -- WLAN
> [! 无线局域网面临的的问题]
> - 广播发送有固定的通信范围
> - 发送方收到的自己的信号与自己发送的信号相差一百万倍, 发送方在发送过程中实际上接收不到任何其他信号
> - 多个发送方与接收方产生的问题: 隐藏终端问题\暴露终端问题

### MACA -- Mutiple Access with Collision Aviodance
##### 定义四个帧
- RTS -> Request to Send
- CTS -> Clear to Send
- 发送方收到CTA, 发送data帧
- ACK
![[Pasted image 20250411131038.png]]
### LAN
#### feature
- Limited number of stations and range
- Higher data rate
- Lower error rate
- Supporting broadcasting and multicasting
- Single administration
![[Pasted image 20250407092820.png]]
