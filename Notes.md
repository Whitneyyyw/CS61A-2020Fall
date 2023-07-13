# Lecture 1. Computer Science

A course about managing **complexity** 

- Mastering abstraction 抽象是计算机的核心思想之一

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

**CLI使用tips：**

查看当前目录：`cmd: dir`VS`powershell: ls`

进入家目录：`cd == cd ~`

`python -i test.py` 执行一遍`test.py`脚本，然后进入交互式命令【`-i` 参数】

`python3 -m doctest test.py` 用于运行`test.py`文档测试【`-m doctest` 参数】

`start .` 在资源管理器中打开当前文件夹

# Lecture 2. Functions

1. 所有类型的表达式都可以用call expression表达 -- Python可以看作一个calculator
2. Types of expressions: 
   - Primitive expressions: Number or Numeral, Name, String
   - Call expressions: Operator(Operand1, Oprand2, ...)
3. Name可以通过import/assignment/def来绑定

我现在的理解：

程序由一连串statements组成，本质是一个状态机，每一条statement会改变程序的状态——

statement由各种expression组成：有数字Number or Numeral、字符串String、函数调用Call expression，比较特殊的是名称Name（其实也是expression的一种），可以用来表示程序状态。

#### expression

- 表达计算，可以计算出值
- 可以嵌套
- call expressions的value比较特殊，需要将operator的值（function）应用在operand的值（parameter）上，最后得出的是return的值（默认返回None）

#### statement

- Assignment is a simple means of abstraction: binds names to values 将等式右边无论复杂简单表达式的值赋给等式左边Name类型的表达式；抽象的一种

  > Execution rule for assignment statements: 
  >
  > 1. Evaluate all expressions to the right of = from left to right.  
  > 2. Bind all names to the left of = to those resulting values in the current frame. 

- Function definition is a more powerful means of abstraction: binds names to expressions 函数定义将一个function赋给了一个Name类型；这个name对应的更为复杂，所以是更强大的抽象

  > **def <name>(<formal parameters>):**
  >
  > ​    **return <return expression>** 
  >
  > Execution procedure for def statements: 
  >
  > 1. Create a function with signature () 
  > 2. Set the body of that function to be everything indented after the first line  
  > 1. Bind <name> to that function in the current frame

#### Environment Diagrams

- Name -- Value
- An environment is a sequence of frames.  & create a new frame = create a new environment
- A name evaluates to the value bound to that name in the earliest frame of the current  environment in which that name is found.  & 往下传递、往上找；往上传递必须通过return语句，不可能往下找
- frame -- scope: 方便复用x、y、z、i、j等名称，如果没有作用域和别人合作非常容易冲突
- function放在objects里，我们关注指向同一对象是否有多个名称

#### python交互式界面

- 可以不需要调用`print()`函数，直接打印出expression的value
- 对于字符串，调用`print()`打印不显示引号，直接打印显示引号

#### Truthy and Falsey Values: 值的真假

- Python values such as `0`, `None`, `''` (the empty string), and `[]` (the empty list) are considered false values. *All* other values are considered true values.

- `short-circuit` / `not short-circuit`：一旦可以确定表达式的值就停下，返回计算的最后一个东西 （对于`and`和`or`）
- `not`：只有返回`True`或~