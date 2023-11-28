# 一、列表的格式
```python
[数据1, 数据2, 数据3, ...]
```
列表可以一次性存储多个数据，且可以不同类型。列表下标，默认从 0 开始

```python
l1 = [123, 345, 567]  
l2 = ["abc", "cde", "def"]  
l3 = [123, "abc"]  
  
print(type(l1))   # list
print(type(l2))   # list
print(type(l3))   # list
```

```python
# 获得数据  
# https://www.luogu.com.cn/problem/P1554  
s = input().split()  
  
k  = ""  
kk = ""  
  
for i in range(int(s[0]), int(s[1])+1):  
    k = str(i)  
    kk = kk + k  
print(kk.count("0"),kk.count("1"),kk.count("2"),kk.count("3"),kk.count("4"),kk.count("5"),kk.count("6"),  
        kk.count("7"),kk.count("8"),kk.count("9"))
```

列表的常见操作: 增、删、改、查

# 二、查找
## 下标
```python
l1 = [123, 345, 567, "abc"]  
print(l1[0])  
print(l1[1])  
print(l1[2])
```

## `index()` 返回指定数据所在位置的下标
```python
数据序列.index(数据，起点，终点)
```

```python
l1 = [123, 345, 567, "abc"]  
print(l1.index(345, 0, 3))  
print(l1.index(345555, 0, 3))
```

## `count()` 统计指定数据在当前列表中出现了多少次
## `len()` 计算指定列表的长度，即统计列表中元素的个数
```python
l1 = [123, 345, 567, "abc", 123]  
print(l1.count(123))  
print(f"列表l1中元素个数：{len(l1)}")
```

# 三、判断操作
### 1、`in` 判断指定数据是不是在列表中
```python
l1 = [123, 345, 567, "abc", 123]  
print(123 in l1)    # True
print("abc" in l1)  # True
print(666 in l1)    # True
```

### 2、`not in` 判断指定数据是不是 不存在 与列表中
```python
l1 = [123, 345, 567, "abc", 123]  
print(123 not in l1)    # False 
print("abc" not in l1)  # False
print(666 not in l1)    # True
```

```python
name_list = ["zhang3", "li4", "wang5", "zhao6"]  
  
name = input("请输入你的名字")  
if name in name_list:  
    print(f"你输入的名字是{name}，已经存在")  
else:  
    print(f"你输入的名字是{name}，不存在")
```


# 四、增加
增加指定数据到列表中
### 1、`append()`
```python
append(): 在列表的末位添加元素
列表序列.append(数据)
```

```python
name_list = ["zhang3", "li4", "wang5"]  
name_list.append("zhao6")  
name_list.append(12345)  
name_list.append(3.1415926)  
print(name_list)
```
**注意：** `append()` 添加数据到序列末位的时候，添加的是整个数据本身
### 2、`extend()` 
也是在序列的末位添加元素，当如果添加一个序列，着会将这个序列逐一的添加到末位
```python
序列列表.extend(数据)
```

```python
name_list = ["zhang3", "li4", "wang5"]  
name_list.extend("zhao6")  
name_list.extend(["12345", 3.14])  
print(name_list)
```

### 3、在指定的位置添加数据
```python
序列列表.insert(下标，元素)
```

```python
name_list = ["zhang3", "li4", "wang5"]  
name_list.insert(1, "zhao6")  
print(name_list)
```

# 五、删除操作
```python
del 目标
删除整个列表
```

```python
name_list = ["zhang3", "li4", "wang5"]  
print(name_list)  
del name_list   # 删除整个列表
print(name_list) # 列表被删除，再打印的话会报错
```

### 也可以删除指定元素
```python
name_list = ["zhang3", "li4", "wang5", "zhao6"]  
del name_list[1]  
print(name_list)
```

### 2、`pop()` 删除指定下标数据(默认是最后一个)，并返回该数据
```python
列表序列.pop(指定下标)
```

```python
name_list = ["zhang3", "li4", "wang5", "zhao6"]  
del_name = name_list.pop(1)  # 默认列表中下标是 1 的元素  
print(del_name)  
print(name_list)
```

```python
name_list = ["zhang3", "li4", "wang5", "zhao6"]  
del_name = name_list.pop()  # 默认删除列表的最后一个元素  
print(del_name)  
print(name_list)
```

### 3、`remove()` 移除列表中某个数据的第一个匹配项
```python
列表序列.remove(数据)
```

```python
name_list = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
name_list.remove("li4")  # 会删除序列在的第一个 "li4"print(name_list)
```

### 4、`clear()` 清空列表
```python
name_list = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
name_list.clear()  
print(name_list)
```

# 六、修改
## 1、根据下标修改数据

```python
name_list = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
name_list[0] = "66666"  
print(name_list)
```

## 2、翻转序列`reverse()`

```python
name_list = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
name_list.reverse()  
print(name_list)
```

## 3、排序
```python
序列列表.sort(key=None, reverse=False)

reverse: 表示排序规则
	True: 表示降序排序
	False: 升序排序，默认情况下是升序排序
```

```python
name_list = [1, 7, 2, 5, 0, 9, 6, 3, 4, 8]  
name_list.sort()  # 默认情况，升序排序  
print(name_list)  
name_list.sort(reverse=True) # 此时是降序排序  
print(name_list)
```

## 4、复制
```python
copy()
```

```python
name_list1 = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
name_list2 = name_list1.copy()  
print(name_list2)
```

# 七、遍历

### 1、`while` 遍历	
```python
name_list = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
  
i = 0  # 列表下标是从 0 开始的  
while i < len(name_list):  
    print(name_list[i], end=" ")  
    i += 1
```

## 2、`for` 遍历
```python
name_list = ["zhang3", "li4", "wang5", "zhao6", "li4"]  
for i in name_list:  
    print(i, end=" ")
```

# 八、列表嵌套
```python
name_list = [["小明", "小红", "小绿"], ["zhang3", "li4", "wang5"], [123, 456, 3.14]]  
print(name_list[0])  
print(name_list[1])  
print(name_list[2][1])
```

# 九、小练习

需求：8位老师，3个办公室， 将8位老师随机分配到3个办公室
步骤：
1. 准备数据
    * 8位老师 -- 列表
    * 3个办公室 - 列表嵌套

2. 分配老师到办公室
    * 随机分配
		就是把老师的名字写入到办公室列表 -- 办公室列表追加老师名字数据

3. 验证是否分配成功
	* 打印办公室详细信息：每个办公室的人数和对应的老师名字