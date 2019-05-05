# 接口:setOneStudentResults[返回][1]

用例:[评定成绩][2]

<ul>
<li>功能： 设置一个学生的部分评分项成绩和评语<br>
          输入参数result不为空，自动设置update_date为当前日期，表示同时设置批改日期<br>
          输入参数result为空，自动设置update_date为空，表示未批改。</li>
<li>权限： 老师：可以查看选自己课的所有学生的成绩，管理员可以查看所有课程的所有学生的成绩</li>
<li>API请求地址： 接口基本地址/v1/api/setOneStudentResults</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
{ "user_id": "201610414414", "total": 6, "data": [ { "scoreItems_id":1, "score_result": 91, "score_describe":"本实验做得好", }, { ...其他实验 } ] }
```

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>user_id</td>
            <td>学号</td>
        </tr>
        <tr>
            <td>total</td>
            <td>本次批改的所有评分项的总数，小于等于全部评分项的总数</td>
        </tr>
        <tr>
            <td>data</td>
            <td>评分项的成绩和评语</td>
        </tr>
        <tr>
            <td>scoreItems_id</td>
            <td>评分项id</td>
        </tr>
        <tr>
            <td>score_result</td>
            <td>评分项得分</td>
        </tr>
        <tr>
            <td>score_describe</td>
            <td>评语</td>
        </tr>
    </table>

<li>返回实例：</li>

```
  { 
      "status": true,
      "info": null,    
  }
```

<li>返回参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>status</td>
            <td>bool类型，true表示正确的返回，false表示有错误</td>
        </tr>
        <tr>
            <td>info</td>
            <td>返回结果说明信息</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/评定成绩.md    "评定成绩" 