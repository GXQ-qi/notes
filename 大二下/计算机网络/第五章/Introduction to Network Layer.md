![[Pasted image 20250418142534.png]]
### Network Duties
- Internetworking(网络互连) ->
- Addressing(编址) -> 
- Routing(路由) -> 
- Packetizing(组包) -> 
- Fragmenting(分片) -> 
- QoS -> 
### Network Design Goal
- The services should be independent of the router technology. 
- The transport layer should be shielded from the number, type, and topology of the routers present
- The network addresses made available to the transport layer should use a uniform(统一)numbering plan, even across LANs and WANs
#### 向上层提供的服务
- 面向连接的 -> 虚电路 -- Virtual circuit
- 无连接的 -> 数据报 -- datagram
 ![[Pasted image 20250421083421.png]]
#### Datagram Network
==无连接的==
![[Pasted image 20250421083928.png]]
#### Virtual Circuit Network
==面向连接的==
- 先发一个连接请求,记录下来走过的路径, VC
- 接下来发送的包用的地址不再是目的地址, 换成VC
- 数据传输完后, 释放VC
![[Pasted image 20250421084415.png]]

