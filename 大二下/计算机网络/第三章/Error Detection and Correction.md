## Error Control
- 接收方反馈ACK/NAK
- 发送方设置timer, 时间过长默认发送失败 -> 以防止整个帧丢失或返回的反馈丢失
### Error Detection
- Parity check: 校验位与数据bit异或后得零为偶校验, 否则为奇校验
- CRC(Cyclic Redundacy Check): 检测突发错误
##### 应对突发错误
##### Parity Check
###### Parity Check for Blocks(interleaving)
应对突发干扰的奇偶校验
![[Pasted image 20250321135600.png]]
##### Polynomial Code(多项式编码)
**CRC**
> [! ] 校验码位数
> 校验码的位数(被除数补零的位数)是生成式的最高位, 不是生成式的位数, 余数最后也是添上0成为r位

![[CRC计算.png]]
###### CRC的纠错能力

### Error correction
- FEC(Forward Error Correction, 向前纠错)
- ARQ(Automatic Repeat reQuest)发现错误直接要求重新发送
#### Error-Correcting Codes(纠错码)
基本思路: 将冗余信息加入到发送的信息中
基本术语:
- Block code(块编码): 
- Systematic code(系统码): 先发m位数据, 再发r位校验
- Line code(线性码)
- Codeword(码字): n = m+r
- code rate: 码率 m/n
方法码：
- FEC: Hamming code
- ARQ: error detection + retransmission
- *HEC: 混合纠错*
##### Hamming Distance
- 检错k位: 需要任意两个码字的海明距离为 k+1
- 纠错k位: 需要任意两个码字的海明距离为 2k+1
#### The Number of Check Bits
**对于mbits的数据，插入多长的检测bits更合适？**
![[Pasted image 20250321131906.png]]
##### 一比特纠错
![[单比特纠错公式.png]]
###### Hamming Code -- 纠错码
- check bits r的位置为2的幂次, 
- 偶校验：带上校验位与他们对应的bit位相异或得到零为偶校验
- ![[汉明码举例.png]]
- 如何纠错?看下图![[汉明码纠错举例.png]]
