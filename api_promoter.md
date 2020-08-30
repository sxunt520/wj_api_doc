文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=promoter


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[推广二维码路径](#qrcode_address)  | N |  api |  mobile-app|&act=qrcode_address            | GET/POST    | YES     |
[推广历史](#history)  | N |  api |  mobile-app|&act=history            | POST    | YES     |

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


## <a name="qrcode_address"/>推广二维码路径
地址：&act=index
### 接口输入
提交方式：GET/POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  string   | 见详参 | 二维码的路径

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="history"/>推广历史
地址：&act=history
### 接口输入
提交方式：POST
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
user_name        |是|string     |                    |推广会员用户名
reg_time        |是|int     |                    |注册时间
profit        |是|float     |                    |推广收益