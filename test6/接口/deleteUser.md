# 接口:deleteUser [返回][1]

用例:[维护学生信息][2][维护教师信息][3]

<ul>
<li>功能： 删除用户信息</li>
<li>权限： 管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/deleteUser</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "user_id":"201610414414",
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