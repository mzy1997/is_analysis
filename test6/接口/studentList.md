# 接口:studentList [返回][1]

用例:[学生列表][2]

<ul>
<li>功能： 查看学生列表</li>
<li>权限： 老师/管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/studentList/lesson_id</li>
<li>请求方式 ： GET</li>

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
            <td>可以为空</td>
        </tr>
        <tr>
            <td>lesson_id</td>
            <td>课程id</td>
            <td>是，为空代表查询所有学生，不为空查询对应课程的学生列表</td>
        </tr>
    </table>

<li>返回实例：</li>

```
  {
      "status": true,
      "info": null,
      "total": 120,
      "data": [
          {
          "user_id": "201510315203",
          "student_class": "软件(本)15-1",
          "user_name": "陈松华",
          "update_date": "2018-04-02 13:48:01"
          "github_username":"mzy1997"
          "lesson_average":95},
          {
          ...其他学生
          }
      ]
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
        <tr>
            <td>total</td>
            <td>返回学生总数</td>
        </tr>
        <tr>
            <td>data</td>
            <td>所有学生数组</td>
        </tr>
        <tr>
            <td>user_id</td>
            <td>学号</td>
        </tr>
        <tr>
            <td>student_class</td>
            <td>学生班级</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>学生姓名</td>
        </tr>
        <tr>
            <td>update_date</td>
            <td>学生github修改时间</td>
        </tr>
        <tr>
            <td>github_username</td>
            <td>github用户名</td>
        </tr>
        <tr>
            <td>lesson_average</td>
            <td>课程平均分</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/学生列表.md    "学生列表"
 