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
### 1.3. 类图说明：
## 2. 图书管理系统的对象图
### 2.1类user的对象图
#### 源码如下：
```
```
#### 对象图如下：
### 2.2 类...的对象图
#### 源码如下：
```
```
#### 对象图如下:
