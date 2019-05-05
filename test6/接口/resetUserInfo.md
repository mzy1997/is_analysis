# 接口:resetUserInfo [返回][1]

用例:[维护个人信息][2]

<ul>
<li>功能： 修改（设置）用户的密码</li>
<li>权限： 学生/老师/管理员：修改自己的信息，必须先登录。</li>
<li>API请求地址： 接口基本地址/v1/api/resetUserInfo</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "user_name":mzy1997,
      "photo":xxxxx,
      "github_username":mzy1997
  }
```

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>用户名</td>
        </tr>
        <tr>
            <td>photo</td>
            <td>头像</td>
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
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护个人信息.md    "维护个人信息" 