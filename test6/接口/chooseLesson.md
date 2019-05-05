# 接口:chooseLesson [返回][1]

用例:[选课][2]

<ul>
<li>功能： 选择课程</li>
<li>权限： 学生/教师登录后。</li>
<li>API请求地址： 接口基本地址/v1/api/chooseLesson</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "user_id":"21048329823",
      "type":"学生"
      "lesson_id":"1231654"
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
            <td>学生学号、老师的工号或者管理员的管理员号，由type决定</td>
        </tr>
        <tr>
            <td>lesson_id</td>
            <td>课程id</td>
        </tr>
        <tr>
            <td>type</td>
            <td>用户类型，学生、老师或者管理员</td>
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
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/选课.md    "选课" 