# 实验一:业务流程建模

|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|

## 流程图1:考试及成绩管理流程
### PlantUML源码如下：
```
@startuml
|教务处|
start
  :安排考试;
  :考试安排表;
|#AntiqueWhite|教师|
  :出卷;
  fork
    :A、B试卷;
  fork again
    :打印审批表;
    |系主任|
       :审批签字;
       :打印审批表;
  end fork
|教务处|
  :打印试卷;
  :试卷;
|学生|
  :参加考试;
  :答卷;
|教师|
  :阅卷出成绩;
  split
    :成绩单;
    |教务处|
    if (有不及格?) then (no)
      stop
    else
      :安排补考;
      split
        :补考安排表;
        detach
      split again
      end split
    endif
   split again
     |教师|
     :答卷;
     :装订成档;
   end split
:期末流程结束;
@enduml
```
### 业务流程图如下：
<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/markManager.png"/>

### 流程说明：
## 流程图2:客户维修服务流程
### PlantUML源码如下：
```
@startuml
|#AntiqueWhite|客户|
start
    :申请服务;
|#AntiqueWhite|业务经理|
if(是新客户吗？)then(是)
    :登记客户信息;
    else (不是)
    endif
    :上门勘察;
    :制定方案;
|#AntiqueWhite|客户|
    if(满意吗？)then(是)
        :签订服务合同;
    else(否)
        stop
    endif
|#AntiqueWhite|业务经理|
    fork
        split
            :安排工人;
        split again
            :安排材料;
        end split
        end fork
        :填写派工单;
|#AntiqueWhite|工人|
:领取材料;
:上门服务;
|#AntiqueWhite|客户|
:验收并填写反馈意见;
|#AntiqueWhite|业务经理|
:交回派工单;
|#AntiqueWhite|财务人员|
:结算收款;
@enduml
```
### 业务流程图如下：
<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/customerService.png"/>
