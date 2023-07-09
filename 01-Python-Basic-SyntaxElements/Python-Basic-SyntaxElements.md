# 1. 基本语法元素

![image-20230222091921263](https://bucket-zly.oss-cn-beijing.aliyuncs.com/img/Typora/202303102105374.png)



---

## 1.1 数据类型

### 1.1.1 基本类型：数字、字符串、布尔

1. 数字

   ​		int 整型---整数

   ​		float 浮点型---带小数的数

   ​		complex 复数---a+bj

2. 字符串

   ```python
   "python123asdf"
   ```

3. 布尔类型

   ```python
   y = 2 > 1
   print(y)
   ```

### 1.1.2 组合类型：列表、元组、字典、集合

1. 列表

   ```python
   list1 = [1, 2, 3, 4]
   print(list1[0]) # 1
   list1[0] = 7
   print(list1[0]) # 7
   ```

   列表中的元素可以进行修改

2. 元组

   ```python
   tuple1 = (1, 2, 3, 5)
   ```

   元组中的元素不支持修改

3. 字典

   通过“键：值” 的映射实现数据存储和查找

   ```python
   dict1 = {key1 : value1, key2 : value2, ...}
   student = {2001: "小明", 2002: "小张", 2003: "小红"}
   print(student[2002])
   ```

   字典是无序的

4. 集合

   一系列互不相等元素的集合，内部也是无序的

   ```python
   student_set = {"小红", "小张", "小明", "小红"}
   print(student_set) # {"小张", "小红", "小明"}
   ```

   

---

## 1.2 变量

### 1.2.1 变量的概念

实实在在的对象：如数据、抽象

可变性：增删改查等

变量定义二要素：变量名、赋值

```python
x = 1
```

### 1.2.2 变量的命名

![image-20230222154840152](https://bucket-zly.oss-cn-beijing.aliyuncs.com/img/Typora/202303102105905.png)

- 可以用来做变量名

  - 大写字母、小写字母、数字、下划线、汉字及其组合
  - 严格区分大小写

- 不可以用来做变量名

  - 首字符不允许是数字

  - 变量名中间不能有空格

  - 不能与33个python保留字相同

    ![image-20230222094931161](https://bucket-zly.oss-cn-beijing.aliyuncs.com/img/Typora/202303102105388.png)

### 1.2.3 变量名定义技巧

- 变量名尽可能有实际意义，表征数据的某种特性

  ```python
  age_of_student = [13, 14, 17]
  ```

- 下划线（推荐：变量名和函数名）变量名由多个单词组成，用_连接多个单词

  ```python
  age_of_student = [13, 14, 17]
  ```

- 驼峰体（推荐：类名）变量名由多个单词组成，单词首字母大写

  ```python
  AgeOfStudent
  ```

- 尽量避免用中文和拼音作变量名

- 特殊的变量：常量（Π、e）变量名所有字母均为大写

  ```python
  MAX_ITERATION = 1000
  ```

### 1.2.4 变量的赋值

1. 一般赋值

   通过等号自右向左进行赋值

   ```python
   x = 1 + 2
   ```

2. 增量赋值

   ```python
   x = 10
   x = x + 10
   x += 10
   ```

3. 打包赋值

   ```python
   x, y = 1, 2
   print(x, y) # 1, 2
   x, y = y, x
   print(x, y) # 2, 1
   ```



---

## 1.3 控制流程

### 1.3.1 顺序流程

自顶向下依次执行

```python
# 实现1-5的整数求和
res = 0
res += 1
res += 2
res += 3
res += 4
res += 5
print(res)
```

### 1.3.2 循环流程——遍历循环（for）

从可迭代对象中，一次取出每一个元素，并进行相应的操作

```python
# 实现1-5的整数求和
res = 0
for i in [1, 2, 3, 4, 5]:
    res += i
print(res)
```

### 1.3.3 循环流程——无限循环（while）

```python
# 实现1-5的整数求和
res = 0
i = 0
while i <= 5:
    res += i
    i += 1
print(res)
```

### 1.3.4 分支流程（if）

```python
age = 18
if age > 22:
    print("age > 22")
else:
    print("age < 22")
```



---

## 1.4 输入输出

### 1.4.1 数据从哪里来

1. 外部文件导入

   - 从本地硬盘、网络端读入
   - 该部分在【文件、异常和模块】

2. 程序中定义

   ```python
   age = 18
   ```

3. 动态交互输入input

   ```python
   x = input("请输入一个数字：")
   print(type(x)) # str
   print(x)
   ```

4. eval()去掉引号

   ```python
   x = eval(input("请输入一个数字"))
   print(type(x)) # int
   print(x)
   ```

### 1.4.2 数据到哪里去

1. 存储到本地硬盘或网络断端

   - 该部分在【文件、异常和模块】

2. 打印输出 print

   - 直接打印数据

     ```python
     print("dasfdsgdg ")
     ```

   - 打印变量

     ```python
     x = 124
     print(x)
     ```

   - 简单的组合打印

     ```python
     PI = 3.14
     E = 2.71
     print("PI = ", PI, "E = ", E)
     ```

     

   - print 默认换行

   - 换行控制 end=

     ```python
     print(123, end = "留在这里")
     print(345) # 123留在这里345
     ```

3. 格式化输出方法 format

   - 基本格式："字符{0}字符{1}字符".format(v0, v1)

     ```python
     PI = 3.14
     E = 2.71
     print("PI = {0}, E = {1}".format(PI, E)) # PI = 3.14, E = 2.71
     print("PI = {0}, E = {0}".format(PI, E)) # PI = 3.14, E = 3.14
     print("PI = {1}, E = {0}".format(PI, E)) # PI = 2.71, E = 3.14
     ```

   - 填充输出

     ```python
     # _____3.1415926535_______ 进行填充
     PI = 3.1415926535
     print("{0:_^20}".format(PI)) # ____3.1415926535____
     print("{0:*<30}".format(PI)) #3.1415926535******************
     ```

   - 数字千分位分隔符

     ```python
     print("{0:,}".format(100000000)) # 100,000,000
     print("{0:&>20,}".format(100000000)) # &&&&&&&&&100,000,000
     ```

   - 浮点数简化输出

     - 留两位小数

       ```python
       PI = 3.1415926535
       print("{0:.2f}".format(PI)) # 3.14
       ```

     - 按百分数输出

       ```python
       print("{0:.1%}".format(0.8979671256)) # 89.8%
       ```

     - 科学计数法输出

       ```python
       print("{0:.2e}".format(0.897189625)) # 8.97e-01
       ```

   - 整数的进制转换输出

     十进制整数转二进制、Unicode编码、十进制、八进制、十六进制输出

     ```python
     print("二进制{0:b}, Unicode码{0:c}, 十进制{0:d}, 八进制{0:o}, 十六进制{0:x}".format(450)) 
     # 二进制111000010, Unicode码ǂ, 十进制450, 八进制702, 十六进制1c2
     ```

   ![image-20230222153622559](https://bucket-zly.oss-cn-beijing.aliyuncs.com/img/Typora/202303102105409.png)



---

## 1.5 程序格式

1. 行最大长度

   所有行限制的最大字符数为79

2. 缩进

   - 用缩进来表示语句间的逻辑
   - 在 for while if def class等: 之后下一行开始进行缩进，表明后续代码与前句之间的从属关系
   - 缩进量：4字符

3. 使用空格

   - 二元运算符两边加一个空格

     ```python
     x = 2
     y > 3
     x += 4
     ```

   - 使用不同优先级的运算符，考虑在最低优先级的运算符周围添加空格

     ```python
     x = x*2 - 1
     y = (a+b) * (a-b)
     ```

   - 在逗号后使用空格

   - 不要使用一个以上的空格

4. 避免使用空格

   在制定关键字参数或者默认参数值的时候，不要在 = 附近加空格

   ```python
   def fun(n=1, m=2):
       print(n, m)
   ```

5. 注释

   - 单行注释

     ```python
     x = 1 # 这是注释
     ```

   - 多行注释

     ```python
     """
     safhuidosf
     fsdfgdsg
     qwyfh
     """
     ```

