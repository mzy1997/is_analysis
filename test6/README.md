# 基于GitHub的实验管理平台的分析与设计
## 成都大学信息科学与工程学院
|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|

## 1.概述
<ul style="font-size:16px">
<li>基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统。学生和老师的实验内容均存放在GitHUB 页面上。</li>
<li>学生的功能主要有：一是设置自己的GitHub用户名，二是选择自己的课程，三是查询自己的多个科目的多个实验成绩,学生的GitHub用户名是公开的，但成绩不公开。</li>
<li>老师的功能主要有：一是设置自己的GitHub用户名，二是选择自己的课程，三是批改自己学生的成绩，四是查看自己学生的成绩</li>
<li>管理员的功能主要有：一是维护课程信息，二是维护学生信息，三是维护教师信息</li>
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
- [学生列表用例][4],[界面1][19],[界面2][20]
- [选择课程][5]，[界面1][21],[界面2][22]
- [设定实验与评分项][6],[界面][23]
- [学年学期][7],无专门属于此用例的界面
- [查看实验平均分][8]
- [查看评分项得分][9]
- [查看课程平均分][10]，以上三个页面总和，[界面1][24]，[界面2][25],[界面3][26]
- [登录登出][11],[登录界面][27],[登出界面][28]
- [结束课程][12],无专门属于此用例的界面
- [维护个人信息][13]，[修改个人信息界面][29],[查看个人信息界面][30]，[修改密码][31]
- [维护学生信息][14]，
- [维护教师信息][15]，以上两个用例界面在两个界面中，[修改信息界面][32],[删除信息界面][33]
- [维护课程信息][16]，[修改界面][34],[删除界面][35]，[主页][38]
- [评定成绩][17],[界面1][36]，[界面2][37]



[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/src/UserCase.puml     "源码" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/src/systemClass.puml     "源码" 
[3]: https://github.com/mzy1997/is_analysis/blob/master/test6/数据库设计.md     "参见数据库详细设计"
[4]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/学生列表.md     "学生列表用例"
[5]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/选课.md     "选择课程用例"
[6]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/设定实验与评分项.md     "设定实验与评分项"
[7]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/学期学年.md     "学期学年"
[8]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/查看实验平均分.md     "查看实验平均分"
[9]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/查看评分项得分.md     "查看评分项得分"
[10]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/查看课程平均分.md     "查看课程平均分"
[11]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/登录登出.md     "登录登出"
[12]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/结束课程.md     "结束课程"
[13]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护个人信息.md     "维护个人信息"
[14]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护学生信息.md     "维护学生信息"
[15]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护教师信息.md     "维护教师信息"
[16]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护课程信息.md     "维护课程信息"
[17]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/评定成绩.md     "评定成绩"
[19]: https://mzy1997.github.io/is_analysis_finalDesign_pages/studentlist.html    "界面1"
[20]: https://mzy1997.github.io/is_analysis_finalDesign_pages/thlessondetails.html    "界面2"
[21]: https://mzy1997.github.io/is_analysis_finalDesign_pages/chooselesson.html   "界面1"
[22]: https://mzy1997.github.io/is_analysis_finalDesign_pages/chooselesson_2.html   "界面2"
[23]: https://mzy1997.github.io/is_analysis_finalDesign_pages/thsetlesson.html   "界面"
[24]: https://mzy1997.github.io/is_analysis_finalDesign_pages/stulessondetails.html   "界面1"
[25]: https://mzy1997.github.io/is_analysis_finalDesign_pages/evaluationresults.html   "界面2"
[26]: https://mzy1997.github.io/is_analysis_finalDesign_pages/resultsdetails.html   "界面3"
[27]: https://mzy1997.github.io/is_analysis_finalDesign_pages/login.html   "登录界面"
[28]: https://mzy1997.github.io/is_analysis_finalDesign_pages/logout.html   "登出界面"
[29]: https://mzy1997.github.io/is_analysis_finalDesign_pages/updatauserinfo.html   "修改个人信息界面"
[30]: https://mzy1997.github.io/is_analysis_finalDesign_pages/showuserinfouserinfo.html   "查看个人信息界面"
[31]: https://mzy1997.github.io/is_analysis_finalDesign_pages/resetpassword.html   "修改密码"
[32]: https://mzy1997.github.io/is_analysis_finalDesign_pages/updateuser.html   "修改信息界面"
[33]: https://mzy1997.github.io/is_analysis_finalDesign_pages/deleteuser.html   "删除信息界面"
[34]: https://mzy1997.github.io/is_analysis_finalDesign_pages/updatelesson.html   "修改界面"
[35]: https://mzy1997.github.io/is_analysis_finalDesign_pages/deletelesson.html   "删除界面"
[36]: https://mzy1997.github.io/is_analysis_finalDesign_pages/evaluationresults.html   "界面1"
[37]: https://mzy1997.github.io/is_analysis_finalDesign_pages/resultsdetails.html   "界面2"
[38]: https://mzy1997.github.io/is_analysis_finalDesign_pages/index.html   "主页"
