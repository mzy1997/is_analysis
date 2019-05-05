# 接口:getLessons [返回][1]

用例:[维护课程信息][2]

<ul>
<li>功能： 修改（设置）用户的密码</li>
<li>权限： 学生/老师/管理员：修改自己的信息，必须先登录。</li>
<li>API请求地址： 接口基本地址/v1/api/getLessons</li>
<li>请求方式 ： GET</li>
<li>请求实例：</li>


```
  {
      "year_and_term":2019-01,
      "lesson_chooseOrNot":false,
  }
```

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>year_and_term</td>
            <td>学年学期</td>
        </tr>
        <tr>
            <td>lesson_name</td>
            <td>课程名</td>
        </tr>
        <tr>
            <td>lesson_chooseOrNot</td>
            <td>课程是否被选</td>
        </tr>
    </table>

<li>返回实例：</li>

```
  { 
      "status": true,
      "info": null, 
      "data": [
          {"lesson_type": "公共基础课",
          "lesson_describe": "xxxxxxxxx",
          "lesson_name": "大学英语基础课程",
          "lesson_releaseDate": "2018-04-30",
          "user_name": "本尼迪克特",
          },
          {
          ...其他课程
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
            <td>返回课程数目</td>
        </tr>
        <tr>
            <td>data</td>
            <td>所有课程的数组</td>
        </tr>
        <tr>
            <td>lesson_type</td>
            <td>课程的类型</td>
        </tr>
        <tr>
            <td>lesson_describe</td>
            <td>课程的简介</td>
        </tr>
        <tr>
            <td>lesson_releaseDate</td>
            <td>课程的发布时间</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>授课教师的姓名</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/维护课程信息.md    "维护课程信息"
 