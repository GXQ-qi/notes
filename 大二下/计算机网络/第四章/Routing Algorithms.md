### Overview
#### Responsibility
#### How to evaluate?
#### Classification
- 非自适应的算法
- 自适应的算法
## Optimality principle
### 最优化原则
最优路线上任意两点之间的路径也是最优的
### Sink Tree -- 宿树/汇集树

网络最小生成树
![[Pasted image 20250421091123.png]]

## Dijkstra’s “Shortest Path” Algorithm

![[Pasted image 20250421091326.png]]
## Flooding

### Ideas
- 无需路由表
- 收到的包转发到其他的所有接口
- 会有多个copied的包到达目的地
### Problem and solutions
#### 问题
会受到很多重复的包
#### 解决
- 头包含一个跳计数器, 跳数太大直接丢弃
- 每个包添加一个序列号,,,
### Properties
- 包一定会到达
- 所有节点都能被访问
- 至少有一个包走的是最短路径
## Distance Vector Routing -- DVR(距离矢量选路)
### Ideas
- based on Bellman-Ford algorithm
- 每一个路由器都有一个距离矢量表
- 每个路由器周期性的跟邻居广播自己的路由表. -> 每个路由器都能收到来自所有邻居的表, 然后按照这张表更新自己的表

## Link State Routing (LSR)
## Hierarchical Routing