文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=message


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[获取新消息数量](#index)  | N |  api |  mobile-app|&act=index            | GET    | YES     |
[新消息列表](#newpm)  | N |  api |  mobile-app|&act=newpm            | GET    | YES     |
[私人消息列表](#privatepm)  | N |  api |  mobile-app|&act=privatepm            | GET    | YES     |
[系统消息列表](#systempm)  | N |  api |  mobile-app|&act=systempm            | GET    | YES     |
[发送短消息](#send)  | N |  api |  mobile-app|&act=send            | GET    | YES     |
[查看短消息](#view)  | N |  api |  mobile-app|&act=view            | GET    | YES     |
[删除短消息](#drop)  | N |  api |  mobile-app|&act=drop            | GET    | YES     |
[设置消息已读](#set_has_read)  | N |  api |  mobile-app|&act=set_has_read            | GET    | YES     |

## 约定
请阅读README.md

### 全局错误码
请阅读README.md

### 接口返回值示例
请阅读README.md

### 全局Header参数
Header参数名 |示例                                 |说明
------------|------------------------------------|---------------------------
Accept      |application/json                    |输入参数格式，缺省为json


## <a name="index"/>获取新消息数量
地址：&act=index
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  int   |  | 新消息数量

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="newpm"/>新消息列表
地址：&act=newpm
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
msg_id |  Y  |int |                           |消息id
from_id |  Y  |int |                           |发送会员id
to_id |  Y  |int |                           |接收会员id
title |  N  |string |                           |消息主题
content |  Y  |string |                           |消息内容
new |  Y  |int |                           |是否为新消息。1是，0否
status |  Y  |int |                           |消息状态。1发送方已删除，2接收方已删除，3双方未删除
add_time |  Y  |int |                           |发送时间
user_info |  Y  |obj |                           |发送方信息
&ensp;&ensp;└user_id |  Y  |int |                           |会员id
&ensp;&ensp;└user_name |  Y  |string |                           |会员名



## <a name="privatepm"/>私人消息列表
地址：&act=privatepm
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
msg_id |  Y  |int |                           |消息id
from_id |  Y  |int |                           |发送会员id
to_id |  Y  |int |                           |接收会员id
title |  N  |string |                           |消息主题
content |  Y  |string |                           |消息内容
new |  Y  |int |                           |是否为新消息。1是，0否
status |  Y  |int |                           |消息状态。1发送方已删除，2接收方已删除，3双方未删除
add_time |  Y  |int |                           |发送时间
user_info |  Y  |obj |                           |发送方信息
&ensp;&ensp;└user_id |  Y  |int |                           |会员id
&ensp;&ensp;└user_name |  Y  |string |                           |会员名


## <a name="systempm"/>系统消息列表
地址：&act=systempm
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
msg_id |  Y  |int |                           |消息id
from_id |  Y  |int |                           |发送会员id
to_id |  Y  |int |                           |接收会员id
title |  N  |string |                           |消息主题
content |  Y  |string |                           |消息内容
new |  Y  |int |                           |是否为新消息。1是，0否
status |  Y  |int |                           |消息状态。1发送方已删除，2接收方已删除，3双方未删除
add_time |  Y  |int |                           |发送时间
user_info |  Y  |obj |                           |发送方信息
&ensp;&ensp;└user_id |  Y  |int |                           |会员id
&ensp;&ensp;└user_name |  Y  |string |                           |会员名

## <a name="send"/>发送短消息
地址：&act=send
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
to_user_name |  Y  |string |                           |接收方用户名
msg_content |  Y  |string |                           |消息内容

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="view"/>查看短消息
地址：&act=view
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
msg_id |  Y  |int |                           |消息id

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  obj   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
message |  Y  |obj |                           |消息
&ensp;&ensp;└msg_id |  Y  |int |                           |消息id
&ensp;&ensp;└from_id |  Y  |int |                           |发送会员id
&ensp;&ensp;└to_id |  Y  |int |                           |接收会员id
&ensp;&ensp;└title |  N  |string |                           |消息主题
&ensp;&ensp;└content |  Y  |string |                           |消息内容
&ensp;&ensp;└new |  Y  |int |                           |是否为新消息。1是，0否
&ensp;&ensp;└status |  Y  |int |                           |消息状态。1发送方已删除，2接收方已删除，3双方未删除
&ensp;&ensp;└add_time |  Y  |int |                           |发送时间
&ensp;&ensp;user_info |  Y  |obj |                           |发送方信息
&ensp;&ensp;&ensp;&ensp;└user_id |  Y  |int |                           |会员id
&ensp;&ensp;&ensp;&ensp;└user_name |  Y  |string |                           |发送方会员名
replies |  N  |list |                           |回复
&ensp;&ensp;└msg_id |  Y  |int |                           |消息id
&ensp;&ensp;└from_id |  Y  |int |                           |发送会员id
&ensp;&ensp;└to_id |  Y  |int |                           |接收会员id
&ensp;&ensp;└title |  N  |string |                           |消息主题
&ensp;&ensp;└content |  Y  |string |                           |消息内容
&ensp;&ensp;└new |  Y  |int |                           |是否为新消息。1是，0否
&ensp;&ensp;└status |  Y  |int |                           |消息状态。1发送方已删除，2接收方已删除，3双方未删除
&ensp;&ensp;└add_time |  Y  |int |                           |发送时间


## <a name="drop"/>删除短消息
地址：&act=drop
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
msg_id |  Y  |int |                           |消息id

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="set_has_read"/>设置消息已读
地址：&act=set_has_read
### 接口输入
提交方式：GET
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
msg_id |  Y  |int |                           |消息id

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------