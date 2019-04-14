# 实验四:图书管理系统顺序图绘制
|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|

## 图书管理系统的顺序图
### 1.借书用例
#### 1.1借书用例PlantUML源码
```
@startuml
title 借书顺序图

actor 图书管理员
participant 读者
participant 资源项
participant 馆藏资源品种
participant 借书记录
activate 图书管理员
图书管理员 -> 读者 :取读者消息
note left:消息
activate 读者
读者 -> 图书管理员 :返回读者信息
deactivate 读者
alt 读者有资格借书
图书管理员->资源项:获取资源项
activate 图书管理员
activate 资源项
资源项->馆藏资源品种:查找资源品种
deactivate 资源项
activate 馆藏资源品种
馆藏资源品种->馆藏资源品种:减少可借额度
馆藏资源品种-->图书管理员:返回具体信息
deactivate 馆藏资源品种
deactivate 图书管理员
图书管理员 -> 借书记录 :修改读者借书情况
activate 借书记录
借书记录 ->图书管理员 :借书信息
deactivate 借书记录
note left:返回消息
图书管理员->读者:减少可借额度
activate 读者
读者-->图书管理员
deactivate 读者
deactivate 图书管理员
else 读者没有资格借书
图书管理员->读者:拒绝消息
end
@enduml
```
#### 1.2借书用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" />

#### 1.3借书用例顺序图说明
图书管理员查询读者信息，判断读者是否有借书资格(是否注册、读者自身是否有可借额度、读者所借图书是否有可借额度)。如果读者有资格借书，图书管理员根据资源项获取到具体图书的对象，该对象通过自身方法减少自身可借额度并向图书管理员返回相关信息。图书管理员再根据读者查询到借书记录，并进行修改操作，最后获取到读者的对象，减少读者的可借额度。如果读者没有资格借阅，图书管理员向读者发送一个拒绝消息。
### 1.借书用例
#### 1.1借书用例PlantUML源码
```
```
#### 1.2借书用例顺序图


#### 1.3借书用例顺序图说明
