# C++ 

## 基础

1.数组指针和指针数组

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200330201046.png)

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200330201111.png)

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200330201147.png)

2.const 限定符

解决魔数、神秘数字问题

```c++

	const int bufSzie = 512;
	// 定义bufsize取代512
	for (int i=0;i!=512;i++)  // 512 称之为魔数
	{
		
	}

```

变量有可能被修改，定义为const修饰，则不能被修改了

const修饰必须初始化

3.extern：extern关键字声明一个变量或函数，并指定它具有外部链接

```c++
/* test.c */
#include <stdio.h>
 
int etn = 100;
 
void layout()
{
    printf("test.c: The etn is %d\n", etn);
}
/* main.c */
#include <stdio.h>
 
extern int etn;
 
int main()
{
    layout();
    printf("main.c: The etn is %d\n", etn);
    return 0;
}
```

## 引用

1.使用 & 符号

2.引用就是别名

定义时进行初始化

```c++
int var=100;
int &b=var;
```

变量的别名

3非const 引用

只能指向同类型的

4.const 引用

```c++
const int iVar = 100;
const int &iVar1 = iVar;
```

可以指向不同类型，可以指向右值（字面量）

传递函数的参数

## 枚举

1.定义枚举--enum

枚举都是常量

```c++
enum XXX
{
	A = 1,
	B,
	C,
	D
};
```

2.枚举常用

## 类类型

1.class 修饰

2.设计新的类型

接口

实现

3.类成员

数据成员

类的操作：成员函数

4.封装、继承、多态

5.class 默认私有

6.struct 默认公有

## 标准库

### string

string字符串类型

1.四种初始化方法

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200330224729.png)

cout<<s2<<endl;  string类型

cout<<“test”<<endl;   隐含 /0 C风格字符串

2.getline 读取完整一行

cin：读取并忽略有效字符之前的空白，读取字符直到下一个空白

getline：读取整行，直到读到换行符

size()操作

用string：：size_type size size 接收

```c++
string str("test");
	str.size(); // 获取字符串大小
	string::size_type size = str.size();  // 定义变量来接收
为string专门设计的类型
```

3.string对象中字符的处理

### bitset

 ## 指针

void *p ： 万能指针，用处不多

声明时可以不初始化，可以通过赋值

引用一旦声明就必须初始化

引用一个对象后不能改变

## C风格字符串

​	string str("123");
​	const char *str2 = str.c_str();

转换时必须有const限定符

## 数组与vector

