# 实验四:图书管理系统顺序图绘制
|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|

## 图书管理系统的顺序图
### 1.借书用例
#### 1.1借书用例PlantUML源码
```
@startuml
title 借书
actor 图书管理员
participant 读者
participant 资源项
participant 馆藏资源品种
participant 借书记录

activate 图书管理员
图书管理员 ->读者:验证读者
activate 读者
deactivate 读者
alt 读者有借书资格
图书管理员->读者:取读者限额
activate 读者
deactivate 读者
loop
图书管理员->资源项:获取资源项
activate 资源项
资源项->馆藏资源品种:查找资源品种
activate 馆藏资源品种
deactivate 馆藏资源品种
图书管理员->借书记录:创建借书记录
activate 借书记录
deactivate 借书记录
图书管理员->资源项:借出资源
资源项->馆藏资源品种:减少可借数量
activate 馆藏资源品种
deactivate 馆藏资源品种
deactivate 资源项
图书管理员->读者:减少可用限额
activate 读者
图书管理员->读者:借书成功
deactivate 读者
end
图书管理员->借书记录
activate 借书记录
deactivate 借书记录
else 读者没有借书资格
图书管理员->读者:借书失败
activate 读者
deactivate 读者
end
deactivate 图书管理员
@enduml
```
#### 1.2借书用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test4/lib.seq.borrow.png" />

#### 1.3借书用例顺序图说明
图书管理员查询读者信息，判断读者是否有借书资格(是否注册、读者自身是否有可借额度、读者所借图书是否有可借额度)。如果读者有资格借书，图书管理员根据资源项获取到具体图书的对象，该对象通过自身方法减少自身可借额度并向图书管理员返回相关信息。图书管理员再根据读者查询到借书记录，并进行修改操作，最后获取到读者的对象，减少读者的可借额度。如果读者没有资格借阅，图书管理员向读者发送一个拒绝消息。
### 2.图书信息维护用例
#### 2.1图书信息用例PlantUML源码
```
@startuml
title:图书信息维护
actor 图书管理员
participant 资源项
participant 馆藏资源品种

== 查看图书信息 ==
图书管理员->资源项:获取资源项
activate 图书管理员
activate 资源项
资源项->馆藏资源品种:查找资源品种
deactivate 资源项
activate 馆藏资源品种
馆藏资源品种-->图书管理员:返回具体信息
deactivate 馆藏资源品种
deactivate 图书管理员

== 增加图书信息 ==
图书管理员->资源项:传入数据
activate 图书管理员
activate 资源项
资源项->资源项:add
activate 资源项 #DarkSalmon
资源项->馆藏资源品种:传入数据
activate 馆藏资源品种
deactivate 资源项
馆藏资源品种->馆藏资源品种:add
activate 馆藏资源品种 #DarkSalmon
馆藏资源品种-->资源项
deactivate 馆藏资源品种
deactivate 馆藏资源品种
资源项-->图书管理员:增加成功
deactivate 资源项
deactivate 图书管理员
note left:message

== 修改图书信息 ==
图书管理员->资源项:获取资源项
activate 图书管理员
activate 资源项
资源项->馆藏资源品种:查找资源品种
deactivate 资源项
activate 馆藏资源品种
馆藏资源品种-->图书管理员:返回具体信息
deactivate 馆藏资源品种
图书管理员->资源项:修改
activate 资源项
资源项->资源项:update
资源项->馆藏资源品种
activate 馆藏资源品种
馆藏资源品种->馆藏资源品种:update
馆藏资源品种-->资源项
deactivate 馆藏资源品种
资源项-->图书管理员:修改成功
deactivate 资源项
note left:message
deactivate 图书管理员

== 删除图书信息 ==
图书管理员->资源项:获取资源项
activate 图书管理员
activate 资源项
资源项->馆藏资源品种:查找资源品种
deactivate 资源项
activate 馆藏资源品种
馆藏资源品种-->图书管理员:返回具体信息
deactivate 馆藏资源品种
图书管理员->资源项:删除
activate 资源项
资源项->资源项:delete
资源项->馆藏资源品种
activate 馆藏资源品种
馆藏资源品种->馆藏资源品种:delete
馆藏资源品种-->资源项
deactivate 馆藏资源品种
destroy 馆藏资源品种
资源项-->图书管理员:删除成功
deactivate 资源项
deactivate 图书管理员
note left:message
@enduml
```
#### 2.2图书信息维护用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test4/lib.seq.bookinfo.png" />

#### 2.3图书信息维护用例顺序图说明
##### 2.3.1查看图书信息
图书管理员通过资源项数据获得具体图书信息。
##### 2.3.2增加图书信息
图书管理员为资源项对象传入数据，资源项再将数据传给馆藏资源品种，最后返回增加成功消息。
##### 2.3.3修改图书信息
图书管理员先查询到资源项与馆藏资源品种信息，再通过其自身的update方法做出修改操作，最后返回修改成功消息。
##### 2.3.4删除图书信息
图书管理员先查询到资源项与馆藏资源品种信息.再通过其自身的delete方法做出删除操作，最后返回删除成功消息
### 3.读者信息维护用例
#### 3.1读者信息维护用例PlantUML源码
```
@startuml
title:读者信息维护
actor 图书管理员
participant 读者
participant 借书记录
participant 逾期记录
== 查看读者信息 ==
图书管理员->读者:取读者信息
activate 图书管理员
activate 读者
读者->借书记录
activate 借书记录
借书记录->逾期记录
activate 逾期记录
读者-->图书管理员
借书记录-->读者
deactivate 读者
逾期记录-->借书记录
deactivate 借书记录
deactivate 逾期记录
deactivate 图书管理员
== 增加读者信息 ==
图书管理员->读者:输入读者信息
activate 图书管理员
activate 读者
读者-->图书管理员:创建成功
note left:message
deactivate 读者
deactivate 图书管理员

== 修改读者信息 ==
图书管理员->读者:取读者信息
activate 图书管理员
activate 读者
读者->借书记录
activate 借书记录
借书记录->逾期记录
activate 逾期记录
读者-->图书管理员
借书记录-->读者
deactivate 读者
逾期记录-->借书记录
deactivate 借书记录
deactivate 逾期记录
图书管理员->读者:update
activate 读者
读者->借书记录
activate 借书记录
读者->读者:update
借书记录->逾期记录
activate 逾期记录
借书记录->借书记录:update
逾期记录->逾期记录:update
逾期记录-->借书记录
deactivate 逾期记录
借书记录-->读者
deactivate 借书记录
读者-->图书管理员:修改成功
deactivate 读者
deactivate 图书管理员

== 删除读者信息 ==
图书管理员->读者:取读者信息
activate 图书管理员
activate 读者
读者->借书记录
activate 借书记录
借书记录->逾期记录
note right:此功能包括读者\n因为多次逾期而\n被拉黑的功能
activate 逾期记录
读者-->图书管理员
借书记录-->读者
deactivate 读者
逾期记录-->借书记录
deactivate 借书记录
deactivate 逾期记录
图书管理员->读者:delete
activate 读者
读者->借书记录
activate 借书记录
读者->读者:delete
借书记录->逾期记录
activate 逾期记录
借书记录->借书记录:delete
逾期记录->逾期记录:delete
逾期记录-->借书记录
deactivate 逾期记录
destroy 逾期记录
借书记录-->读者
deactivate 借书记录
destroy 借书记录
读者-->图书管理员:删除成功
deactivate 读者
destroy 读者
deactivate 图书管理员
@enduml
```
#### 3.2读者信息维护用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test4/lib.seq.userinfo.png" />

#### 3.3读者信息维护用例顺序图说明
##### 3.3.1查看读者信息
图书管理员根据读者数据取得读者信息、其借书记录、逾期记录。
##### 3.3.2增加读者信息
图书管理员录入读者信息，读者对象返回创建成功的消息。
##### 3.3.3修改读者信息
图书管理员先取得读者信息、其借书记录、逾期记录，再调用其自身的update方法进行修改操作，最后得到修改成功的消息。
##### 3.3.4删除读者信息
图书管理员先取得读者信息、其借书记录、逾期记录，再调用其自身的delete方法进行删除操作，最后得到删除成功的消息。

### 4.读者查询用例
#### 4.1读者查询用例PlantUML源码
```
@startuml
title:读者查询
actor 读者
participant 资源项
participant 馆藏资源品种
participant 借书记录
participant 逾期记录
participant 预定记录

alt 读者有权限查询
== 查看图书信息 ==
读者->资源项:取资源项信息
activate 读者
activate 资源项
资源项->馆藏资源品种:查找资源品种
activate 馆藏资源品种
馆藏资源品种-->资源项
deactivate 馆藏资源品种
资源项-->读者
deactivate 资源项
deactivate 读者

== 查看借阅情况 ==
读者->借书记录:取借书记录信息
activate 读者
activate 借书记录
借书记录->逾期记录:去逾期记录信息
activate 逾期记录
逾期记录-->借书记录
deactivate 逾期记录
借书记录-->读者
deactivate 借书记录
deactivate 读者

== 查看预定记录 ==
读者->预定记录:取预定记录信息
activate 读者
activate 预定记录
预定记录-->读者
deactivate 预定记录
deactivate 读者

== 维护自身信息 ==

读者->读者:查看自身信息
activate 读者

读者->读者:修改自身信息
activate 读者
deactivate 读者
deactivate 读者
else 读者没有权限查询
读者->读者
destroy 读者
end
@enduml
```
#### 4.2读者查询用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test4/lib.seq.userdisplay.png" />

#### 4.3读者查询用例顺序图说明
##### 4.3.1查看图书信息
读者获取资源项信息与馆藏资源信息
##### 4.3.2查看借阅情况
读者查询自身的借书记录与逾期记录
##### 4.3.3查看预定记录
读者查询自身的预定记录
##### 4.3.4维护自身信息
读者查询、修改自身信息
### 5.预定处理用例
#### 5.1预定处理用例PlantUML源码
```
@startuml
title 预定顺序图
actor 图书管理员
participant 读者
participant 资源项
participant 馆藏资源品种
participant 预定记录
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
图书管理员 -> 预定记录 :修改读者预定情况
activate 预定记录
预定记录 ->图书管理员 :预定信息
deactivate 预定记录
note left:返回消息
图书管理员->读者:减少可借额度
activate 读者
读者-->图书管理员
deactivate 读者
opt 取消预定
图书管理员->预定记录
activate 预定记录
预定记录->预定记录:delete
预定记录->馆藏资源品种
deactivate 预定记录
activate 馆藏资源品种
馆藏资源品种->馆藏资源品种:增加可借额度
馆藏资源品种-->资源项
deactivate 馆藏资源品种
activate 资源项
资源项-->图书管理员
deactivate 资源项
图书管理员-->读者:取消预定成功
activate 读者
deactivate 读者
end
deactivate 图书管理员
else 读者没有资格预定
图书管理员->读者:拒绝消息
end
@enduml
```
#### 5.2预定处理用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test4/lib_Sequence.png" />

#### 5.3预定处理用例顺序图说明
图书管理员取到读者消息，根据得到的信息判断读者是否有资格预定(预定额度有无余量、预定的图书有无可借额度)。如果读者有资格预定，图书管理员根据资源项查询到图书的具体信息(馆藏资源品种减少自身的可借额度),图书管理员修改读者的预定记录，再减少读者的预定额度。如果遇到读者取消预定的情况，图书管理员查询到相应的预定记录，调用delete方法删除此记录，馆藏资源品种增加自己的可借额度，图书管理员最后向读者返回预定成功的消息。如果读者没有资格预定，图书管理员向读者发送一个拒绝消息。
### 6.归还处理用例
#### 6.1归还处理用例PlantUML源码
```
@startuml
title:归还
actor 图书管理员
participant 资源项
participant 借书记录
participant 馆藏资源品种
participant 读者
participant 逾期记录
activate 图书管理员
图书管理员->资源项:读取资源信息
activate 资源项
资源项->借书记录:取借书记录
activate 借书记录
deactivate 借书记录
资源项->馆藏资源品种
activate 馆藏资源品种
deactivate 资源项
deactivate 馆藏资源品种
图书管理员->读者:取读者信息
activate 读者
deactivate 读者
图书管理员->资源项:归还资源
activate 资源项
资源项->馆藏资源品种:增加可借数量
activate 馆藏资源品种
deactivate 资源项
deactivate 馆藏资源品种
图书管理员->借书记录:登记还书日期
activate 借书记录
deactivate 借书记录
opt 逾期
图书管理员->逾期记录:登记逾期记录
activate 逾期记录
逾期记录->逾期记录:计算逾期\n金额
逾期记录-->图书管理员:返回逾期信息
deactivate 逾期记录
end
deactivate 图书管理员
@enduml
```
#### 6.2归还处理用例顺序图
<img src="https://github.com/mzy1997/is_analysis/blob/master/test4/lib.seq.back.png" />

#### 6.3归还处理用例顺序图说明
图书管理员查询到资源项，再取到借书记录信息与馆藏资源品种信息，再修改读者信息。图书管理员通过归还资源增加馆藏资源品种的可借数量，再在借书记录中登记还书日期。如果有逾期的情况，图书管理员登记逾期记录，再调用逾期记录的方法计算逾期金额并返回具体信息。
