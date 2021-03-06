文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=popads


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[弹窗](#index)  | N |  api |  mobile-app|&act=getPopAds            | GET/POST    | YES     |

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


## <a name="index"/>弹窗
地址：&act=getPopAds
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
data       |  是  |  obj   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
ads_id    |  是  |int   |                     |弹窗id
ads_Picture        |是|string     |                    |图片地址
ads_url        |是|string     |                    |跳转链接 


## <a name="get_default"/>默认银行卡
地址：&act=get_default
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
data       |  是  |  obj   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
bid    |  是  |int   |                     |银行卡id
bank_name        |是|string     |                    |银行
account_name        |是|string     |                    |开户名 
num        |是|string     |                    |卡号



## <a name="add"/>添加银行卡
地址：&act=add
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
card_num |  Y  |string |                           |卡号
bank_name   |  Y  |string |                           |银行
account_name  |  Y  |string |                           |开户名
cert_no  |  Y  |string |                           |身份证号

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="drop"/>删除银行卡
地址：&act=drop
### 接口输入
提交方式：GET
### 描述
检测版本号

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
bid |  Y  |int |                           |银行卡id

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------