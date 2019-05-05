# 接口:updateUser [返回][1]

用例:[维护学生信息][2][维护教师信息][3]

<ul>
<li>功能： 更新学生或教师信息,如果数据库内无此user_id，则增加新字段</li>
<li>权限： 管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/updateUser</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "user_id":201610414414
      "user_name":"穆峥言",
      "student_department":"信工"
      "student_major":"软件工程"
      "user_grade":"16级"
      "github_username":mzy1997
      "type":"学生"
  }
```

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>user_id</td>
            <td>用户id，对应学生学号，教师职工号</td>
        </tr>
        <tr>
            <td>type</td>
            <td>用户类型</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>用户名</td>
        </tr>
        <tr>
            <td>student_department</td>
            <td>学生所属学院</td>
        </tr>
        <tr>
            <td>student_major</td>
            <td>学生专业</td>
         </tr>
        <tr>
            <td>user_grade</td>
            <td>学生年级</td>
        </tr>
        <tr>
            <td>github_username</td>
            <td>github用户名</td>
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
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护学生信息.md    "维护学生信息"
[3]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护教师信息.md    "维护教师信息" 