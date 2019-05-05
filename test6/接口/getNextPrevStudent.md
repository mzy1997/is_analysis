# 接口:getNextPrevStudent [返回][1]

用例:[评定成绩][2]

<ul>
<li>功能： 返回一个学生的上一个或者下一个学生的学号</li>
<li>权限： 教师/管理员登录后。</li>
<li>API请求地址： 接口基本地址/v1/api/getNextPrevStudent/is_next/user_id</li>
<li>请求方式 ： GET</li>

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>user_id</td>
            <td>学生学号、老师的工号或者管理员的管理员号，由type决定</td>
        </tr>
        <tr>
            <td>is_next</td>
            <td>是下一个还是上一个，如果为1表示取下一个学生，如果为0表示上一个学生</td>
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
        <tr>
            <td>user_id</td>
            <td>学号</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/评定成绩.md    "评定成绩" 