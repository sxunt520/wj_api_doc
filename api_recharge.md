文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 手机充值相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=recharge


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[手机充值列表](#recharge-01) | Y |  api |  mobile-app|&act=index                     | GET    | YES     |手机充值列表
[油卡充值列表](#recharge-02) | Y |  api |  mobile-app|&act=oil_recharge              | GET    | YES     |油卡充值列表
[油卡充值详情](#recharge-03) | Y |  api |  mobile-app|&act=do_oil_recharge           | GET    | YES     |油卡充值详情
[手机充值详情](#recharge-04) | Y |  api |  mobile-app|&act=buy                       | GET    | YES     |手机充值详情(下单)
[获取手机充值支付参数](#recharge-05)|Y|api|  mobile-app|&act=cashier                   | GET    | YES     |获取手机充值支付参数
[获取油卡充值或办理支付参数](#recharge-06)|Y|api|  mobile-app|&act=oil_cashier          | GET    | YES     |获取油卡充值或办理支付参数
[油卡办理](#recharge-07)    | Y |  api |   mobile-app|&act=do_sale                   | GET    | YES     |油卡办理
[获取话费或油卡的订单信息](#get_recharge_detail)    | Y |  api |   mobile-app|&act=get_recharge_detail                   | GET    | YES     |


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


## <a name="recharge-01"/>手机充值列表
地址：&act=index
### 接口输入
提交方式：GET
### 描述
手机充值列表

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
recharge_id|  是  |string |                    |商品ID
recharge_name|是  |string |                    |商品名字
recharge_money|是 |string |                    |金额
recharge_rule|是  |string |                    |反积分


## <a name="recharge-02"/>油卡充值列表
地址：&act=oil_recharge
### 接口输入
提交方式：GET
### 描述
油卡充值列表

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
type       |  是  |string |                    |油卡类型中文名
sign       |  是  |string |                    |油卡标识
card_type  |  是  |string |                    |油卡类型英文名


## <a name="recharge-03"/>油卡充值详情
地址：&act=do_oil_recharge
### 接口输入
提交方式：POST
### 描述
油卡充值详情

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
amount    |  Y  |string |                           |充值金额
card_id   |  Y  |string |                           |油卡ID
new       |  N  |string |    on                     |类型
type      |  N  |string |    on                     |油卡类型


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
goods_id   |  是  |string |                    |商品ID
buyer_id   |  是  |string |                    |购买ID
order_id   |  是  |string |                    |定单号
goods_name |  是  |string |                    |名称
amount     |  是  |string |                    |金额
price      |  是  |string |                    |价格
record_id  |  是  |string |                    |定单ID


## <a name="recharge-04"/>手机充值详情
地址：&act=buy
### 接口输入
提交方式：GET
### 描述
手机充值详情

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
id        |  Y  |string |                           |充值卡ID
quantity  |  Y  |string |                           |数量(写死1)
phone_mob |  Y  |string |                           |手机号


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
phone_mob  |  是  |string |                    |手机号
record_id  |  是  |string |                    |定单ID
recharge_money|是 |string |                    |充值金额


## <a name="recharge-05"/>获取手机充值支付参数
地址：&act=cashier
### 接口输入
提交方式：GET
### 描述
获取手机充值支付参数

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
record_id |  Y  |string |                           |定单ID


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id   |  是  |string |                    |定单ID
amount     |  是  |string |                    |金额


## <a name="recharge-06"/>获取油卡充值或办理支付参数
地址：&act=oil_cashier
### 接口输入
提交方式：GET
### 描述
获取油卡充值或办理支付参数

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
record_id |  Y  |string |                           |定单ID
code      |  N  |string |   oil_card_order          |办卡时需要


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id   |  是  |string |                    |定单ID
amount     |  是  |string |                    |金额


## <a name="recharge-07"/>油卡办理
地址：&act=do_sale
### 接口输入
提交方式：GET
### 描述
油卡办理

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
type      |  Y  |string |                           |卡片类型
apply_name|  Y  |string |                           |姓名
id_card   |  Y  |string |                           |身份证号
consignee |  Y  |string |                           |收件人
phone_mob |  Y  |string |                           |手机号
region_id |  Y  |string |                           |城市地区
address   |  Y  |string |                           |详细地址


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id   |  是  |string |                    |定单号
goods_name |  是  |string |                    |商品名
price      |  是  |string |                    |价格
quantity   |  是  |string |                    |购买数量
amount     |  是  |string |                    |金额
type       |  是  |string |                    |油卡类型
apply_name |  是  |string |                    |用户姓名
id_card    |  是  |string |                    |用户身份证号
consignee  |  是  |string |                    |收件人
phone_mob  |  是  |string |                    |手机号
region_id  |  是  |string |                    |地区
address    |  是  |string |                    |收货地址
record_id  |  是  |string |                    |办卡ID/定单ID




## <a name="get_recharge_detail"/>获取话费或油卡的订单信息
地址：&act=get_recharge_detail
### 接口输入
提交方式：GET
### 描述
油卡办理

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
id      |  Y  |int |                           |id
code|  Y  |string |                           |编号。phone_recharge话费充值，oil_recharge油卡充值，oil_card_order油卡办理


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id   |  是  |string |                    |定单号
amount     |  是  |string |                    |金额
