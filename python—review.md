# 一，数据类型

## （1）int：整数

## （2）float：浮点数

## （3）bool：布尔值

## （4）str：字符串

            [1]ASCII码

```python
s = 'a'
n = 100

print(ord(s))#返回s字符对应的ASCII数字
print(chr(n))#返回n数字对应的ASCII字符
```

            [2]format方法

```python
text = "{1} is {0} years old.".format(25, "Alice") #{}占位符替换
print(text)
```

```python
text = "{name} is {age} years old.".format(name="Bob", age=30)#关键词替换
print(text)
```

```python
n = 3.123456789
print("{}".format(n))
print("{:.2f}".format(n)) #保留两位小数
print("{:*^10.2f}".format(n)) #居中，保留十位位置，填充符为*，保留两位小数
```

            [3]字符串操作，见字符串方法.doc

```python
s = "Hello world"

s1 = s[0]#检索位置迭代器为1的字符
print(s1)

s2 = s[0:4]#检索[0,4)的字符
print(s2)

s3 = max(s)#寻找字符串中ASCII最大的字符
s4 = min(s)
s5 = len(s)#返回字符长度
print(s3,"\n",s4)

s6 = s.lower()#全变小写
s7 = s.upper()
s8 = s.split(" ")#分割
```

## （5）list：列表

            [1]索引切片同string

            [2]列表内置函数与方法

```python
ls = [1,5,89,56,78,2,4,6]

print(len(ls))
print(max(ls))
print(min(ls))
print(sum(ls))
print(sorted(ls))
```

```python
ls1 = ['a','b','c','d']
ls2 = ['1','2','3']

ls1.append('e')#在结尾添加字符'e'
print(ls1)

ls1.extend(ls2)#在结尾添加ls2
print(ls1)

ls1.insert(1,'s')#在位置1前插入‘s’
print(ls1)

ls1.extend(ls2)#在结尾添加ls2
print(ls1)
```

![](C:\Users\14598\AppData\Roaming\marktext\images\2025-05-13-12-10-49-460894430460c507530c4f8c686ca58.png)

            [3]map与split用法

```python
#map(应用函数，迭代对象)
number = [1,2,3,4,5]
sq = map(lambda x:x ** 2,number)
print(list(sq))
```

```python
def up(s):
    return s.upper()

word = ["hello","world","python"]
Word = list(map(up,word))
print(Word)
```

```python
#split 分割字符串
words = "Hello word python"
word = words.split()#默认按空白划分

print(word)
```

```python
s = "a,b,,c,,d"
n = [x for x in s.split(',') if x]#处理连续分隔符

print(n)
```



## （6）字典

            [1]创建

```python
student = {"name":"student1","number":0000}
#或者
student = dict(name="student1",number=0000)
```

            [2]访问与修改

```python
name = student["name"]
print(name)
print(student.get("name",'unknown'))#不存在是返回unknown

student["age"] = 20
print(student["age"])
print(student)

student["name"] = "student2"
print(student["name"])

del student["number"]
#student.pop("number")按键删除
#student.clear()清除字典
#student.key()返回所有键
#student.values()返回所有值
#student.items()返回所有键值对
#.update()合并字典
#.len()返回键值对数量
```







---

# 二、基础操作

## 1.数值运算

        +，-，*，/，//，%，**

## 2.逻辑判断

        and,or,not,>,<,>=,<=,==,!=

## 3.转义字符

        \,\',\",\n,\r,\\

## 4.输入输出

## （1）输入：input()

```python
n = input("请输入") #默认为str类型
```

## （2）输出：print()

        [1]%格式化输出：

```python
print("格式化字符串" % (值1, 值2, ...))
```

```python
name = "Bob"
age = 30
print("Name: %s, Age: %d" % (name, age))  # 输出: Name: Bob, Age: 
```

        [2]一般输出

```python
print(v1,v2...,sep='',end='')
#sep为间隔的字符，end为结尾之后的字符
```

# 三、控制结构

## 1.判断结构

（1）if

（2）if-else

（3）if-elif-else

```python
n = int(input())


if n > 10:
    print("n > 10")
elif n > 5:
    print("n <= 10 and n > 5")
esle:
    print("n <= 5")
```

## 2.循环结构

（1）while

```python
i = 0

while i < 10: #（当代码块判断为True时执行）
    print("正在循环第%d次"%i)
    i = i + 1
```

（2）for

        range迭代：range（a,b,n）从[a,b)步长为n的遍历，n默认1

```python
for i in range(10):#（从1开始到10遍历）
    print("i = %d"%i)
```

        list迭代：

```python
list1 = [5,8,6,2,4,3]

for i in list1:
    print(i,end='--')
```

        字符串迭代：

```python
s = 'python'

for i in s:
    print(i,end=' ')
```

（3）break与continue

break跳出循环执行循环下一轮的代码

continue跳过本轮循环

```python
for i in range(10):
    s += i
    print(s)
    if s > 15:
        break


for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
```

---

# 三、函数

## （1）函数的定义

```python
def f_name(x,y):
    for i in range(x,y,2):
        print(i)


x = int(input())
y = int(input())


f_name(x,y)
```

## （2）lambda函数

```python
m = lambda x,y:x ** 2 + y ** 2

print(m(3,4))
```



---

# 四、面对对象编程

```python
class book:
    def __init__(self,name,number,price,looking_number = 0):
        self.name = name
        self.looking_number = 0
        self.number = number
        self.price = price

    def looking(self,looking):
        self.looking_number += looking

    def discount(self,d):
        self.price *= d

n = input("请输入书名：")
num = int(input("请输入总页数："))
p = int(input("请输入原价："))

book1 = book(n,num,p)

d = float(input("请输入折扣"))

print("原价为：",book1.price)
book1.discount(d)
print("折扣后为：",book1.price)
```

---

# 五、Python文件

## （1）文件的读写与打开

file = open(文件名，mode = 'r',encoding = 'utf-8')


r 只读

w 覆盖写入

a 结尾追加

x 创建并写入

b 二进制写入

            [1]创建并写入

```python
s = ["hello","world","python"]

with open("1.txt","x",encoding="utf-8") as f:#创建并写入
    for i in s:
        f.write(i)
        f.write("\n")
```

```python
s = ["hello","world","python"]

f = open("1.txt","x",encoding="utf-8")
for i in s:
    f.write(i)
    f.write("\n")
```



             [2]读取

```python
lines = []
with open("1.txt","r",encoding="utf-8") as f:
    for line in f:
        lines.append(line)
        print(line,end="")

print(lines)
```

```python
with open("1.txt","r",encoding="utf-8") as f:
    line = f.readlines()

print(line)
```

示例讲解：

```python
import os.path
import sys

def main():
    # Prompt the user to enter filenames
    f1 = input("Enter a source file: ").strip()
    f2 = input("Enter a target file: ").strip()

    # Check if target file exists
    if os.path.isfile(f2):
        print(f2 + " already exists")
        sys.exit()

    # Open files for input and output
    infile = open(f1, "r")
    outfile = open(f2, "w")

    # Copy from input file to output file
    countLines = countChars = 0
    for line in infile:
        countLines += 1
        countChars += len(line)
        outfile.write(line)
    print(countLines, "lines and", countChars, "chars copied")

    infile.close()
    outfile.close()

main()
```

```python
def main():
    filename = input("Enter a filename: ").strip()
    infile = open(filename, "r")

    counts = 26 * [0]  # Create and initialize counts
    for line in infile:
        # Invoke the countLetters function to count each letter
        countLetters(line.lower(), counts)

    # Display results
    for i in range(len(counts)):
        if counts[i] != 0:
            print(chr(ord('a') + i) + " appears " + str(counts[i])
                  + (" time" if counts[i] == 1 else " times"))

    infile.close()

# Count each letter in the string
def countLetters(line, counts):
    for ch in line:
        if ch.isalpha():
            counts[ord(ch) - ord('a')] += 1

main()
```

csv与excal放在下一节数据分析与pandas中

---

# 六、数据处理

## （1）pandas库

            [1]创建

```python
#series一维数据
import pandas as pd

d = [11,22,33,44,55]
i = ['a','b','c','d','e']

s = pd.Series(data=d,index=i)
print(s)
```

```python
#多维数据
import pandas as pd

score = {'数学':[10,20,30],'语文':[40,50,60],'英语':[70,80,90]}
name = ['1号','2号','3号']

df = pd.DataFrame(data=score,index=name)

print(df)
```

```python
#csv,excel读入
import pandas as pd
df = pd.read_excel("DoubanTest.xls")
print(df)
df.to_csv("DoubanTest.csv")#导出为csv格式
```

            [2]数据查看

```python
import pandas as pd
da = {'name':["苹果","香蕉","梨子","山竹","西瓜","橘子","菠萝"],
      'price':[10    ,20   ,15   ,80   ,12   ,18   ,22],
      'color':['红色','黄色','黄色','黑色','绿色','橙色','黄色']}

df = pd.DataFrame(da)

print(df) 
```

```python
df.head(n)       # 查看前n行
df.tail(n)       # 查看后n行
```

```python
df.shape         # 行列数
df.info()        # 数据信息
```

```python
df.describe()    # 统计摘要
df.dtypes        # 列数据类型
df.columns       # 列名
df.index         # 索引
df.values        # 数据值数组
```

```python
df.dropna(inplace=True)#删除含缺失值的行
df.fillna(value=0, inplace=True)#填充缺失值
df.drop_duplicates(inplace=True)#删除重复行
```

            [3]数据选择

```python
#列选择
print(df[['name','price']])
#行选择
print(df.iloc[2]]
print(df.loc[0:10,'name'])
#条件选择
print(df[df['price'] > 15])
```

            [4]数据添加与删除

```python
#添加列
df['重量'] = (20,30,10,50,20,33,40)
print(df)
```

```python
#添加行
new_fruit = pd.DataFrame({'name':['椰子'],'price':[35],'color':['棕色']})
df = pd.concat([df,new_fruit],ignore_index=True)

print(df)
```

```python
#删除行
df.drop(1,axis=0,inplace=True)
print(df)
```

```python
#删除列
df.drop('color',axis=1,inplace=True)
print(df)
```
