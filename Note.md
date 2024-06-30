# JavaScript

# Day 1

## JavaScript介绍

### 1.1JavaScript是什么

JavaScript是运行在客户端（浏览器）的编程语言，实现人机交互的效果。作用有网页特效、表单验证、数据交互、服务端编程（node.js）

组成：

1. ECMAScript规定了基础语法：变量、分支语句、循环语句等...

![image-20240629233815248](C:\Users\LZH\AppData\Roaming\Typora\typora-user-images\image-20240629233815248.png)

### 1.2JS书写位置

1. 内部js

   1. 直接写在HTML文件中，用scirpt标签包住 **规范：script写在</body>上面**

   ![image-20240630002920847](C:\Users\LZH\AppData\Roaming\Typora\typora-user-images\image-20240630002920847.png)

2. 外部js

   1. 代码写在.js文件中 **注意：script标签中间无需写代码，会被忽略**

3. 行内js

   代码写在标签内部，Vue框架会使用这种模式

![image-20240630003507501](C:\Users\LZH\AppData\Roaming\Typora\typora-user-images\image-20240630003507501.png)

### 1.3基本语法

```
赋值语句：
	var x=1;
语句块：
	if (2 > 1) {
    x = 1;
    y = 2;
    z = 3;
}
注释：
行注释 //
块注释 /* ...*/

```

### 1.4数据类型

Number 

​	不区分整数和浮点数，统一用Number。

```
123 //整数123
0.789 //浮点数
-99 //负数
NaN //表示Not a Number,当无法计算结果时用NaN表示
Infinity //表示无限大，当数值超出Js的Number所能表示最大值
```

可以进行加减乘除和区域的运算

注意：

​	JavaScript中Number不区分整数和浮点数，即1.00==1。且最大整数范围±2的53次幂，不是63次幂。

```
打印Number能表示的最大整数
console.log(Number.MAX_SAFE_INTEGER)
```

字符串：

​	单引号或双引号括起来的任意文本。

布尔值：

​	布尔值和布尔代数的表示完全一致，一个值只有 **true**和**false**两种值。

比较运算符：

```
>
>=
== 
注意： ==有两种，第一种==比较，会自动转换数据类型再比较，可能得到诡异结果。
第二种===比较，不会自动转换数据类型，如果数据类型不一致，返回false，数据类型一致再进一步比较
！！所以坚持使用===进行比较

另外NaN与包括自己在内所有值不相等，想要判断就使用isNaN（）函数

浮点数的相等比较：
	由于计算机无法精确表示无限循环小数，导致浮点数计算过程中会产生误差。所以要比较两浮点数是否相等，只能计算它们之间差的绝对值，是否小于某个阈值。
	Math.abs(1/3-(1-2/3))<0.00000000001; //true
```

BigInt

​	要精确比2的53次幂还大的整数，要使用内置的BigInt类型，表示方法是在整数后加n，如8908098324092384092834n；也可用BigInt（）把Number和字符串转换成BigInt。

！！注意：使用BigInt可以进行加减乘除和取余，结果仍然是BigInt。但不能将Number和BigInt放一起运算。

```
console.log(1234567n+123245n) 
console.log(123456n+3424324) //Uncaught TypeError:Cannot mix BigInt and other types
```

null和undefined

​	null表示一个空值，区别于0和''，0是一个数值，''是一个空字符串。

​	undefined表示未定义，仅在判断函数参数是否传递的情况下有用。

数组

​	[1,1.2,true,null,'Hello'] 元素用，隔开。还可以用Array（）函数实现，如Array（1，1.1，'Hello'）

​	！！！出于对代码的可读性，建议直接用[]

​	数组的元素可以通过索引来访问，起始为0

对象

​	由键-值组成的无需集合，如：

```
var student = {
	name:'lzh',
	age:20,
	city:'BeiJing'
}
上述student对象定义了三个键值对，键成为对象的属性
要获取一个对象的属性，使用 对象变量.属性名的方式
```

变量

​	用变量名表示，变量名是大小写英文、数字、$和_的组合，不能由数字开头。变量名也不能是关键字。申明一个变量用var语句。

strict模式

```
var声明的变量不是全局变量，限制在函数体内
```

