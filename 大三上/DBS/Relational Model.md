对于一个 Model，关注三个部分
- 数据的存储结构
- 数据的完整性约束
- 可以对数据执行什么操作
### Relational Data Structure
关系 -- 一系列**域**的**笛卡尔乘积**的**有限的有意义的子集**
每一个域称为一个属性
#### Relation Schema（模式）
按照关系模式组织的一张表或者多张表。
#### Relation Instance（实例）
关系模式的具体实例，实际的数据。

### key
#### primary key
##### 实体完整性约束 Integrity Constraint of Primary Key
主键的取值不能为空
- 若是**联合主键**，主键的所有属性的取值都不能为空
#### super key
没有重复值的
#### certification key（候选键）
#### foreign key
在一个关系模式 r1 中的某个属性包含另一个关系模式的主键
- 外键的值可以为空
- 外键的属性命名不一定要和对应主键的名称一致
- 外键可以定义在同一张表上。参照自己的主键定义的外键。
##### 参照完整性约束 Integrity Constraint of Reference
外键的取值不能同时为空或超出参照的主键的取值。
或者说外键的取值可以为空或者取 参照的主键 中的某一个值，而不能取其他值。
## the Relational Algebra（关系代数）
关系代数与关系演算是完全等价的，是从不同角度定义出来的。
六种基本操作
- Select（选择）
- Project（投影）
- Union（并）
- set difference（差）
- Cartesian product
- Rename
### Select -- 找出满足条件的行
操作对象和结果都是关系。从一个关系选择另一个
σp(r) = {t | t ∈ r and p(t)}
p是定义的逻辑运算条件，用来找到用户期望寻找的 t 元素
### Project -- 得到想要的列
选择表中的某些属性组合成新的表作为投影。
投影之后如果没有选择主键，就可能导致有重复行，需要做 **去重**
### Union
r ∪ s
条件
- 属性个数相同
- 对应属性的取值域要相容

