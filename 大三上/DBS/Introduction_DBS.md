数据库完成对**文件系统**的补充
- 基础操作 -- 增删查改
- 一致性保证
- 并发
- 安全性 -- 日志
- 数据库系统如下 -- DBMS 管理数据库，为前端应用提供服务接口
	![[Pasted image 20250908141307.png]]
	![[Pasted image 20250908141643.png]]
---
DBMS is a software system that manages, stores, and retrieves data efficiently in a structured format.

- It allows users to create, update, and query databases efficiently.
- Ensures data integrity, consistency, and security across multiple users and applications.
- Reduces data redundancy(冗余) and inconsistency(不一致) through centralized control.
- Supports concurrent data access, transaction management, and automatic backups
---
DBMS 组成
1. Hardware
2. Software
3. Data
4. Procedures
5. Database Access Language
6. People
DBMS分类
- RDBMS -- 关系型
- NoSQL DBMS -- 非关系型
- OODBMS -- Object-Oriented DBMS 面向对象
- Hierarchical Database -- 树状 
- Network Database -- 网状
- Cloud-Based Database -- 云
---

DBMS 内部的三级模式
1. 物理模式 -- 物理上怎么存储数据
2. 逻辑模式 -- 数据之间的关系信息
3. 视图模式 -- **外模式** 有多个外模式

Mappings（映像） -- 两级映像
physical || logical
logical || view

物理数据独立性 -> 当物理数据发生改变时，逻辑层和试图层不需要做出改变
- 关系型数据库的 物理数据独立性 是完备的
逻辑结构独立性 -> 当逻辑结构发生改变时，视图层的应用可以不变（不完备的）

---
Instances and Schemas（模式）
类似于 类与对象。模式提供一个静态的框架，是数据库中数据组织结构的描述
实例是数据库的快照，是数据库在特定时刻包含的实际数据。

Data Models
在数据库系统中，**Data Model（数据模型）** 是一种 **抽象方法或框架**，用来描述、表示和组织数据，以及数据之间的关系和操作方式。它是数据库设计的核心概念，相当于“数据库的语言和规则”。

**数据模型的三个核心要素**
1. **数据结构（Data Structure）**
    
    - 描述数据的组织形式（比如表、树、图）。
        
    - 决定了数据如何存储和表现。
        
2. **数据操作（Data Operations）**
    
    - 定义了对数据可以进行的操作（查询、插入、删除、更新）。
        
3. **完整性约束（Data Constraints）**
    
    - 确保数据正确性和一致性（比如主键唯一、外键约束）。

Database Languages
DDL -- 数据定义语言 -> 创建表格、定义模式等
DML -- 数据操作语言 -> 增删查改
DCL -- 数据控制语言 -> 安全性相关、完整性约束相关等