# Java se

### 0.开发细节

1. ##### 源文件为.java，基本组成是类；执行文件为.class，视为类，字节码文件
2. ##### Java程序执行入口是main（）方法，有固定的书写格式：

```java
public static void main(String []args) {}
```

3. ##### 每一条Java语句都以；结尾

4. ##### Java语言严格区分大小写

5. ##### 每对括号成对出现

6. ##### 每个源文件最多只能有一个 public 类，其他类不限，编译也会生成相应的.class文件，如dog.class, cat.class

```java
public class HelloWorld {
    public static void main(String []args) {
       System.out.println("Hello World!"); //ln代表换行，去掉就不换行
    }
}

class dog{}
class cat{}
```

7. ##### 如果源文件中有 public 类，则文件名为类名，如上面的源文件名为 HelloWorld.java

8. ##### 可以将 main（）方法写在非 public 类中，然后指定运行非 public 类，则程序入口为非 public 类中的main（）方法

```java
public class HelloWorld {
    public static void main(String []args) {
       System.out.println("Hello World!");
    }
}

class dog{
	public static void main(String []args) {
		System.out.println("Hello dog!");
	}
}
	
class cat{
	public static void main(String []args) {
		System.out.println("Hello cat!");
	}
}
```

9. ##### 运算符两边要加空格

   ```java
   int n1 = 1 + 2;
   ```

10. ##### tab 右移；shift+tab左移

11. ##### 行宽不超过80

12. 

### 1.转义字符

```java
public class changechar{
	public static void main(String[] args){
		//\t一个制表位，实现对齐功能
		System.out.println("-----------------\\t一个制表位，实现对齐功能--------------------");
		System.out.println("未使用制表位：你我他");
		System.out.println("使用制表位：\t你\t我\t他");
		//\n换行符
		System.out.println("-----------------\\n换行符--------------------");
		System.out.println("未使用换行符：你我他");
		System.out.println("使用换行符：\n你我他");
		//\\等于\,\"等于",\'等于'
		System.out.println("-----------------\\转义--------------------");
		System.out.println("将\\表示出来\n将\"表示出来\n将\'表示出来");
		//\r一个回车,把光标定义在该行最前方
		System.out.println("-----------------\\r回车--------------------");
		System.out.println("本来是这样的：你我\\r他");
		System.out.println("本来是这样的：你我\r他");
	}
}
```

输出

```
-----------------\t一个制表位，实现对齐功能--------------------
未使用制表位：你我他
使用制表位：    你      我      他
-----------------\n换行符--------------------
未使用换行符：你我他
使用换行符：
你我他
-----------------\转义--------------------
将\表示出来
将"表示出来
将'表示出来
-----------------\r回车--------------------
本来是这样的：你我\r他
他来是这样的：你我
```

### 2.注释

```java
//这是单行注释
/*这
  是
  多
  行
  注
  释*/
```

文档注释javadoc，生成一套网页文件，类和方法的注释也采用

```java
/**
 * @author baymax //注释1
 * @version 1.2 //注释2
 */
public class filecomment{
	public static void main(String[] args){
		System.out.println("文档注释,生成一套网页文件形式");
		System.out.println("用 javadoc -d 目标文件夹 -注释1 -注释2 源文件.java");
	}
}

```

输出

```
E:\java\javacode>javadoc -d E:\java\javacode\internetfile -author -version filecomment.java
正在加载源文件filecomment.java...
正在构造 Javadoc 信息...
标准 Doclet 版本 1.8.0_131
正在构建所有程序包和类的树...
正在生成E:\java\javacode\internetfile\filecomment.html...
正在生成E:\java\javacode\internetfile\package-frame.html...
正在生成E:\java\javacode\internetfile\package-summary.html...
正在生成E:\java\javacode\internetfile\package-tree.html...
正在生成E:\java\javacode\internetfile\constant-values.html...
正在构建所有程序包和类的索引...
正在生成E:\java\javacode\internetfile\overview-tree.html...
正在生成E:\java\javacode\internetfile\index-all.html...
正在生成E:\java\javacode\internetfile\deprecated-list.html...
正在构建所有类的索引...
正在生成E:\java\javacode\internetfile\allclasses-frame.html...
正在生成E:\java\javacode\internetfile\allclasses-noframe.html...
正在生成E:\java\javacode\internetfile\index.html...
正在生成E:\java\javacode\internetfile\help-doc.html...
```

在 E:\java\javacode\internetfile 下生成的文件

![1653880082(1)](C:\Users\Administrator\Desktop\1653880082(1).png)

### 3.DOS 命令

```
dir + 目录：查看目录下的内容               dir e:\java  
cd + 目录：切换到指定目录下（ 换盘须加/D）   cd /D c：
tree + 目录：展示指定目录下的子级结构       tree e:/好好看文献！
cls：清屏
exit：退出
md + 文件夹：创建目录
rd + 文件夹：删除目录
echo + 内容 + 文件：在指定文件里输入内容    echo 美女 > wlt.txt
del + 文件：删除指定文件                  del wlt.txt
type nul > 文件：创建文件                type nul > wlt.txt
copy + 文件 + 目录：把文件复制到指定目录    copy wlt.txt e:\gzc.txt
move + 文件 + 目录:把文件移到指定目录      move wlt.txt e:\wlt2.txt

```

### 4. 变量

变量=类型+变量名+值

##### 1. + 号的使用，两边都是数值时，加法作用；两边有一边为字符串时，拼接作用

```java
System.out.println(100 + 98);       //输出198
System.out.println("100" + 98);     //输出10098
```

##### 2. 整数型

```
byte[1]			-(2)^7~[(2)^7]-1      -128~127
short[2]	    -(2)^15~[(2)^15]-1    -32728~32727
int[4]	        -(2)^31~[(2)^31]-1    
long[8]         -(2)^63~[(2)^63]-1
```

一个字节 = 8个bit，java中整数常量默认为int，long 型末尾必须带上 l 或 L

##### 3. 浮点型

浮点数 = 符号位 + 指数位 + 尾数位

```
float[4]	    
double[8]
```

java中默认为 double 型，float 型末尾必须带上 f 或F，double 精度更高，末尾可带d

书写形式

```java
double n1 = 0.123
double n2 = .123
double n3 = 12.3e-2
```

浮点数的陷阱，2.7 = 8.1/3 ？

```java
public class floattrap{
	public static void main (String[] args){
		double n1 = 2.7;
		double n2 = 8.1/3;
		System.out.println("n1 = " + n1);
		System.out.println("n2 = " + n2);
	}
}
```

输出

```java
n1 = 2.7
n2 = 2.6999999999999997
//浮点数只能结近真实值
```

因此，对运算结果是小数的进行判断时，不要直接比较，取其差值的绝对值进行精度判断

```java
if(n1 == n2){
	System.out.println("n1和n2一样");
}
//不可取
if(Math.abs(n1 - n2) < 0.0000001){
	System.out.println("n1和n2相等");
}
//可取
```

##### 4. 字符型

单个字符（可汉字）为char，2个字节，用单引号；多个字符为string，双引号

```java
public class chartest{
	public static void main (String[] args){
		char c1 = 'w';
		char c2 = '文';
		char c3 = '\t';
		char c4 = 97;  
        char c5 = 'a'
		System.out.println(c1);
		System.out.println(c2);
		System.out.println(c3);
		System.out.println(c4);
        System.out.println((int)c5);
        System.out.println('a' + 10);
	}
}
```

输出

```
E:\java\javacode>javac chartest.java

E:\java\javacode>java chartest
w
文

a                    //说明字符可以存放数字，输出数字代表的符号
97                   //说明字符本质是数字，默认输出对应字符，可以输出数字
107
```

##### 5. 布尔类型

boolean，一个字节，true和false，不能用0或非0代表

```java
public class booleantest{
	public static void main(String[] args){
		boolean a = false;   //注意小写
		if (a) {
			System.out.println("这是true");
		} else{
			System.out.println("这是false");
		}
	}
}
```

输出

```
E:\java\javacode>java booleantest
这是false
```

##### 6. 数据类型变换

自动变换，按照精度（byte<short=char<int<long<float<double）

byte, short不与char发生自动转换，且三者进行运算时，结果会转换为int

boolean不参与转换

运算结果会转换为操作数中精度最高的类型

```java
public class autoconvert{
	public static void main(String[] args){
		int a = 'a';
		System.out.println(a);
		double b = 'a';
		System.out.println(b);

		byte n1 = 1;
		short n2 = 2;
		byte n3 = 3;
		int n4 = n1 + n2;
		System.out.println(n4);            //n4是int
		int n5 = n1 + n2;
		System.out.println(n5);            //n5是int

		int m1 = 1;
		float m2 = 2;
		double m3 = 3;
		double m4 = m1 + m2 + m3;
		System.out.println(m4);             //m4是double
	}
}
```

强制转换

（要转换的类型）待转换的数，只转换距离最近的数

char 可保存 int 常量，不可保存变量

```java
public class forceconvert{
	public static void main(String[] args){
		int a1 = (int)1.9;
		System.out.println(a1);
		byte a2 = (byte)2000;
		System.out.println(a2);
		int b1 = 100;
		char b2 = 100;
		char b3 = (char)b1;
		System.out.println(b1);
		System.out.println(b2);
		System.out.println(b3);
	}
}
```

输出

```
E:\java\javacode>java forceconvert
1              //精度降低
-48            //溢出
100
d
d
```

##### 7. 字符串String与基本类型的转换

基本类型转字符串

```
基本类型+“”
eg: String a1 = b1 + ""
```

字符串转基本类型：包装类(eg,Byte,Short,Integer,Long,首字母大写).parse类型(首字母大写)(string)

```
eg: int a2 = Intager.parseInt(a1)
```

注意，字符串转字符时类似于在数组里取一个数

```
eg: char a2 = a1.charAt(0)
```

```java
public class stringtobasic{
	public static void main(String[] args){
		//基本类型转字符串
		System.out.println("----------基本类型转字符串-----------");
		byte a1 = 99;
		short a2 = 958;
		int a3 = 520;
		long a4 = 942;
		float a5 = 13.14f;
		double a6 = 14.13;
		boolean a7 = true;
		String b1 = a1 + "";
		String b2 = a2 + "";
		String b3 = a3 + "";
		String b4 = a4 + "";
		String b5 = a5 + "";
		String b6 = a6 + "";
		String b7 = a7 + "";	
		System.out.println(b1 + " " + b2 + " " + b3 + " " + b4 + " " + b5 + " " + b6 + " " + b7);
		//字符串转基本类型
		System.out.println("----------字符串转基本类型-----------");
		byte c1 = Byte.parseByte(b1);
		short c2 = Short.parseShort(b1);
		int c3 = Integer.parseInt(b1);
		long c4 = Long.parseLong(b1);
		float c5 = Float.parseFloat(b1);
		double c6 = Double.parseDouble(b1);
		boolean c7 = Boolean.parseBoolean(b1);
		char c8 = b1.charAt(1);
		System.out.println(c1);
		System.out.println(c2);
		System.out.println(c3);
		System.out.println(c4);
		System.out.println(c5);
		System.out.println(c6);
		System.out.println(c7);
		System.out.println(c8);

	}
}
```

输出

```
E:\java\javacode>java stringtobasic
----------基本类型转字符串-----------
99 958 520 942 13.14 14.13 true
----------字符串转基本类型-----------
99
99
99
99
99.0
99.0
false
9
```

注意转换格式，例如字符串“hello”不能转整数

### 5. 运算符

##### 1. 算术运算符

+-*/, ++, --（分前后），%

```
a % b = a - a / b * b； 当a是小数：a % b = a - （int）a / b * b
eg: 10 % (-3) = 10 - 10 / (-3) *(-3) = 1

c = a ++    // temp = a, a = a + 1, c = temp
c = ++ a    // a = a + 1, temp = a, c = temp
```

```java
public class ArithmeticOperator{
	public static void main(String[] args){
		int i = 1;
		int l = 1;
		i = i ++;
		l = ++ l;
		System.out.println(i);
		System.out.println(l);

		//还有59天放寒假,合几个星期零几天
		int total = 59;
		int weeks = total / 7;
		int  days= total % 7;
		System.out.println("还有59天放寒假,合" + weeks + "个星期零" + days + "天"); 

		//华氏温度与摄氏温度的转换：摄氏温度=5/9(摄氏温度 - 100)
		double fahrenheit = 135.937;
		double celsius = 5.0 / 9.0 * (fahrenheit - 100);
		System.out.println("华氏温度" + fahrenheit + "对应于摄氏温度" + celsius);
	}
}
```

输出

```
E:\java\javacode>java ArithmeticOperator
1
2
还有59天放寒假,合8个星期零3天
华氏温度135.937对应于摄氏温度19.965000000000007
```

##### 2. 关系运算符

==，>, <, >=, <=， !=

结果都为boolean型，要么true，要么false

##### 3. 逻辑运算符

逻辑与&和短路与&&（主要用&&，效率高）

​			&：两个条件均要进行判断，都为true，结果才为true

​			&&：第一个条件为false时，不会判断第二个个条件，直接false

逻辑或|和短路或||

​			|：判断两个条件，只要有一个条件为true，结果为true

​			||：第一个条件为true时，不再判断第二个条件，结果直接为true

非！：真变假，假变真

逻辑异或 ^ ：两个条件不同为true，相同为false

```java
public class LogicOperator{
	public static void main(String[] args){
		//& 和 &&
		System.out.println("-----------&& 和 &-----------");
		int a1 = 1;
		int a2 = 1;
		if(a1++==2 & ++a2==2)
			a1++;
		System.out.println("&:a1 = " + a1 + "\ta2 = " + a2);
		a1 = a2 = 1;
		if(a1++==2 && ++a2==2)
			a1++;
		System.out.println("&&:a1 = " + a1 + "\ta2 = " + a2);
	

		//| 和||
		System.out.println("-----------|| 和 |-----------");
		int b1 = 1;
		int b2 = 1;
		if(b1++==1 | ++b2==1)
			b2++;
		System.out.println("|:b1 = " + b1 + "\tb2 = " + b2);
		b1 = b2 = 1;
		if(b1++==1 || ++b2==1)
			b2++;
		System.out.println("||:b1 = " + b1 + "\tb2 = " + b2);

		//test
		System.out.println("-----------test-----------");
		boolean c1 = true , c2 = false;
		int z = 1;
		if(z++==1 && (c2 = true))
			z++;
		if((c1 = false) || ++z==4)
			z++;
		System.out.println("z=" + z);

	}
}
```

输出

```
E:\java\javacode>java LogicOperator
-----------&& 和 &-----------
&:a1 = 2        a2 = 2
&&:a1 = 2       a2 = 1
-----------|| 和 |-----------
|:b1 = 2        b2 = 3
||:b1 = 2       b2 = 2
-----------test-----------
z=5
```

##### 4. 赋值运算符

=，+=，-=，*=，/=，%=

会自动进行类型转换

```
a += b 等价于 a = a + b
byte c = 1;
c += 3 //等价于 c = (byte)(c + 3)
```

##### 5. 三元运算符

条件表达式？表达式1：表达式2（真1假2）等价于if……else

注意赋值时的类型转换

```java
public class TernaryOperator{
	public static void main(String[] args){
		//输出三个数中的最大值
		//method 1(可读性不强，且运算效率低)
		int a = 123, b = 321, c = 213;
		int max = a > b ? (a > c ? a : c):(b > c ? b : c);
		System.out.println("最大值是" + max);
		//method 2 （可读性强，且运算效率高）
		int max1 = a > b ? a : b;
		int max2 = max1 > c ? max1 : c;
		System.out.println("最大值是" + max2);
	}
}
```

输出

```
E:\java\javacode>java TernaryOperator
最大值是321
最大值是321
```

##### 6. 运算符的优先级

（1）（）{} .  , ;等

（2）单目运算 ++ --

（3）算数运算符 * / % + -

（4）位移运算符 <<  >>  <<<

（5）关系运算符 < > <= >= == !=

（6）逻辑运算符 & ^ | && ||

（7）三元运算符 ？ ：

（8）赋值运算符 =  +=  -=  *=  /=  %=    

### 6. 标识符

（1）26个字母大小写，0-9，_或$

（2）数字不能开头

（3）不能使用关键字(java使用的，如int， public)和保留字(java将会使用的，文档)

（4）严格区分大小写，长度无限制

（5）不能包含空格

包名：多单词组成时，所有字母小写，aaa.bbb.ccc

类名、接口名：多单词组成时，所有单词首字母大写，AaaBbbCcc

变量名、方法名：多单词组成时，第一个单词小写，之后的单词首字母大写，aaaBbbCcc

常量名：所有字母大写，多单词时用_连接，AAA_BBB_CCC

### 7. 关键字和保留字

关键字：被 java 赋予特殊含义，都为字母小写，不用背，会变色

保留字：还未被现有 java 使用，以后版本可能会用，byValue，generic，inner，operator，rest，var，goto， const，future，cast，outer。

### 8. 键盘输入语句

（1）查阅文档引入包下的类，import   xxx

（2）创建该类下的对象，Scanner  对象名 = new  Scanner(System.in)

（3）用相关的方法进行接收，int 变量名 = 对象名.nextint,等

```java
import java.util.Scanner; //导入相关包下的具体类
public class KeyboardInput{
	public static void main(String[] args){
		//键盘输入姓名，年龄，工资并输出
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入姓名：");
		String name = sc.next();
		System.out.println("请输入年龄：");
		int age = sc.nextInt();
		System.out.println("请输入工资：");
		float money = sc.nextFloat();
		System.out.println("人的信息如下\n" + "姓名\t年龄\t工资\n" 
			+ name + "\t" + age + "\t" + money);
	}
}
```

输出

```
E:\java\javacode>java KeyboardInput.class
错误: 找不到或无法加载主类 KeyboardInput.class

E:\java\javacode>java KeyboardInput
请输入姓名：
baymax
请输入年龄：
5
请输入工资：
10000.0
人的信息如下
姓名    年龄    工资
baymax  5       10000.0
```

### 9. 进制

二进制：0b或者0B开头

八进制：0开头

十进制：默认

十六进制：0x或者0X开头

##### 1. 其他进制转十进制

二进制：从最右边开始，对应位数*2^(n-1)，再相加，最右n = 1；

八进制：从最右边开始，对应位数*8^(n-1)，再相加，最右n = 1；

十六进制：从最右边开始，对应位数*16^(n-1)，再相加，最右n = 1；

##### 2. 十进制转其他进制

二进制：十进制数不断除2，记下余数，直至商为0为止，所得余数倒过来即为对应二进制

八进制：十进制数不断除8，记下余数，直至商为0为止，所得余数倒过来即为对应八进制

十六进制：十进制数不断除16，记下余数，直至商为0为止，所得余数倒过来即为对应十六进制

##### 3. 二进制转其他进制

八进制：从最右开始，取三位为一组，分别转换为对应八进制数，不够前补0

十六进制：从最右开始，取四位为一组，分别转换为对应十六进制数，不够前补0

##### 4. 其他进制转二进制

八进制：从最右开始，每一位数都转为对应的三位二进制数，字节不够前补零

十六进制：从最右开始，每一位数都转为对应的四位二进制数，字节不够前补零

### 10. 位运算

```
m>>n      m右移n位，低位溢出，高位用符号位补齐，符号位不变
m<<n      m左移n位，符号位不变，低位补0
m>>>n     m算数右移n位，低位溢出，高位补零
~m		  m按位取反
m&n		  m和n按位与
m|n 	  m和n按位或
m^n       m和n按位异或
```

##### 1. 原码、反码、补码

1. 二进制最高位是符号位，0为正数，1为负数
2. 正数的原码、反补码都一样
3. 负数的反码，符号位不变，其他位取反
4. 负数的补码，为负数的反码+1
5. 0的反码、补码都是0
6. 计算机运算时以补码形式运算
7. 看结果时，要看原码

```
~-2的过程：
	-2原码：10000000 00000000 00000000 00000010
	-2反码：11111111 11111111 11111111 11111101
	-2补码：11111111 11111111 11111111 11111110
    对补码进行取反操作：00000000 00000000 00000000 00000001
	~-2结果为1
~2的过程：
	2的补码：00000000 00000000 00000000 00000010
    对补码进行取反操作：11111111 11111111 11111111 11111101（是负数，转为原码）
	先转反码（补码-1）：11111111 11111111 11111111 11111100
	再转原码：10000000 00000000 00000000 00000011
	~2结果为-3
-1 >> 2的过程：
	-1原码：10000000 00000000 00000000 00000001
	-1反码：11111111 11111111 11111111 11111110
	-1补码：11111111 11111111 11111111 11111111
    对补码进行右移2位：11111111 11111111 11111111 11111111（是负数，转为原码）
	先转反码：11111111 11111111 11111111 11111110
	再转原码：10000000 00000000 00000000 00000001
	-1 >> 2的结果为-1
-1 << 2的过程：
	-1原码：10000000 00000000 00000000 00000001
	-1反码：11111111 11111111 11111111 11111110
	-1补码：11111111 11111111 11111111 11111111
     对补码进行左移2位：11111111 11111111 11111111 11111100（是负数，转为原码）
     先转反码：11111111 11111111 11111111 11111011
     再转原码：10000000 00000000 00000000 00000100
     -1 << 2的结果为-4
```

### 11. 顺序控制

##### 1. 单分支结构

```
if(条件表达式){
	执行代码块;
}
执行代码块只有一条语句，{}可省略
```

##### 2. 双分支结构

```
if(条件表达式){
	执行代码块1;
}
else{
	执行代码块2;
}
执行代码块只有一条语句，{}可省略
```

```java
import java.util.Scanner;
public class if_else{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		//声明两个double并赋值，第一个大于10，第二个小于20，打印两者的和
		System.out.println("请输入a1：");
		double a1 = sc.nextDouble();
		System.out.println("请输入a2：");
		double a2 = sc.nextDouble();
		if(a1>10 && a2<20){
			System.out.println("a1和a2的和为：" + (a1+a2));
		}
		System.out.println("程序继续");

		//定义两个int，两者和能被3整除同时被5整除，打印信息
		System.out.println("请输入b1：");
		int b1 = sc.nextInt();
		System.out.println("请输入b2：");
		int b2 = sc.nextInt();
		int sum = b1 + b2;
		if((sum%3) == 0 && (sum%5) == 0){
			System.out.println("b1 = " + b1 + "\nb2 = " + b2 + "\nsum = " + sum);
		}
		System.out.println("程序继续");

		//判断今年是否是闰年，（1）能被4整除，不能被100整除，（2）能被400整除
		System.out.println("请输入年份：");
		int year = sc.nextInt();
		if((year%400) != 0){
			if((year%100) != 0){
				if((year%4) != 0){
					System.out.println(year + "年不是闰年");
				}
				else{
					System.out.println(year + "年是闰年");
				}
			}
			else{
				System.out.println(year + "年不是闰年");
			}
		}
		else{
			System.out.println(year + "年是闰年");
		}
	}
}
```

输出

```
E:\java\javacode>java if_else
请输入a1：
14
请输入a2：
12
a1和a2的和为：26.0
程序继续
请输入b1：
4
请输入b2：
11
b1 = 4
b2 = 11
sum = 15
程序继续
请输入年份：
2100
2100年不是闰年
```

##### 3. 多分支结构

```
if(条件表达式){
	执行代码块;
}
else if(条件表达式){
	执行代码块;
}
...
else{
	执行代码块;
}
(else可无)
```

```java
import java.util.Scanner;
public class if_elseif{
	public static void main(String[] args){
		//输入信用分，输出等级
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入信用分(0-100)：");
		int score = sc.nextInt();
		if(0 <= score && score<= 100){
			if(score == 100){
				System.out.println("信用极好");
			}
			else if(score >= 80){
				System.out.println("信用优秀");
			}
			else if(score >= 60){
				System.out.println("信用良好");
			}
			else{
				System.out.println("信用不及格");
			}
		}
		else{
			System.out.println("输入有误！");
		}
		
	}
}
```

输出

```
E:\java\javacode>java if_elseif
请输入信用分(0-100)：
110
输入有误！

E:\java\javacode>java if_elseif
请输入信用分(0-100)：
45
信用不及格

E:\java\javacode>java if_elseif
请输入信用分(0-100)：
78
信用良好
```

##### 4. 嵌套分支

```
if(条件表达式){
	if(条件表达式){
		if(条件表达式){
			执行代码块;
		}
		else{}
	}
	else{}
}
else{}
//最多嵌套3层，可读性不好
```

```java
import java.util.Scanner;
public class if_if_if_test{
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入月份（1-12)：");
		int month = sc.nextInt();
		if(month >= 1 && month <=12){
			System.out.println("请输入年龄：");
			int age = sc.nextInt();
			if(age >= 0){
				if(month >= 4 && month <= 10){
					System.out.println("这是旺季");
					if(age >= 60){
						System.out.println("老人，票价20");
					}
					else if(age <= 18){
						System.out.println("小孩，票价30");
					}
					else{
						System.out.println("成人，票价60");
					}
				}
				else{
					System.out.println("这是淡季");
					if(age >= 18 && age <= 60){
						System.out.println("成人，票价40");
					}
					else{
						System.out.println("特殊人群，票价20");
					}
				}	
			}
		}
		else{
			System.out.println("月份错误");
		}
	}
}
```

输出

```
E:\java\javacode>java if_if_if_test
请输入月份（1-12：
5
请输入年龄：
34
这是旺季
成人，票价60

E:\java\javacode>java if_if_if_test
请输入月份（1-12：
2
请输入年龄：
3
这是淡季
特殊人群，票价20

E:\java\javacode>java if_if_if_test
请输入月份（1-12：
7
请输入年龄：
98
这是旺季
老人，票价20
```

##### 5. switch结构

```
switch(表达式){ //表达式的数据类型应和case后的常量类型一致，或可以自动转换，比如表达式是char，常量为int
	case 常量1：//不能为变量
		语句块1；
		break；//跳出switch，没有break则执行下一个case的语句块
	...
	case 常量n：//不同case执行一样的语句块时，使用穿透
		语句块n；
		break；
	default：//可没有default
		default 语句块；
		break；
}
```

```java
import java.util.Scanner;
public class switch_test{
	public static void main(String[] args){
		//把输入的小写转变为大写，只转a,b,c,d
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入字母：");
		char word = sc.next().charAt(0);
		switch(word){
			case 'a':
				System.out.println("A");
				break;
			case 'b':
				System.out.println("B");
				break;
			case 'c':
				System.out.println("C");
				break;
			case 'd':
				System.out.println("D");
				break;
			default:
				System.out.println("other");
				break;
		}
		System.out.println("程序继续~");

		//用switch判断分数是否合格
		System.out.println("请输入分数：");
		double score = sc.nextDouble();
		if(score >= 0 && score <= 100){
			switch((int)(score/60)){
				case 0:
					System.out.println("不合格");
					break;
				case 1:
					System.out.println("合格");
					break;
			}
		}
		else{
			System.out.println("分数输入错误！");
		}
		System.out.println("程序继续~");

		//输入月份，判断季节
		System.out.println("请输入月份：");
		int month = sc.nextInt();
		switch(month){
			case 3:
			case 4:
			case 5:
				System.out.println("这是春季");
				break;
			case 6:
			case 7:
			case 8:
				System.out.println("这是夏季");
				break;
			case 9:
			case 10:
			case 11:
				System.out.println("这是秋季");
				break;
			case 12:
			case 1:
			case 2:
				System.out.println("这是冬季");
				break;
			default:
				System.out.println("输入月份有误！");
				break;
		}
	}
}
```

输出

```
E:\java\javacode>java switch_test
请输入字母：
a
A
程序继续~
请输入分数：
34
不合格
程序继续~
请输入月份：
4
这是春季
```

##### 6. for循环

```
for(循环变量初始化;循环条件;循环变量迭代){  //初始化可在循环前，在循环内初始化的变量只能在循环里用
	循环语句； //循环变量迭代可在循环语句内
}
for(;;) //死循环
```

```java
public class for_test{
	public static void main(String[] args){
		//打印1-100内9的倍数，统计个数及总和
		int count = 0, sum = 0, num = 9;
		int start = 1, end = 100;
		for(int i = start; i <= end; i ++){
			if((i % num) == 0){
				count ++;
				sum += i;
			}
		}
		System.out.println("1-100内，9的倍数有" + count + "个，总和为" + sum);

		//输出正数和为5的表达式
		sum = 5;
		for(int i = 0; i <=sum; i ++){
			for(int j = 0; j <= 5; j ++){
				if((i + j) == sum){
					System.out.println(i + "+" + j + "=" + (i+j));
				}
			}
		}
		//另一种方法
		for(int i = 0; i <= sum; i ++){
			System.out.println(i + "+" + (sum-i) + "=" + sum);
		}
	}
}
```

输出

```
E:\java\javacode>java for_test
1-100内，9的倍数有11个，总和为594
0+5=5
1+4=5
2+3=5
3+2=5
4+1=5
5+0=5
0+5=5
1+4=5
2+3=5
3+2=5
4+1=5
5+0=5
```

##### 7. while循环

```
循环变量初始化
while(循环条件){
	循环语句；
	循环变量迭代；
}
```

```java
public class while_test{
	public static void main(String[] args){
		//打印1-100之间所有能被3整除的数
		int start = 1, end = 100;
		int divisor = 3;
		int i = start;
		while(i <= end){
			if((i % divisor) == 0){
				System.out.println(i);
			}
			i ++;
		}	
	}
}
```

输出

```
E:\java\javacode>java while_test
3
6
9
12
...
93
96
99
```

##### 8. do_while循环

```
循环变量初始化
do{
	循环语句；
	循环变量迭代；
}while(循环条件);
条件不满足时执行循环
```

```java
import java.util.Scanner;
public class do_while_test{
	public static void main(String[] args){
		//统计1-100之间能被5整除，但不能被3整除的个数
		int start = 1, end = 100;
		int divisor1 = 5, divisor2 = 3;
		int count = 0;
		int i = start;
		do{
			if((i % divisor1) == 0 && (i % divisor2) != 0){
				count ++;
			}
			i ++;
		}while(i <= end);
		System.out.println(count);
		System.out.println("--------------------程序继续------------------");

		//一直询问还钱吗，直至说yes为止
		Scanner sc = new Scanner(System.in);
		char answer;
		do{
			System.out.println("还钱吗！y/n:");
			answer = sc.next().charAt(0);
			}while(answer != 'y');
		System.out.println("终于还钱了！");
	}
}
```

输出

```
E:\java\javacode>java do_while_test
14
--------------------程序继续------------------
还钱吗！y/n:
g
还钱吗！y/n:
y
终于还钱了！
```

##### 9. 多重循环

```
for(){
	for(){
		for(){
		
		}
	}
}
while,do_while同理
```

```java
import java.util.Scanner;
public class multifor{
	public static void main(String[] args){
		//年级3个班，每班5人，输入学生成绩，统计平均分和及格人数
		int classnum = 3, studentnum = 5;
		double ave_class, ave_grade, sum_class = 0, sum_grade = 0;
		Scanner sc = new Scanner(System.in);
		double score;
		int passnum = 0;
		for(int i = 1; i <=classnum; i ++){
			for(int j = 1; j <= studentnum; j ++){
				System.out.println("请输入" + i + "第" + j + "位学生成绩：");
				score = sc.nextDouble();
				if(score >= 60){
					passnum ++;
				}
				sum_class += score;
			}
			ave_class = sum_class / studentnum;
			System.out.println(i + "班平均成绩为：" + ave_class);
			sum_grade += ave_class;
			sum_class = 0;
		}
		ave_grade = sum_grade / classnum;
		System.out.println("年级平均成绩为：" + ave_grade);
		System.out.println("及格人数为：" + passnum);

		//´打印99乘法表
		for(int i = 1; i < 9; i ++){
			for(int j = 1; j <= i; j ++){
				System.out.print(j + "*" + i + "=" + (i*j));
				System.out.print("\t");
			}
			System.out.println();
		}
	}
}
```

输出

```
E:\java\javacode>javac multifor.java

E:\java\javacode>java multifor
请输入1班，第1位同学的成绩：
69
请输入1班，第2位同学的成绩：
23
请输入1班，第3位同学的成绩：
34
请输入1班，第4位同学的成绩：
45
请输入1班，第5位同学的成绩：
56
1班平均成绩为：45.4
请输入2班，第1位同学的成绩：
67
请输入2班，第2位同学的成绩：
23
请输入2班，第3位同学的成绩：
45
请输入2班，第4位同学的成绩：
43
请输入2班，第5位同学的成绩：
24
2班平均成绩为：40.4
请输入3班，第1位同学的成绩：
34
请输入3班，第2位同学的成绩：
56
请输入3班，第3位同学的成绩：
90
请输入3班，第4位同学的成绩：
65
请输入3班，第5位同学的成绩：
34
3班平均成绩为：55.8
年级平均成绩为：47.199999999999996
及格人数为：4
1*1=1
1*2=2   2*2=4
1*3=3   2*3=6   3*3=9
1*4=4   2*4=8   3*4=12  4*4=16
1*5=5   2*5=10  3*5=15  4*5=20  5*5=25
1*6=6   2*6=12  3*6=18  4*6=24  5*6=30  6*6=36
1*7=7   2*7=14  3*7=21  4*7=28  5*7=35  6*7=42  7*7=49
1*8=8   2*8=16  3*8=24  4*8=32  5*8=40  6*8=48  7*8=56  8*8=64
1*9=9   2*9=18  3*9=27  4*9=36  5*9=45  6*9=54  7*9=63  8*9=72  9*9=81
```

##### 10. break

# 高级

<img src="E:\java\QQ图片20220906154108.png" style="zoom:50%;" />

### 1. 类变量和类方法(static)

静态成员只能访问静态成员

普通成员可以访问普通成员也可以访问静态成员

```java
类变量（静态变量/静态属性）：
    所有类对象共享一个变量数据，在类加载时生成，并不依赖于对象，随着类销毁而销毁
定义：
    访问修饰符 static 数据类型 变量名
访问：
    遵守访问修饰符的访问权限，类名.类变量名、对象名.类变量名
内存机制：
    1. 在堆空间开辟空间存放静态变量，每个类对象都存放指向该空间的地址（jdk8之后）
    2. 加载类信息时，存放在方法区的静态域中（jdk8之前）
```

```java
类方法（静态方法）：
    可以不通过创建实例，调用类的方法
定义：
    访问修饰符 static 数据返回类型 方法名(){}
访问：
    1. 遵守访问修饰符的访问权限，类名.方法名、对象名.方法名
    2. 类方法中只能访问静态变量或者静态方法
    3. 类方法中不能使用对象有关的关键字， super 和 this
    4. 类方法不能被重写
内存机制：
    随着类加载而加载，存储在方法区
```

<img src="E:\java\截图\1.png" alt="1" style="zoom: 50%;" />

```java
9
10  
11
//共享一个 count
```

<img src="E:\java\截图\2.png" alt="2" style="zoom: 67%;" />

```java
//修改代码
1. getTotalPerson()为静态方法不能访问属性 id，id 修改为静态变量
//输出
0
1
```

<img src="E:\java\截图\3.png" alt="3" style="zoom:67%;" />

```java
//修改代码
1. setTotalPerson()方法中不能使用 this，注释
//total最终为
4
```

### 2. main 方法

```java
public static void main(String[] args){}
1. main 方法由 java 虚拟机调用，访问权限必须是 public
2. java 虚拟机调用 main 方法时不需要创建对象，所以该方法必须是 static
3. main 方法接收 String 类型的数组参数，该数组中保存执行 java 命令时传递给所运行的类的参数
4. java 执行程序名 参数1 参数2 参数3，参数1 参数2 参数3就可传入 args
5. java 虚拟机不需要返回值，所以返回类型为 void
6. main 是静态方法，可以直接访问类中的静态属性和静态方法，不能访问非静态成员，需要创建类对象来调用
```

传递参数实例

![image-20220906175005934](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220906175005934.png)

![image-20220906175127916](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220906175127916.png)

![image-20220906175213165](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220906175213165.png)

### 3. 代码块

##### 1. 细节

又称为初始化块，类中的成员，类似于方法，将逻辑语句封装在方法体中

没有方法名，没有返回，没有参数

不用通过类或者对象显式调用，加载类时或创建对象时隐式调用（当构造器重载且内容冗余时，创建代码块）

```java
1. 基本语法
	修饰符{    //修饰符可选，只能写static
    	代码  //有 static 修饰就为静态代码块，否则就为非静态代码块，可以使用任何逻辑语句
	};       //;号可以省略
2. 如果代码块由 static 修饰，随着类的加载而执行，只会执行一次，因为类只加载一次；而普通代码块在每次创建对象时都会执行，与构造器相关。会先加载静态代码块。
```

![image-20220907180545109](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220907180545109.png)

```java
3. 类在什么时候会被加载
    创建对象实例时（new）
    创建子类对象实例，父类也会被加载，而且父类先被加载
    使用类的静态成员时，如果该类有父类，父类也会被加载，普通代码块不会执行（需要创建对象才执行）
```

![image-20220907181844653](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220907181844653.png)

```java
4. 创建对象时，调用顺序是：
    首先调用静态代码块和静态属性初始化（并非构造器），多个按定义顺序执行
    其次调用普通代码块和普通属性初始化，多个按定义顺序执行
    最后调用构造器
    //静态成员只能访问静态成员，这里 n1 = getN2() 不可行
```

![image-20220907203712270](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220907203712270.png)

```java
5. 构造器中隐含了 super() 和调用普通代码块、普通属性初始化
    （下图箭头有误，第三句指向 B 类构造器）
```

![image-20220907205351162](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220907205351162.png)

```java
6. 继承关系中，构造方法时调用顺序：
    首先调用父类的静态属性初始化和静态代码块
    其次调用子类的静态属性初始化和静态代码块
    再调用父类的普通属性初始化和普通代码块
    接着调用父类构造器
    然后调用子类普通属性初始化和普通代码块
    最后调用子类构造器
```

![image-20220907212025386](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220907212025386.png)

```java
7. 静态代码块只能直接调用静态成员，普通代码块可以调用任意成员
```

##### 2. 练习

<img src="E:\java\截图\4.png" alt="4" style="zoom:50%;" />

输出

```java
in static block!  //Person.total 是 Person 类静态成员，被调用时会加载类，即静态代码块会调用
total = 100;
total = 100;     //静态代码块只执行一次
```

<img src="E:\java\截图\5.png" alt="5" style="zoom:67%;" />

输出

```java
静态成员sam初始化         //执行 Test 类的静态属性 sam 初始化，在Sample类的有参构造器内输出
static 块执行            //执行 Test 类的静态代码块
sam1成员初始化           //执行 Test 类的普通属性初始化，在Sample类的有参构造器内输出
Test默认构造器函数被调用  //执行 Test 类的构造器
```

### 4. 单例模式

单例模式是设计模式中的一种，有饿汉式和懒汉式，目的是采取一定的方法保证在整个的软件系统中， 某个类只能存在一个对象实例， 并且该类只提供一个取得其对象实例的方法。

```java
步骤：
    首先，构造器私有化（防止直接 new ）
    其次，在类中创建对象
    最后提供一个静态的 get 方法
//饿汉式（创建对象时就会 new 初始化）
//创建的对象必须是静态，才能被静态方法 get 访问
//由于所创对象为静态属性，在类加载时就初始化了（饿汉，可能创建了对象并没有使用）    
//不管在主方法中创建多少个对象，都是同一个对象
```

![image-20220908100256321](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908100256321.png)

```java
//懒汉式（调用时才会 new 初始化）
//不存在资源浪费，但有多线程安全问题
```

![image-20220908104124047](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908104124047.png)

### 5. final

可以修饰类、属性、方法、局部变量

访问修饰符 final

```java
1. 需求：
    不希望类被继承
    不希望类里的方法被重写
    不希望类里的属性被修改
    不希望局部变量被修改
2. 细节：
    属性被 final 修饰时为常量，必须初始化：定义时直接赋值或者构造器中赋值或者代码块赋值。
    final 修饰静态属性时，只能在定义和静态代码块中初始化。
    类被 final 修饰后，其中方法就不必用 final 修饰了
    final 不能修饰构造器
    final 和 static 搭配使用，效率更高，不会导致类加载，底层做了优化
    包装类（ Integer 、 Double 、 Boolean 等）和 String 都是 final ，不能被继承
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908124546622.png" alt="image-20220908124546622" style="zoom:67%;" />

![image-20220908124441260](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908124441260.png)

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908124611931.png" alt="image-20220908124611931" style="zoom:67%;" />

```java
//修改
++ x，不能修改 x 的值
//输出
x 的值加上 1
```

### 6. 抽象类

当类里的方法需要声明，但不确定怎么实现，可以声明为抽象方法（没有方法体），则类为抽象类

价值在于设计模式，被继承

```java
1. 声明：
    abstract 类名{
    	abstract 返回类型 方法名()；
	}
2. 细节：
    抽象类不可以实例化
    抽象类里可以没有抽象方法
    抽象方法必须在抽象类里
    抽象 abstract 只能修饰类和方法，不能修饰属性
    抽象类还是类，可以有任意类成员：属性、构造器、方法
    如果继承了抽象类，则该类必须实现抽象类的所有抽象方法（有方法体就是实现），否则也要声明为抽象类
    抽象方法不能使用 private 、 static 、 final 修饰，与方法重写违背
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908162942946.png" alt="image-20220908162942946" style="zoom:67%;" />

模板设计模式

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908163126967.png" alt="image-20220908163126967" style="zoom:67%;" />

```java
System.currentTimeMillis(); // 计时器
//首先创建一个抽象类定义公共的计时模板（方法）：开始 -> job() -> 结束
//声明 job() 为抽象方法，具体实现由之后的类继承重写
//需要子类计时时直接调用父类的计时方法
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908171854951.png" alt="image-20220908171854951" style="zoom: 50%;" /><img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908172018806.png" alt="image-20220908172018806" style="zoom: 50%;" />

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220908172447253.png" alt="image-20220908172447253" style="zoom:50%;" />

### 7. 接口

##### 1. 基本介绍

接口就是给出一些没有实现的方法，封装到一起，某个类要用时根据具体情况写方法

统一规范

```java
访问修饰符 interface 接口名{
	属性
    方法（jdk7及之前，接口方法都为抽象方法，之后接口方法可以为静态方法（static）、普通方法（default）
}
访问修饰符 class 类名 implements 接口名{
    属性
    方法（必须实现接口的方法）
}
```

##### 2. 细节

```java
1. 接口不能被实例化
2. 接口中所有方法都默认是 public ，抽象方法可以不用 abstract 修饰
3. 一个普通类实现接口，必须把接口所有方法都实现，继承了所有属性
4. 抽象类实现接口，可以不实现抽象方法
5. 一个类可以实现多个接口： class 类名 implements  接口名,接口名
6. 接口中的属性必须是 final 、 public 、 static ， int n1 = 1 == public final static int n1 = 1
7. 接口可以继承接口，不能继承类
8. 接口的访问修饰符只能是默认和 public
```

##### 3. 练习一

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220911112003770.png" alt="image-20220911112003770" style="zoom:67%;" />

输出

```java
//B 类实现了 A 接口，会实现其方法，继承其属性
23 //通过实例访问静态属性
23 //通过类名访问静态属性
23 //同上
```

##### 4. 接口 Vs 继承

接口时 java 单继承机制的补充

子类继承父类，自动拥有了父类的属性和方法，如子类要扩展功能就需要接口实现

```java
1. 解决问题不同：
    继承价值在于，解决代码的复用性和可维护性
    接口价值在于，设计好各种规范，让其他类去实现
2. 灵活性不同：
    继承是 is-a 关系，灵活性更低
    接口是 like-a 关系，灵活性更高
3. 接口规范+动态绑定可以实现代码解耦
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220911161422289.png" alt="image-20220911161422289" style="zoom:80%;" />

##### 5. 接口多态

```java
1. 多态参数
    把接口作为方法的形参，只要是实现该接口的类的实例都可以传入该方法，接口类型的变量可以指向实现了该接口的实例
    	public interface UsbInterface{}
    	public class Phone implements UsbInterface{}   // UsbInterface usb = new Phone
		public class Camera implements UsbInterface{} // UsbInterface usb = new Camera
         public void work(UsbInterface usbInterface){}  //这里可传入 Phone 和 实例 Camera 实例
2. 多态数组
         也存在动态绑定和向下、向上转型，以及类型判断
         UsbInterface[] usbs = new UsbInterface[2]
         usbs[0] = new Phone
         usbs[1] = new Camera
3. 多态传递
    	接口存在继承时，类就实现了该接口及其父类接口，也需实现其父类的方法 
        public interface TypeC extends UsbInterface{}
	    public class Camera implements TypeC{}  //相当于 Camera 实现了 UsbInterfac 和 TypeC 两个接口
```

##### 6. 练习二

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220911165730187.png" alt="image-20220911165730187" style="zoom:67%;" />

```java
//修改
System.out.println(x) 时 x 可以是父类 B 的属性，也可以是接口 A 的属性
System.out.println(A.x) 或者 System.out.println(super.x)
//输出
0 或者 1
```

### 8. 内部类

类的五大成员：属性、方法、构造器、代码块、内部类

一个类的内部完整的嵌套了另一个类结构，被嵌套的为内部类，可直接访问私有属性

```java
class A{
    class B{}
}
class C{}
//A 为外部类，B为内部类，C为外部其他类
//内部类里还可以有内部类
定义在外部类的局部位置（比如方法内）上：
    局部内部类（有类名）
    匿名内部类（无类名）
定义在外部类的成员位置上：
    静态内部类（有 static 修饰）
    成员内部类（无 static 修饰）
```

##### 1. 局部内部类

```Java
1. 可以直接访问外部类的所有成员，包含私有
2. 地位为一个局部变量，不能添加访问修饰符，只能添加 final ，可以被继承
3. 作用域只在定义的方法内或者代码块内
4. 在外部类中，通过创建内部类的对象（必须在内部类的作用域中）来调用内部类的方法
5. 外部其他类不能访问局部内部类
6. 外部类和局部内部类的成员重名时，遵循就近原则，如果想访问外部类成员使用：外部类.this.成员名
```

##### 2. 匿名内部类

一个类只使用一次，后面不再使用，用匿名内部类简化开发

```java
1. 本质是内部类，没有名字， new 类名或接口（参数列表）{}；
		interface A{}
		A a  = new A(){}
2. a 的编译类型是接口类型 A，运行类型是匿名内部类
3. 在底层，相当于匿名内部会被创建并分配名字，然后立即创建一个实例，并且把地址返回给 a，也可以不赋给 a
    	class XXXX implements A{}   //xxxx 为外部类$1，1为顺序
		A a = new XXXX()
         new A(){}.方法名     //本身返回的就是实例，可直接调用方法
4. 匿名内部类用过一次就消失，但创建的实例 a 还能调用
5. 基于接口是实现 implements ，基于类是继承 extends ，遵循所有实现和继承的规则
6. 参数列表会传给构造器
7. 可以直接访问外部类所有成员，包括私有
8. 不能添加访问修饰符，低位只是局部变量
9. 外部其他类不能访问匿名内部类
10. 外部类和匿名内部类的成员重名时，遵循就近原则，如果想访问外部类成员使用：外部类.this.成员名
```

练习

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220912191210489.png" alt="image-20220912191210489" style="zoom: 67%;" />

解析

```java
接口 AA 内有方法 cry
show() 方法形参类型是 AA，内容是调用 a.cry
new AA(){public void cry{System.out.println("AA cry")}}//本质上一个实现 AA 接口的匿名内部类的一个对象
show(该对象) 调用 show 方法，此时对象的编译类型是 AA，运行类型是匿名内部类
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220912192120850.png" alt="image-20220912192120850" style="zoom:67%;" />

```java
public class Anonymous_ {
    public static void main(String[] args) {
        Cellphone cellphone = new Cellphone();
        cellphone.alarmcolok(new Bell() {
            @Override
            public void ring() {
                System.out.println("懒猪起床了"); //两个匿名内部类不一样
            }
        });

        cellphone.alarmcolok(new Bell() {
            @Override
            public void ring() {
                System.out.println("该去上课了");
            }
        });
    }
}
 interface Bell{
    void ring();
 }

 class Cellphone{
     public void alarmcolok(Bell bell){
        bell.ring();
     }
 }
```

##### 3. 成员内部类

```java
1. 定义在外部内的成员位置，且没有 static 修饰，有名字
2. 可以直接访问外部类的所有成员，包括私有
3. 本身地位是一个成员，可以用 public ，默认， private ， protected 修饰，
4. 作用域在整个外部类中，参考属性和方法在类中的使用
5. 外部其他类可以访问成员内部类：
    方式一，创建对象：Outer outer = new Outer(); Outer.Inner inner = outer.new Inner();
    				Outer.Inner inner = new Outer().new Inner();
    方式二，可以在类中使用 get、set 方法访问： getInner(){return new Inner();}
										Inner inner = outer.getInner;
6. 外部类和成员内部类的成员重名了，遵循就近原则，如要访问外部类的成员 Outer.this.成员名
```

##### 4. 静态内部类

```java
1. 定义在外部类的成员位置，有 static 修饰，有名字
2. 本质上是外部类的静态成员，只能访问外部类的所有静态成员，包括私有的
3. 可以添加四种访问修饰符
4. 作用域是整个类体
5. 外部类访问静态内部类，创建对象再访问
6. 外部其他类访问内部类
    方式一：创建对象访问，Outer.Inner inner = new Outer.Inner()
    方式二：用 get 访问，get 可以为静态的
7. 外部类和静态内部类的成员重名，遵循就近原则，如果要访问外部类的成员，Outer.成员，（该成员只能是静态的）
```

##### 5. 练习

1. <img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220913164827445.png" alt="image-20220913164827445" style="zoom:67%;" />

输出

```java
//成员内部类
5
5
```

### 9. 枚举类

enumeration

一组常量的组合，是一种特定的类，里面只包含一组有限的特定的对象

##### 1. 自定义枚举类

```java
1. 构造器私有化，外部不可新建对象
2. 去掉 setX() 方法，外部不可修改属性
3. 在内部创建固定的对象，对象名大写，视为常量
4. 优化， static + final 修饰对象 
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220915100727458.png" alt="image-20220915100727458" style="zoom:67%;" />

##### 2. enum 实现枚举

使用关键字enum 创建枚举类时，默认继承 Enum 类，而且是一个 final 类，（用javap看底层逻辑）

```java
1. 用关键字 enum 代替 class
2. 创建对象时，直接使用：对象名(参数列表).如果使用无参构造器创建对象，则实参列表和()都可以省略，直接对象名
3. 多个对象用 , 间隔，最后一个带;
4. 定义对象写在最前面
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220915103745516.png" alt="image-20220915103745516" style="zoom:67%;" />

练习

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220915105349644.png" alt="image-20220915105349644" style="zoom:67%;" />

```java
正确
1. 关键字enum 创建枚举类 Gender
2. 没有定义构造器，默认无参构造器
3. 用无参构造器创建对象 BOY 和 GIRL
```

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220915105647835.png" alt="image-20220915105647835" style="zoom:67%;" />

```java
1. System.out.println(boy) 默认调用 boy.toString()，这里 toString() 是父类 Enum 的（返回 name）
    输出BOY
2. boy 和 boy2 都指向同一对象，即 BOY 指向的对象
```

##### 3. Enum 类成员方法

常用方法

```java
0. toString()：Enum 类重写了，返回枚举对象名
1. name() 方法：返回枚举对象的名字
		EnumSeason ES = EnumSeason.SPRING;
		ES.name();  //返回 SPRING
2. ordinal() 方法：返回枚举对象的次序/编号，从 0 开始
		SPRING.oridinal();  //返回 0 
		AUTUMN.oridinal();  //返回 1
		SUMMER.oridinal();  //返回 2
		WINDER.oridinal();  //返回 3
3. values() 方法：返回枚举对象数组
		EnumSeason[] seasons = EnumSeason.values();
		//增强 for 循环
		for (数组类型 变量名 ： 数组名) ：会依次把数组里的元素赋给变量名，直至所有元素退出循环
                    for(EnumSeason season : seasons){   //依次输出 SPRING AUTUMN SUMMER WINTER
            			System.out.println(season);
        			}
4. valueOf() 方法：将字符串转换为枚举对象，要求字符串必须为已有的常量名
		EnumSeason winter = EnumSeason.valueOf("WINTER");
		winter 指向 WINTER 这个枚举对象
5. compareTo() 方法：比较两个枚举对象，比较的是编号
         winter.compareTo(ES); //返回 winter 的编号减去 ES 的编号，为 3
```

##### 4. 练习

<img src="C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220915124848786.png" alt="image-20220915124848786" style="zoom:67%;" />

```java
public class Week {
    public static void main(String[] args) {
        System.out.println("所有的星期信息如下：");
        Weekday[] weekdays = Weekday.values();
        for(Weekday weekday: weekdays){
            System.out.println(weekday);
        }
    }
}

enum Weekday{
    MONDAY("星期一"),
    TUESDAY("星期二"),
    WEDNESDAY("星期三"),
    THURSDAY("星期四"),
    FRIDAY("星期五"),
    SATURDAY("星期六"),
    SUNDAY("星期天");

    private String name;

    public String toString(){
        return name;
    }

    Weekday(String name) {
        this.name = name;
    }
}
```

##### 5. enum 实现接口

```java
1. 使用关键字enum 创建枚举类，隐式继承 Enum 不能再继承其他类
2. 枚举类还是一个类，可以实现接口
      enum 类名 implements 接口
```

### 10. 注解

annotation，也被称为元数据，用于修饰解释包、类、属性、方法、构造器等数据信息

和注释一样，注解不影响程序逻辑，但注解可以编译运行，相当于补充信息

注解类源码被 @interface 修饰

##### 1. @Override

限定某个方法是重写父类的方法

```java
1. 编译器会判断是否重写了这个方法，没有则报错
2. 如果不写 @Override ，而父类确实有相同的方法，仍构成重写
3. 该注解只能用于方法
```

##### 2. @Deprecated

用于表示程序的某个元素（类、方法等）已过时

```java
1. 过时并不等于不能用，只是不推荐使用
2. 被 @Deprecated 修饰的元素会带上横线
3. 用于版本升级过渡
```

##### 3. @SuppressWarnings

抑制编译器警告

```java
1. @SuppressWarnings({""})，可以写不希望显示的警告信息，见文档
2. 作用范围与放置位置有关
    放在语句上，只对该语句有效
    放在方法上，则抑制该方法内的警告
    放在类上，对整个类有效
```

##### 4. 四种元注解

```java
1. @Retention：指定注解的作用范围，该类里面包含一个 value 成员变量，需要给成员变量赋值
    SOURCE：编译器使用后，直接丢弃这种注解
    CLASS：编译器把这种注解保存在 class文件中，运行Java程序时，JVM 不会保留注解
    RUNTIME：编译器把这种注释保存在 class文件中，运行Java程序时，JVM 会保留注释，程序通过反射获取该注解
2. @Target：指定注解可以在哪些地方使用，该类里面包含一个 value 成员变量，可以为 TYPE、FILED、METHOD等，可以指定多个值
3. @Documented：指定注解是否会在 Javadoc 中体现
4. @Inherited：子类会继承父类的注解
```

### 11. 异常

##### 1. throws 练习

```java
基本介绍
  如果一个方法(中的语句执行时)可能生成某种异常， 但是并不能确定如何处理这种异常，则此方法应显示地声明抛出异常，表明该方法将不对这些异常进行处理，而由该方法的调用者负责处理。
  在方法声明中用throws语句可以声明抛出异常的列表，throws后面的异常类型可以是方法中产生的异常类型，也可以是它的父类。
  
  方法名 throws 异常类型，异常类型，...，{}
    
1)对于编译异常，程序中必须处理，比如try- catch或者throws
2)对于运行时异常，程序中如果没有处理，默认就是throws的方式处理
3)子类重写父类的方法时，对抛出异常的规定:子类重写的方法，所抛出的异常类型要么和父类抛出的异常一致， 要么为父类    抛出的异常的类型的子类型
4)在throws过程中，如果有方法try-catch ,就相当于处理异常，就可以不必throws
5)如果被调用的方法会抛出编译异常，则调用的地方要做显式的异常处理
```

##### 2. 自定义异常

当程序中出现了某些"错误”, 但该错误信息并没有在 Throwable 子类中描述处理，这个时候可以自己设计异常类，用于描述该错误信息。

```java
自定义异常的步骤
1)定义类:自定义异常类名(程序员自己写)继承 Exception 或 RuntimeException
2)如果继承 Exception,属于编译异常
3)如果继承 RuntimeException,属于运行异常(一般来说， 继承RuntimeException)，编译异常必须处理
```

![image-20220923103442094](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923103442094.png)

![image-20220923102921348](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923102921348.png)

![image-20220923102951207](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923102951207.png)

##### 3. throw VS throws

![image-20220923103239238](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923103239238.png)

![image-20220923104244478](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923104244478.png)

输出

```java
1. 进入方法A
2. 用 A 方法的 finally
3. 制造异常
4. 进入方法B
5. 调用B方法的 finally
```

##### 4. 练习

![image-20220923140236574](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923140236574.png)

![image-20220923142403085](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923142403085.png)

![image-20220923142854104](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923142854104.png)

输出

```java
1. ArrayIndexOutOfBoundsException 异常，可能会发生，如果没有配置 args[4] ，则数组指针超界异常
    如果不会，则输出 AA 或者 BB
2. 若 args[4] = null ，则 NullPointerException 异常
3. ClassCastException 异常，一定会发生，o 运行类型为字符串，编译类型不能向下转型为整数型
```

![image-20220923145354300](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923145354300.png)

输出

```
B
C
D
```

![image-20220923145921573](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923145921573.png)

输出

```
B
C
D
```

### 12. 包装类

针对八种基本数据类型相应的引用类型一包装类。有了类的特点，就可以调用类中的方法。

![image-20220923152220364](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923152220364.png)

##### 1. 装箱和拆箱

包装类和基本数据类型的相互转换

装箱:基本类型->包装类型，反之，拆箱

```java
1) jdk5前的手动装箱和拆箱方式：
    装箱：
    	包装类 对象名 = new 包装类(变量名)： Integer integer1 = new Integer(n1);
    	包装类 对象名 = 包装类.valueOf(变量名)： Integer integer2 = Integer.valueOf(n1);
    拆箱：
         数据类型 变量名 = 对象名.intValue() : int i = intrger.intValue();
2) jdk5以后(含jdk5)的自动装箱和拆箱方式：
    装箱：
        包装类 对象名 = 变量名 ： Integer integer3 = n1;  //底层还是调用 valueOf() 
    拆箱：
    	数据类型 变量名 = 对象名： int i = integer1;
3) 自动装箱底层调用的是valueOf方法，比如Integer.valueOf()
```

##### 2. 练习

![image-20220923194358806](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923194358806.png)

```java
1. 正确
2. 不同，上面输出 1.0，下面输出1
//因为三元运算符是一个整体，会把数据类型会自动转换为更高的，而 if——else 是分开的
```

##### 3. 包装类与String类的相互转换

```java
1. 包装类 -> String 类：以 Integer 为例
    1）  Integer i = 100;
		String str1 = i + "";  // i 本身没有变化，只是创造了一个 str1 对象
    2）  String str2 = i.toString();  //通过 toString() 输出
    3)	 String str3 = String.valueOf(i); //通过装箱

2. String 类 -> 包装类： Integer 为例
    1）  String str = "1234";
		Integer n1 = Integer.parseInt(str);
    2）  Integer n2 = new Integer(str); //通过构造器转换
    3）  Integer n3 = Integer.valueOf(str)  //通过装箱
```

##### 4. 包装类常用方法

![image-20220923201305871](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923201305871.png)

##### 5. Integer 面试题

![image-20220923201825218](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923201825218.png)

输出

```java
false   // i 和 j 是 new 出来的不同的对象，对象地址不同
true    // 底层代码为 Integer m = Integer.valueOf(1)，输入的参数在 -128-127 范围内，不用 new 对象
false   //同上
```

Integer.valueOf() 源码

![image-20220923202703767](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923202703767.png)

![image-20220923203712041](C:\Users\baymax\AppData\Roaming\Typora\typora-user-images\image-20220923203712041.png)

输出

```java
//示例一
false      // new 是不同的对象
//示例二
false      //同上
//示例三
true       // 底层是调用valueOf(),在范围内，不需要 new
//示例四
false      // 底层是调用valueOf(),不在范围内，需要 new
//示例五
false      //有 new
//示例六
true       //只要有基本数据类型，判断的是值
//示例七
true      //同上
```

