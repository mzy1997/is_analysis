# 接口:getUserInfo [返回][1]

用例:[维护个人信息][2]

<ul>
<li>功能： 删除用户信息</li>
<li>权限： 管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/getUserInfo/<user_id></li>
<li>请求方式 ：  GET</li>

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
    </table>

<li>返回实例：</li>

```
  {         
      "status": true,
      "info": null,
      "user_id":"2101201281",    
      "user_name":"张三",
      "student_class":"软件工程1班"
      "github_username":"ABCD",
      "type":"学生"            
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
            <td>user_id</td>
            <td>用户id，对应学生学号，教师职工号，管理员管理员号</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>用户姓名</td>
        </tr>
        <tr>
            <td>github_username</td>
            <td>github用户名</td>
        </tr>
        <tr>
            <td>student_class</td>
            <td>学生所在班级</td>
        </tr>
        <tr>
            <td>type</td>
            <td>用户类型</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护个人信息.md    "维护个人信息"
