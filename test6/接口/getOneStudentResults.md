# 接口:getOneStudentResults [返回][1]

用例:[评定成绩][2][查看评分项得分][3]

<ul>
<li>功能： 返回一个学生的所有评分项得分和评价</li>
<li>权限： 老师/管理员登录。</li>
<li>API请求地址： 接口基本地址/v1/api/getOneStudentResults</li>
<li>请求方式 ： GET</li>


<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>user_id</td>
            <td>用户id，对应学生学号</td>
        </tr>
    </table>

<li>返回实例：</li>

```
{         
      "status": true,
      "info": null,    
      "user_id": "201610414414", 
      "github_username": "mzy1997", 
      "grade": "16级", 
      "major":"软件工程"
      "class":"4班",
      "user_name": "穆峥言", 
      "total": 6,
      "average_test":90,       
      "data": [
          {
          "scoreItems_id":1,
          "scoreItems_name":"xxx"
          "web_exists": true, 
          "score_result": 91, 
          "score_describe":"本实验做得好",
          "score_releaseDate": "2018-04-02"
          }, 
          {
          ...其他评分项
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
            <td>user_id</td>
            <td>用户id，对应学生学号</td>
        </tr>
        <tr>
            <td>github_username</td>
            <td>github用户名</td>
        </tr>
        <tr>
            <td>grade</td>
            <td>年级</td>
        </tr>
        <tr>
            <td>major</td>
            <td>专业</td>
        </tr>        
        <tr>
            <td>class</td>
            <td>班级</td>
        </tr>
        <tr>
            <td>user_name</td>
            <td>用户姓名</td>
        </tr>
        <tr>
            <td>total</td>
            <td>总评分项数目</td>
        </tr>
        <tr>
            <td>average_test</td>
            <td>实验平均分</td>
        </tr>
        <tr>
            <td>scoreItems_id</td>
            <td>评分项id</td>
        </tr>
        <tr>
            <td>scoreItems_name</td>
            <td>评分项名</td>
        </tr>
        <tr>
            <td>web_exists</td>
            <td>网址是否存在</td>
        </tr>        
        <tr>
            <td>score_result</td>
            <td>评分项得分</td>
        </tr>
        <tr>
            <td>score_describe</td>
            <td>评价</td>
        </tr>
        <tr>
            <td>score_releaseDate</td>
            <td>评改时间</td>
        </tr>
    </table>
</ul>

[1]: https://github.com/mzy1997/is_analysis/blob/master/test6/README.md    "返回" 
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/评定成绩.md    "评定成绩"
[3]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/查看评分项得分.md    "查看评分项得分" 