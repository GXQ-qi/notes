### DataLink Types
- PTP links -> Protocols: HDLC \ PPP
- Broadcast links: Protocols: ALOHA \ CSMA/CD
# PTP
## HDLC: 
面向连接的\可靠的通信
支持: GoBackN ARQ \
### 面向比特的协议
bit stuffing 使用零比特填充方法
### Frame Type
- information: 信息帧
- supervisory: 监督帧
- unnumbered: 无序号帧-不要求
### Station Types
![[Pasted image 20250331083628.png]]
可以支持点到点和多点通信
#### Primary Station
发送控制
Frame issues 称为 command
#### Secondary Station
接受主站控制
Frame issues 称为 response
#### Combined Station
混合站
## PPP
- 只支持点到点
- 字节填充
- 更简单
- 无连接的无确认服务
### What are enhanced
- Working with numerous network layer protocols
- Negotiation of connections（dynamic IP address）
- User authentication (身份认证)
- Negotiation of data compression
- Physical layer can be asynchronous or synchronous
### What are removed
- Error correction -> 无纠错但是有CRC检错
- Flow control
- Sequence number
![[Pasted image 20250331084741.png]]
![[Pasted image 20250331084909.png]]
# Broadcast
...