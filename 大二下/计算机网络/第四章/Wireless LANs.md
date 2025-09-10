## 组织方式
- AP
- Ad hoc
## IEEE802.11
### Mutiple Access -- 如何避免冲突?
- PCF
- DCF
### Modes of operation
### CSMA/CA
#### Channel sensing
### Reliability
### Saving Power
#### Beacon frames
- Clients can enter Power-Save mode -- 省电模式
- AP 会缓存发送给进入省电模式的客户端的信息
- 客户端在每一个信标帧时苏醒, 并检查是否有数据在
- 如果有信息, 客户端向AP请求数据
- AP发送缓存的数据
#### APSD
- Client 可以进入Power-Save模式
- AP缓存
- Client有数据发送时, 发送完数据后, AP会将缓存的数据发送给Client

