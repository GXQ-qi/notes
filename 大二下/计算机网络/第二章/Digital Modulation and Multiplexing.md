--数字调制与复用--
信道通常被多个信号共享，称为多路复用。
![[28119285f63e8bdca9e2cd5c5630b77.png]]
- 信源编码/译码器
- 信道编码/译码器
- 调制/解调器

### Baseband transmission
#### 信道编码(线路编码)
- Non-Return to Zero(NRZ)：正电压表示1, 负电压表示0
- Manchester->自带时钟(检测到跳变就是一个时钟)
- Bipolar encoding(AMI码)->正负电压交替表示1,零电压表示0
#### 编码评价指标
##### Clock Recovery时钟可恢复
接收方的时钟周期要和发射放的时钟周期要保持一致,才能正确解析信号
**方法**
- 在信号中混合时钟->Manchester码
- 发送额外的时钟信号给接收方,两条信道->不好
##### Bandwidth Efficiency


##### Balanced Signals
平均电压是0称为平衡信号,可以避免出现直流. 
### Passband transmission---Modulation
Place a signal in a given frequency band.数字信号->模拟信号 以便于信号在信道上传输
device: Modem->调制/解调器
#### 技术
ASK, FSK, PSK, QPSK, *QAM(混合调制)*
#### 星座图
查看QAM的阶数
- 极限也要遵循香农公式 -> 带宽\信噪比 影响
### Digital Analog Signals---Source Coding
- 将信源的模拟信号转换为数字信号
#### Procedures
##### Sample(采样)
Nyquist theorem: 用最高频率的二倍采样, 可以保证不失真
##### Quantizing(量化)
将采样值转换为距离最近的量化值(规定好的编码值)
##### Encoding
数字化语音信号(PCM)

## Multiplexing(复用)
![[Pasted image 20250314132356.png]]
### TDM(时分复用)
#### 同步时分复用
不同的信号轮流使用信道.
将一个时间段分为多个时隙.
数字信号多用这种方法
- 若分配了时隙但是用户不发数据?
#### 异步时分复用
加冗余信号表明信号是谁的, 如果不发数据, 则不分资源
### FDM(频分复用)
使用调制技术, 将不同信号调到不同波段.
选择合适的载波, 
接收方通过带通滤波器将不同波段信号分开.
![[Pasted image 20250314131529.png]]
模拟信号多用
### CDM(码分复用)
在时间合频率上都公用, 但是编码不同. 接收方能解码则收到信息,
