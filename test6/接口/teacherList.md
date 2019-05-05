# 接口:teacherList [返回][1]

用例:[教师列表][2]

<ul>
<li>功能： 查看教师列表</li>
<li>权限： 管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/teacherList</li>
<li>请求方式 ： GET</li>


<li>返回实例：</li>

```
  {
      "status": true,
      "info": null,
      "total": 60,
      "data": [
          {
          "user_id": "123454656",
          "user_name": "本尼迪克特",
          "teacher_department": "信工"
          {
          ...其他教师
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
            <td>返回教师总数</td>
        </tr>
        <tr>
            <td>data</td>
            <td>所有教师数组</td>
        </tr>
        <tr>
            <td>user_id</td>
            <td>职工号</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>教师姓名</td>
        </tr>
        <tr>
            <td>teacher_department</td>
            <td>教师所在学院</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/教师列表.md    "教师列表"
 