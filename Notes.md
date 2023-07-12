# Lecture 1. Computer Science

A course about managing **complexity** 

- Mastering abstraction

> Abstraction: You've giving a name to something that's complicated  and not worrying about its parts.

- Programming paradigms

Functions; Values; Objects; Interpreters; Data

> **PEMDAS**
>
> 是一个记忆法则，用于帮助记住运算顺序，特别是在解决复杂的数学表达式时。它是以下单词的首字母缩写：
>
> - P：括号 (Parentheses)
> - E：指数 (Exponents)
> - MD：乘法和除法 (Multiplication and Division)
> - AS：加法和减法 (Addition and Subtraction)
>
> PEMDAS规定了一系列运算的顺序，按照这个顺序执行计算可以确保结果的准确性。具体规则如下：
>
> 1. 首先计算括号中的表达式。
> 2. 接下来计算指数运算。
> 3. 然后按照从左到右的顺序依次执行乘法和除法运算。
> 4. 最后按照从左到右的顺序依次执行加法和减法运算。
>
> 例如，考虑以下数学表达式：2 + 3 × 4 - (6 ÷ 2)

查看当前目录：`cmd: dir`VS`powershell: ls`

进入家目录：`cd == cd ~`

`python -i test.py` 执行一遍`test.py`脚本，然后进入交互式命令

`python3 -m doctest test.py` 用于运行`test.py`文档测试

`start .` 在资源管理器中打开当前文件夹

# Lecture 2. Functions

1. calculator: call expression
2. Types of expressions: 
   - Primitive expressions: Number or Numeral, Name, String
   - Call expressions: Operator(Operand1, Oprand2, ...)
3. name可以通过import/assignment/ def来绑定
4. Environment Diagrams:
   - Name -- Value
   - An environment is a sequence of frames.  
   - A name evaluates to the value bound to that name in the earliest frame of the current  environment in which that name is found. 

我现在的理解：

程序由一连串statements组成，本质是一个状态机，每一条statement会改变程序的状态——

statement由各种expression组成：有数字Number or Numeral、字符串String、函数调用Call expression，比较特殊的是名称Name（其实也是expression的一种），可以用来表示程序状态。

**expression**

- 表达计算，可以计算出值
- 可以嵌套
- call expressions的value比较特殊，需要将operator的值（function）应用在operand的值（parameter）上才能得出
- function也是一种express

**statement**

- Assignment is a simple means of abstraction: binds names to values 就是将等式右边表达式的值赋给等式左边Name类型的表达式
- Function definition is a more powerful means of abstraction: binds names to expressions 函数调用是一种特殊的表达式