# 接口:updateLesson [返回][1]

用例:[维护课程信息][2]

<ul>
<li>功能： 更新课程信息</li>
<li>权限： 管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/updateLesson</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "lesson_id":123456
      "lesson_name":"大学英语",
      "lesson_type":"公共基础课"
      "lesson_describe":"本书为远程教育大学英语基础课教材，由十课组成;每课包括课文，词汇，注释，语音或语法，练习，补充课文等。文章语言规范，语法讲解透彻，增强了教材的实用性。"
      "user_name":"本尼迪克特"
  }
```

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
                <tr>
            <td>lesson_id</td>
            <td>课程id</td>
        </tr>
        <tr>
            <td>lesson_name</td>
            <td>课程名</td>
        </tr>
        <tr>
            <td>lesson_type</td>
            <td>课程类型</td>
        </tr>
        <tr>
            <td>lesson_describe</td>
            <td>课程简介</td>
         </tr>
        <tr>
            <td>user_name</td>
            <td>授课教师名</td>
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
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护课程信息.md    "维护课程信息" 