## Users of Bridges
### 为什么要互连多个 LAN?
- 局域网之间需要交流
- LAN有物理范围限制
- Split a LAN into separate LANs to accommodate the load (multiple collision domains) -> 将 LAN 拆分为多个单独的 LAN 以适应负载（多个冲突域）
- Reliability
- Security
### Bridge --网桥
Repeater是一个物理层的设备, 单纯转发比特
Bridge属于数据链路层 
#### 功能
Bridges are used to interconnect LANs at data link layer
![[Pasted image 20250418053013.png]]
- 实现不同帧格式的转换
- 速率切换
- 不同帧长度的转换
- 安全性保证
#### 缺点
- 延迟 -> 因为会做CRC校验, 工作模式是先收存再转发
- Broadcast storm -> 遇到FFFFF地址的帧会转发到所有的接口
## Learning Bridges
### Ralated algorithms of Bridge
- ==Backward learning(后向学习)==
- Spanning tree(生成树)
#### Learning Bridges(学习网桥)
**动作:**
- forward
- discard
- flooding
**学习过程:**
- 初始的Station Table是一张空表
- 桥根据收到的帧判断来源并更新表. -> 例: A发了一个帧从桥的1口进入, 桥会记录A在1口

> [! ] Switch -- 交换机

#### Spanning Tree

## Summary of connection devices
#### 互联设备
![[Pasted image 20250418061218.png]]
![[Pasted image 20250418061246.png]]
## Virtual LANs
