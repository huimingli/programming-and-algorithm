# Week8

## 赋值运算

要点一：两边类型不同

- 类型转换
- 不管右边是什么类型，都转换成左边的类型

要点二：长数赋给短数

- 截取长数的低位给短数

要点三：短数赋给长数

- 数不变
- 但二进制表示的改变因短数不同而不同，详见PPT

要点四：符号位的赋值处理

- 直接赋值

## 赋值运算的说明

表达式

- 程序中有运算符、操作数和括号组成等所组成的计算式，是计算求值的基本单位
- 赋值语句的值：通过赋值符号所传送的值

## 算术运算

计算过程中的类型转换

### 自增运算符

`++` `--` 只能用于变量

```c++
cout << -i++ << endl; // -3
cout << -++i << endl; // -4
cout << (-i)++ <<endl; // compile error
cout << ++i++ << endl; // compile error
```

`cout`语句中如果有多个表达式，优先计算右边的

```c++
int main()
{
	int a  = 0, b = 0, c = 2, d = 0, e = 2, f = 2;
	cout << a << " " << a++ << " " << endl; // 1，0
	cout << ++b << " " << b++ << " " << endl; // 2，0
	cout << c << " " << (c++) + (++c) << " " << endl; // 4,6 先计算前置++
	cout << (d = f++) + (e = f) << endl; // 4 最后计算后置++
  	cout << f << " " << d << " " << e << endl; // 3,2,2
}
```

## 关系运算

不等式的优先级大于等式（包括`!=`）

算术运算符>关系运算符>赋值运算符

## 逻辑运算

运算优先级：`!` > `&&` > `||`

`!` > 算术运算符> 关系运算符 > `&&` > `|| ` > 赋值运算符

逻辑表达式求解中，并不总是执行所有的运算，只有在必须执行下一个逻辑运算符才能求出表达式的解时，才执行该运算符

```c++
int main()
{
	int i = 0, a = 1, b = 2, c = 3;
  	i = ++a || ++b || ++c;
  	cout << i << a << b << c << endl; // 1 2 2 3
  	return 0;
}
```

## 逗号，条件，强转

### 逗号运算

运算优先级最低

用逗号将两个表达式连起来

`表达式1, 表达式2, 表达式3, ..., 表达式n`

整个表达式的值为`表达式n`

### 条件运算

`表达式1 ? 表达式2 : 表达式3`

### 强制类型转换

`(类型名) (表达式)`

强制类型转换后，被转换的量的类型并没有改变

## 位运算

详见PPT