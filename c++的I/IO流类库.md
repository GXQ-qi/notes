程序与文件交互信息时, 存在两个对象- 程序对象 - 文件对象
- 抽象流基类 - IOS - 所有输入输出流类的基类
- 输入流类 - istream -
- 输出流类 - ostream - 
- 输入输出流类 - iostream, fstream - 

## cout
### 单一i控制
#### 输出宽度控制
- cout>>setw(width)
- cout.width()
两种方法都只有一次有效, 字符放最后
#### 填充字符
如果设置宽度大于字符数,默认填充空格, 但可以自己设置.**设置后一直有效**
方法:
- cout<<setfill('+')
- cout.fill('\*')
#### 输出精度(其实是有效值?)
方法:
- cout<<setprecision()
- cout.precision()
设置一次后一直有效直到下一次精度改变, 默认精度是6

### 组合控制
