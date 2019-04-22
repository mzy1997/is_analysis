# 实验五:图书管理系统数据库设计与界面设计
|    学号    |       班级       |      姓名     |照片|
|:-------:|:-------------:|:----------:|:-----------:|
|  201610414414  |     软件工程4班    |   穆峥言   |<img src="https://github.com/mzy1997/is_analysis/blob/master/test1/5617531AD9394A6243FCDEEBF0F683B1.jpg" width="200" height="300" />|

## 1.数据库表设计
### 1.1碟片表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  isbn  |     int    |   主键   |否|||国际出版号|
|  dv_name  |     varchar    |      |否|||碟片名称|
|  dv_price |     double    |      |否|||碟片价格|
|  dv_describe  |     string    |      |是|||碟片简介|
|  store_num  |     string    |      |否||max>=ava_num|在库总数|
|  ava_num  |     string    |      |否||max<=store_num|可借总数|
|  dv_company  |     string    |      |否|||制作公司|
|  dv_category  |     string    |      |否|||碟片分类|
|  dv_picture  |     image    |      |否|||碟片图片|


### 1.2图书表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  isbn  |     int    |   主键   |否|||国际出版号|
|  book_name  |     varchar    |      |否|||图书名称|
|  book_price  |     double    |      |否|||图书价格|
|  book_describe  |     string    |      |是|||图书简介|
|  store_num  |     string    |      |否||max>=ava_num|在库总数|
|  ava_num  |     string    |      |否||max<=store_num|可借总数|
|  book_author  |     string    |      |否|||作者|
|  book_press  |     string    |      |否|||出版社|
|  book_date  |     date    |      |否|||出版日期|
|  book_picture  |     image    |      |否|||图书图片|
|  book_category  |     string    |      |否|||图书分类|

### 1.3资源项表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  source_id  |     int    |   主键   |否||AUTO_INCREMENT|资源流水号，每一本图书的唯一编号|
|  status  |     string    |      |否|||资源状态，只有在库和借出两种状态|
|  isbn  |     int    |   外键   |否|||国际出版号|

### 1.4读者表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  reader_borrowid  |     int    |   主键   |否||AUTO_INCREMENT|借书卡号|
|  reader_name  |    string   |      |否|||读者姓名|
|  reader_id  |   int   |      |否|||读者身份证号|
|  reader_booklimit  |   int   |      |否|20||读者借书限额|
|  reader_bookborrowed  |   int   |      |是|空||读者已结图书数,为空表示借书数为0|
|  reader_dvlimit  |   int   |      |否|5||读者借碟片限额|
|  reader_dvborrowed  |   int   |      |是|空||读者已结碟片数,为空表示借碟片数为0|

### 1.5图书管理员表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  admin_id  |     int    |    主键  |否|||管理员职工号|
|  admin_name  |     string    |      |否|||管理员姓名|
|  admin_password  |     string    |      |否|||管理员密码|


### 1.6借书记录表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  borrow_id  |     int    |   主键   |否||AUTO_INCREMENT|借书记录ID|
|  borrow_date  |     date    |      |否||isDate()==True|借书时间|
|  bringback_date  |     date    |      |是|空|isDate()==True|还书时间,允许为空，如果为空则表示尚未归还|
|  admin_id  |     int    |    外键  |否|||处理此借书记录的管理员职工号|
|  reader_borrowid  |     int    |   外键   |否|||存储借此书读者的卡号|
|  source_id  |     int    |   外键   |否|||存储所借图书的流水号|

### 1.7逾期记录表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  expect_id  |     int    |   主键   |否||AUTO_INCREMENT|逾期记录ID|
|  expect_money  |     double    |      |否|0||罚款金额，默认值为0|


### 1.8预定记录表
|    字段    |       类型       |      主键，外键     |是否为空|默认值|约束|说明|
|:-------:|:-------------:|:----------:|:-----------:|:-----------:|:-----------:|:-----------:|
|  schedule_id  |     int    |   主键   |否||AUTO_INCREMENT|预定记录ID|
|  schedule_date  |     date   |      |否||isDate()==True|预定时间|
|  isbn  |     int    |   外键   |否|||所预定图书的ISBN|
|  reader_borrowid  |     int    |   外键   |否|||提交预定申请的读者的借书卡号|
|  admin_id  |     int    |    外键  |否|||处理此预定申请的图书管理员工号|

## 2.界面设计
### 2.1借书界面
### 2.1.1借书界面首页
<img src="https://github.com/mzy1997/is_analysis/blob/master/test5/index1.jpg"/>

### 2.1.2借书界面详情页
<img src="https://github.com/mzy1997/is_analysis/blob/master/test5/newpage1.jpg"/>

### 2.1.3借书界面确认页
<img src="https://github.com/mzy1997/is_analysis/blob/master/test5/newpage2.jpg"/>

### 2.1.4借书界面首页链接
https://mzy1997.github.io/is_analysis_pages/index.html
(页面加载较慢)

### 查看图书详情接口

#### 1) 请求地址

>http://mzy1997.github.io/is_analysis_pages/v1/api/book_detals

#### 2) 调用方式：GET

#### 3) 请求参数:
|    参数名称    |       必填       | 说明 |
|:-------:|:-------------:|:-------:|
|access_token|是|用于验证请求合法性的认证信息|
|name|是|资源名称|
|isbn|否|资源的国际出版号,选填|
|category|否|资源类别,选填|
#### 4) 请求返回结果:

```
{
    "info": "查询成功",
    "data": [
    {
        "name": "平凡的世界",
        "author": "路遥",
        "category": "小说",
        "isbn": "753021200",
        "describe": "劳动与爱情，挫折与追求，痛苦与欢乐，日常生活与巨大社会冲突，纷繁地交织在一起，深刻地展示了普通人在大时代历史进程中所走过的艰难曲折的道路",
        "image": "...",
    },
    {
        "name": "平凡的世界",
        "author": "路遥",
        "category": "小说",
        "isbn": "9787020048045",
        "describe": "劳动与爱情，挫折与追求，痛苦与欢乐，日常生活与巨大社会冲突，纷繁地交织在一起，深刻地展示了普通人在大时代历史进程中所走过的艰难曲折的道路",
        "image": "...",
    }
    ...
    ]
    "code": 200
}
```
#### 5) 返回结果说明:
|    参数名称    | 说明 |
|:-------:|:-------------:|
|info|消息|
|data|资源信息|
|code|返回码|

### 查看图书详情接口

#### 1) 请求地址

>http://mzy1997.github.io/is_analysis_pages/v1/api/book_details

#### 2) 调用方式：GET

#### 3) 请求参数:
|    参数名称    |       必填       | 说明 |
|:-------:|:-------------:|:-------:|
|access_token|是|用于验证请求合法性的认证信息|
|isbn|是|资源的国际出版号|

#### 4) 请求返回结果:

```
{
    "info": "查询成功",
    "details": {
        "name": "平凡的世界",
        "author": "路遥",
        "category": "小说",
        "isbn": "753021200",
        "describe": "劳动与爱情，挫折与追求，痛苦与欢乐，日常生活与巨大社会冲突，纷繁地交织在一起，深刻地展示了普通人在大时代历史进程中所走过的艰难曲折的道路",
        "image": "...",
        "ava_num": "40",
    }，
    "code": 200
}
```
#### 5) 返回结果说明:
|    参数名称    | 说明 |
|:-------:|:-------------:|
|info|消息|
|details|资源信息|
|code|返回码|

### 借阅图书接口

#### 1) 请求地址

>http://mzy1997.github.io/is_analysis_pages/v1/api/borrow

#### 2) 调用方式：Post

#### 3) 请求参数:
|    参数名称    |       必填       | 说明 |
|:-------:|:-------------:|:-------:|
|access_token|是|用于验证请求合法性的认证信息|
|isbn|是|资源的国际出版号|
|book_name|是|资源的名称|
|reader_name|是|读者的名称|
|reader_borrowid|是|借书卡号|
|borrow_date|是|借书时间|
#### 4) 请求返回结果:

```
{
    "info": "借书成功",
    "code": 200
}
```
#### 5) 返回结果说明:
|    参数名称    | 说明 |
|:-------:|:-------------:|
|info|消息|
|code|返回码|
