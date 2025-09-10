
## Elementary Data Link Protocols
### Protocol 1: A Utopian Simplex
assumptions:
- channel is simplex
- error-free
- receiver has unlimited buffers
-> need no error control and flow control
### Protocol2: A Simplex Stop-and-Wait Protocol for an Error-Free channel
> [! 假设]
> - channel is simplex
> - error-free
> - receiver has limited buffers

-> need no error control, but flow control
#### flow control method -- *stop-and-wait*
1. 发送方发数据包, 等待
2. 接收方发送简短的ACK帧
3. 发送方收到ack后,发送下一帧
#### Problems
##### 帧损坏
-> CRC校验未通过. 接收方直接将损坏帧丢弃, 发送方timer超时重发
##### 帧丢失
- 数据帧丢失. 发送方timer超时重传
- ack帧丢失. 发送方timer超时重传, 此时接收方收到==两个相同的帧==
###### ack丢失导致收到相同帧的解决办法
**数据帧和ack帧的帧头都添加序号(sequence number)**
只需要1bit的序号即可
##### ARQ(auto repeat request): 自动请求重传
增加了NAK, 在收到错误的帧之后接收方可以发送NAK来加速重传
![[Pasted image 20250403103102.png]]

### Protocol3: A Simplex Protocol for a Noisy channel
>[! 假设]
>- channel is simplex
>- unreliable
>- limited buffers

enhance的点:
- 帧的序号
- 计时器与重传机制
#### Sender

## Sliding Window Protocols
==双工通道(Full-duplex)==使用的流控制协议. 此时接受和发送可以同时进行
### Piggybacking(捎带应答/确认)
### Protocol 4: Sliding Windows of size 1
