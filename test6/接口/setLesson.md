# 接口:setLesson [返回][1]

用例:[设定实验与评分项][2]

<ul>
<li>功能： 选择课程</li>
<li>权限： 学生/教师登录后。</li>
<li>API请求地址： 接口基本地址/v1/api/setLesson</li>
<li>请求方式 ： POST</li>
<li>请求实例：</li>


```
  {
      "test_id":"1554601",
      "test_name":"顺序图实战"
      "data": [
          {"scoreItems_id": "15546011",
          "scoreItems_describe": "xxxxxxxxx",
          "scoreItems_name": "画图得分",
          },
          {
          ...其他评分项
          }   
          ]
  }
```

<li>请求参数说明:</li>
    <table>
        <tr>
            <td>参数</td>   
            <td>说明</td>
        </tr>
        <tr>
            <td>test_id</td>
            <td>实验id</td>
        </tr>
        <tr>
            <td>test_name</td>
            <td>实验名称</td>
        </tr>
        <tr>
            <td>data</td>
            <td>评分项数组</td>
        </tr>
        <tr>
            <td>scoreItems_id</td>
            <td>评分项id</td>
        </tr>
        <tr>
            <td>scoreItems_describe</td>
            <td>评分项简介</td>
        </tr>
        <tr>
            <td>scoreItems_name</td>
            <td>评分项名称</td>
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
[2]: https://github.com/mzy1997/is_analysis/blob/master/test6/用例/设定实验与评分项.md    "设定实验与评分项" 