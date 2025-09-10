#Java #惠集宝

北邮[[Java课]]
[[Java语言程序设计]]
## Java语法基础
*类似于C的部分省略*
- main方法放在类里作为程序运行的开始
- Java并不像C一样把0当作false, 非零当作true. 而是用专用Boolean类型储存.
- 通过创建Scanner对象来实现输入, 用完记得关掉, 凡是I/O流如果不关闭就会一直占用资源
- instanceof()函数用来判断一个对象是否是是某个类的实例.
- switch可以简化相同条目,且有返回值.
### Java接口
接口是Java的一个抽象类型，是抽象方法的集合，接口常以interface来声明。
**一个类通过继承接口的方式，从而来继承接口的抽象方法**
*接口是纯抽象类*：
- 接口包含类要实现的方法, 默认都是抽象方法
- 接口本身不实现方法
- 可以包含基本数据类型的数据成员，但它们都默认为static和final
- 不能用new运算符直接产生接口对象
利用接口设计类的过程，称为接口的实现，使用implements关键字，语法如下：
```Java
public class 类名称 implements 接口名称 {

        //在类体中实现接口的方法

        //本类声明的更多变量和方法

		//必须实现接口所有的方法

}
```
类实现接口的过程相当于把接口当作父类, 父类的引用就可以指向子类的对象
**不同的类实现接口的方法时可能不同, 也就是@Override**, 但实际上接口只是定义了方法, 并没有实现, 所以子类中必须要实现相应方法.
[D:\Program Files (x86)\Tencent\QQ]
### 常用的类：

> [!NOTE] 边学边记类型
> 常用类随时补充, 或者说属于学习记录. 最开始接触相关类时进行记录强化记忆用.
#### Scanner
用于从*输入流*提取数据
Scanner sc = new Scanner(System.in);
**方法：**
- next()->用来读取下一个"标记",即空白符分隔的字符串(空白符包含),**读取的内容是String**
- nextLine()->用来读取整行字符串
- nextInt()->用来读取一个整数
- nextFloat()->用来读取下一个浮点数
- **hasNext()->用来判断是否有下一个输入**
- close()->关闭输入流
#### String类
String类表示***不可变***的字符序列
**方法:**
- length()
- cahrAt(int Index)->用于获取指定位置的字符,参数为位置信息
- substring(int begin, int end)->截取字符串
- indexOf(String str)->返回字符串首次出现的位置
- **equals(Object another)** 和 **equalsIgnoreCase(String another)**->分别区分或不区分大小写地比较两个字符串, 例如 `s1.equals(s2) == True;`
- toUppeCase() 和 toLowerCase()->将字符串转换为大写/小写
- trim()->去除首尾空白
#### StringBuffer 和 StringBuilder 类
StringBuffer 和 StringBuilder类都是用来对String类进行修改的.
StringBUffer 和 StringBUilder创建的对象能够被多次修改且不产生新的未使用对象.
>StringBuilder 相较于 StringBuffer 更快,但是StringBuilder不是线程安全的.

使用实例:
```Java fold title:StringBuilderDemo
public class Demo {
	public static void maim(String[] args) {
	StringBuilder sb = new StringBuilder(10);
        sb.append("Runoob..");
        System.out.println(sb);  //Runoob..
        sb.append("!");
        System.out.println(sb);  //Runoob..!
        sb.insert(8, "Java");
        System.out.println(sb);  //Runoob..Java!(自动将长度字符串长度增长了)
        sb.delete(5,8);
        System.out.println(sb);  //RunooJava!
	}
}
```

**方法**
- append(String s)->将参数字符串追加到对象末尾
- reverse()->将字符串用其反转形式取代
- delete(int start, int end)->将从start到end的子字符串删除
- insert(int offset, int/String ob)->将给定的参数插入offset位置
- replace(int start, int end, String str)->将从start到end的字符串替换为给定字符串参数
- capacity()->返回当前容量
- chatAt(int index)->返回index处的char值
- getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)->将字符从此序列复制到目标字符数组dst的指定位置
- indexOf(String str)->返回第一次出现参数字符串的位置
- length()->返回字符串长度
- setCharAt(int index, char ch)->将index位置的字符设置为ch
- toString()->返回String类型的字符串




#### 包机制
为了更好的管理和组织类，Java有了包机制。
- 包的本质是文件夹
- 一般用公司名字倒写作为包名，例如百度以com.baidu.www做包名
- 用import导入需要的包，* 是通配符，会导入这个包下所有的类
javadoc参数信息
> @author
> @version
> @since(最早使用的jdk版本号)
> @param(参数名)
> @return
> @throws(异常抛出情况)

#### 语法篇结束任务
来几道简单题用Java完成
- [x] 计算阶乘->定义一个方法`factorial(int n)`求出n的阶乘,用Scanner输入整数;
- [x] 判断素数->编写一个方法 `isPrime(int n)`，判断一个数是否为质数
- [x] 字符串反转->编写一个方法接收一个字符串，然后反转并返回反转后的字符串。要求分别用 String 的 charAt() 循环和 StringBuilder 的 reverse() 方法实现。
- [ ] 数组排序->可尝试使用多种排序方法
- [ ] 使用 ArrayList 处理数据->实现增加、删除、查找和遍历集合中元素的操作。使用 Iterator 或增强 for 循环遍历 ArrayList 并打印每个元素。
- [ ] 计算斐波那契数列->编写一个递归方法 `fibonacci(int n)` 返回第 n 个斐波那契数。可扩展：实现非递归版本，使用循环或数组存储中间值以提高性能。
### 注意点
- 无法从static方法中引用非static方法
## JDK
- Java development kit

**JDK包含JRE**、**JRE包含JVM**
### JRE
- Java runtime environment
#### JVM
- Java virtual machine
**Java跨平台的核心**，所有的机器运行Java代码都在JVM虚拟机上。*一次编译，到处运行*

### IDEA
- psvm = public static void main(String[] args){}
- sout = System.out.println("");

## Java常用类库
- [ ] 抽空学吧
### Math
### Random



