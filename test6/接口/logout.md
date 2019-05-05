# 接口:logout [返回][1]

用例:[登录登出][2]

<ul>
<li>功能： 已经登录的用户登出平台</li>
<li>权限： 学生/老师/管理员</li>
<li>API请求地址： 接口基本地址/v1/api/login</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "user_id":324111
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
            <td>已经登录用户的user_id值，对应学生学号、教师职工号、管理员管理员号</td>
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
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/登录登出.md    "登录登出" 