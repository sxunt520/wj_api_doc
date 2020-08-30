文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=deposit


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[零钱余额和银行卡数量](#index)  | N |  api |  mobile-app|&act=index          | GET/POST    | YES     |
[验证手机验证码](#verify_code)  | N |  api |  mobile-app|&act=verify_code            | POST    | YES     |
[修改支付密码](#change_pay_password)  | N |  api |  mobile-app|&act=change_pay_password            | POST    | YES     |
[查询收支明细](#record_list)  | N |  api |  mobile-app|&act=record_list            | GET/POST    | YES     |
[查询单笔收支详细](#record)  | N |  api |  mobile-app|&act=record            | GET    | YES     |
[提交充值](#recharge)  | N |  api |  mobile-app|&act=recharge            | POST    | YES     |
[提现确认](#withdraw)  | N |  api |  mobile-app|&act=withdraw            | POST    | YES     |
[提现记录](#withdraw_list)  | N |  api |  mobile-app|&act=withdraw_list            | GET    | YES     |


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


## <a name="index"/>零钱余额和银行卡数量
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
data       |  是  |  obj   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
deposit_amount    |  是  |float   |                     |零钱余额
bank_count  |  是  |string|                     |银行卡数量


## <a name="verify_code"/>验证手机验证码
地址：&act=verify_code
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
code  |  Y  |string |                           |验证码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="change_pay_password"/>修改支付密码
地址：&act=change_pay_password
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
password |  Y  |string |                           |新支付密码
confirm_password   |  Y  |string |                           |确认新支付密码
code  |  Y  |string |                           |验证码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="record_list"/>查询收支明细
地址：&act=record_list
### 接口输入
提交方式：GET/POST
### 描述
检测版本号

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
N

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
tradeNo|  是  |string |                    |交易号
bizOrderId        |  是  |string |                    |订单号
title        |  是  |string |                    |交易名称
add_time        |  是  |int |                    |下单时间
pay_time        |  是  |int |                    |支付时间
end_time        |  是  |int |                    |完成时间
status_label        |  是  |string |                    |交易状态
flow      |  是  |string |                    |收入或支出。income收入，outlay支出
amount        |  是  |float |                    |金额
partyInfo        |否|obj     |                    |交易对方信息
&ensp;&ensp;└name        |是|string     |                    |对方会员名
refund        |否|obj     |                    |退款信息
&ensp;&ensp;└refund_total_fee        |是|float     |                    |退款金额
&ensp;&ensp;└status_label        |  是  |string |                    |退款状态



## <a name="record"/>查询单笔收支信息
地址：&act=record
### 接口输入
提交方式：GET
### 描述
检测版本号

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
tradeNo |  Y  |string |                           |交易号

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
tradeNo|  是  |string |                    |交易号
bizOrderId        |  是  |string |                    |订单号
title        |  是  |string |                    |交易名称
add_time        |  是  |int |                    |下单时间
pay_time        |  是  |int |                    |支付时间
end_time        |  是  |int |                    |完成时间
status_label        |  是  |string |                    |交易状态
flow      |  是  |string |                    |收入或支出。income收入，outlay支出
amount        |  是  |float |                    |金额
partyInfo        |否|obj     |                    |交易对方信息
&ensp;&ensp;└name        |是|string     |                    |对方会员名
refund        |否|obj     |                    |退款信息
&ensp;&ensp;└refund_total_fee        |是|float     |                    |退款金额
&ensp;&ensp;└status_label        |  是  |string |                    |退款状态


## <a name="recharge"/>提交充值
地址：&act=recharge
### 接口输入
提交方式：POST
### 描述
检测版本号

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
money |  Y  |string |                           |金额

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
tradeNo|  是  |string |                    |交易号
bizOrderId        |  是  |string |                    |订单号
bizIdentity |  是  |string |                          |订单类别，trade20001表示充值
title        |  是  |string |                    |交易名称
add_time        |  是  |int |                    |下单时间
flow      |  是  |string |                    |收入或支出。income收入，outlay支出
amount        |  是  |float |                    |金额


## <a name="withdraw"/>提现确认
地址：&act=withdraw
### 接口输入
提交方式：POST
### 描述
检测版本号

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
bid |  Y  |int |                           |银行卡id
money |  Y  |float |                           |提现金额
password |  Y  |string |                           |支付密码


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------

## <a name="withdraw_list"/>提现记录
地址：&act=withdraw_list
### 接口输入
提交方式：GET
### 描述
检测版本号

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
add_time_from |  N  |string |                           |提现时间开始于
add_time_to |  N  |string |                           |提现时间结束于
status |  N  |string |                           |状态。VERIFING等待审核，SUCCESS提现完成，为空查询全部

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
tradeNo|  是  |string |                    |交易号
bizOrderId        |  是  |string |                    |订单号
title        |  是  |string |                    |交易名称
add_time        |  是  |int |                    |下单时间
pay_time        |  是  |int |                    |支付时间
end_time        |  是  |int |                    |完成时间
status_label        |  是  |string |                    |交易状态
flow      |  是  |string |                    |收入或支出。income收入，outlay支出
amount        |  是  |float |                    |金额
card_info        |是|obj     |                    |银行卡信息
&ensp;&ensp;└bank_name        |是|string     |                    |银行
&ensp;&ensp;└account_name        |是|string     |                    |开户名 
&ensp;&ensp;└num        |是|string     |                    |卡号