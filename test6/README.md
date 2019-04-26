### 基于GitHub的实验管理平台的分析与设计
### 成都大学信息科学与工程学院
|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|

## 1.概述
<ul style="font-size:16px">
<li>基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统。学生和老师的实验内容均存放在GitHUB 页面上。</li>
<li>学生的功能主要有：一是设置自己的GitHub用户名，二是选择自己的课程，三是查询自己的多个科目的多个实验成绩,学生的GitHub用户名是公开的，但成绩不公开。</li>
<li>老师的功能主要有：一是设置自己的GitHub用户名，二是选择自己的课程，三是批改自己学生的成绩，四是查看自己学生的成绩</li>
<li>同一个课程的老师和学生都能跳转到对方的GitHub页面，以便批改实验或者查看实验情况</li>
<li>每个实验的实验成绩细分为多个评分项，每个评分项对应各自的评分标准。 老师在批改实验的时候，对每个评分项进行评分并输入对应的文字评价，系统自动计算出所有评分项的成绩之和为该实验的总成绩</li>
</ul>

## 2.系统总体结构
<img src="https://github.com/mzy1997/is_analysis/blob/master/test6/systemStructure.png"/>

## 3.用例图设计 [源码][1]
<img src="https://github.com/mzy1997/is_analysis/blob/master/test6/UserCase.png"/>

## 4. 类图设计 [源码][2]
<img src="https://github.com/mzy1997/is_analysis/blob/master/test6/systemClass.png"/>

## 5.数据库设计
[参见数据库详细设计][3]

## 6.用例及界面详细设计
- [学生列表用例][4]
- [选择课程][5]

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/src/UserCase.puml     "源码" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/src/systemClass.puml     "源码" 
[3]: https://github.com/mzy1997/is_analysis/blob/master/test6/数据库设计.md     "参见数据库详细设计"
[4]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/学生列表.md     "学生列表用例"
[5]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/选择课程.md     "选择课程用例"