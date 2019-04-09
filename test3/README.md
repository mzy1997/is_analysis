# 实验3：图书管理系统领域对象建模
|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|
## 1.图书管理系统的类图
### 1.1类图PlantUML源码如下：
```
@startuml
abstract class 馆藏资源品种{
-资源名称： String
-国际出版号: int
-价格: double
-简介: String
-馆藏数量: int
-可借数量: int
-Create()
-Insert()
-Find()
-Delete()
-Update()
-ShowAll()
}

class 资源项{
-馆藏流水号: int
-状态: Boolean
}

class 碟片品种{
-碟片类型 : String
-碟片数: int
-制作公司: String
-Create()
-Insert()
-Find()
-Delete()
-Update()
-ShowAll()
}

class 图书品种{
-作者: String
-出版社: String
-出版日期: Date
-Create()
-Insert()
-Find()
-Delete()
-Update()
-ShowAll()
}

class 馆藏目录{
-目录名
}

class 预定记录{
-预定日期: Date
-Create()
-Find()
-Delete()
}

class 读者{
-姓名: String
-身份证号: String
-借书卡号: int
-图书限额: int
-已借图书数: int
-碟片限额: int
-已借碟片数: int
-Create()
-Insert()
-Find()
-Delete()
-Update()
-ShowAll()
}

class 借书记录{
-借书日期: Date
-归还日期: Date
-Create()
-Delete()
-Update()
}

class 图书管理员{
-职工号: int
-姓名: String
-Create()
-Delete()
-Update()
-resetPword()
}

class 逾期记录{
-逾期天数: int
}

class 罚款细则{
-金额
-countMoney()
}
馆藏资源品种 "1..*" -left- "    1" 馆藏目录
馆藏资源品种 "1"*-right-"*" 资源项:has
馆藏资源品种 <|-down- 碟片品种
馆藏资源品种 <|-down- 图书品种
馆藏资源品种 "1"-up-"*" 预定记录:被预定
资源项 "1"-down-"0..1" 借书记录
预定记录 "*"-right-"1" 读者
读者 -left- 借书记录
借书记录 "               1"--"0...1" 逾期记录
逾期记录 -left- "0..1"罚款细则:使用
借书记录 "*"--"1" 图书管理员:登记
@enduml
```
### 1.2. 类图如下：
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/lib_Class.png" />

### 1.3. 类图说明：
1.一个馆藏目录可能有一个或多个馆藏资源品种\n
2.馆藏资源品种包含资源项，是抽象类，图书品种、碟片品种是其子类\n
3.一个馆藏资源品种可以有0个或多个预定记录;\n
4.每个读者可以有0个或多个预定记录;\n
5.一个借书记录可以有0个或1个逾期记录;\n
6.每个图书管理员登记0个或多个借书记录;\n
7.每个资源项有0个或一个借书记录;\n
8.每位读者0个或多个与前期记录对应有0个或1个罚款细则;\n
## 2. 图书管理系统的对象图
### 2.1类读者的对象图
#### 源码如下：
```
object 读者{
姓名:本尼迪克特
身份证号:5110241997....0371
借书卡号:123456789
图书限额:10
已借图书数:2
碟片限额:5
已借碟片数:1
}
```
#### 对象图如下：
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/object3.png" />

### 2.2 类图书的对象图
#### 源码如下：
```
object 图书品种{
资源名称:平凡的世界
国际出版号:9787530216774
价格:26
简介:劳动与爱情，挫折与追求，痛苦与欢乐，
日常生活与巨大社会冲突，纷繁地交织在一起，
深刻地展示了普通人在大时代历史进程中所走过的艰难曲折的道路
馆藏数量:30
可借数量:27
作者:路遥
出版社:北京十月文艺出版社
出版日期:1986-12
}
```
#### 对象图如下:
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/object1.png" />

### 2.3 类碟片的对象图
#### 源码如下：
```
object 碟片品种{
资源名称:泰坦尼克号
国际出版号:9787530216774
价格:50
简介:影片以1912年泰坦尼克号邮轮在其处女启航
时触礁冰山而沉没的事件为背景，讲述了处于不同阶
层的两个人穷画家杰克和贵族女露丝抛弃世俗的偏见坠入爱河，
最终杰克把生命的机会让给了露丝的感人故事。
馆藏数量:10
可借数量:8
碟片类型:Romance
碟片数:10
制作公司:福斯电影公司
}
```
#### 对象图如下:
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/object2.png" />

### 2.4 类图书管理员的对象图
#### 源码如下：
```
object 图书管理员{
职工号:001
姓名:康伯巴奇
}
```
#### 对象图如下:
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/object4.png" />

### 2.5 类借书记录的对象图
#### 源码如下：
```
object 借书记录{
借书日期:2019-4-9
归还日期:2019-5-9
}
object 逾期记录{
逾期天数:10
}
object 罚款细则{
金额:20
}
借书记录 *--"0..1"逾期记录
逾期记录 *--"1"罚款细则
```
#### 对象图如下:
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/object5.png" />

### 2.6 类预定记录的对象图
#### 源码如下：
```
object 预定记录{
预定日期:2019-3-9
}
object 资源项{
馆藏流水号:45646477
状态:true
}
预定记录 o--"*"资源项
```
#### 对象图如下:
<img src="https://github.com/mzy1997/is_analysis/blob/master/test3/object6.png" />
