文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=depopay

## 接口文档

## <a name="list"/>支付接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[获取支付方式列表](&act=get_payment_list)    | N |  api |  mobile-app|&act=get_payment_list    | POST    | YES     |获取支付方式列表和个人钱包信息
[提交支付](&act=confirm_pay)    | N |  api |  mobile-app|&act=confirm_pay    | POST    | YES     |提交支付
[支付成功后验签](&act=pay_result_sign)    | N |  api |  mobile-app|&act=pay_result_sign    | POST    | YES     |支付成功后验签


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



## <a name="&act=get_payment_list"/>获取支付方式列表
地址：&act=get_payment_list
### 接口输入
提交方式：POST
### 描述
 

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id_list     |  Y  |int | 471  |订单号，多个订单号用","分开,如："471,472,473"
order_type|  Y  |string | material|订单分类,(material:普通订单；phone：话费充值；oil：油卡充值；oil_card:油卡办理；recharg:余额充值。不传则默认为material）


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
all_payments |  是  |list |                    |支付方式列表
&ensp;&ensp;└ payment_id  |  是  |int |    3                 |支付方式ID
&ensp;&ensp;└ store_id  |  是  |int |     0               |支持该支付方式的商品，0则表示所有商品都支持
&ensp;&ensp;└ payment_code  |  是  |string |     deposit               |支付方式对应的编码
&ensp;&ensp;└ payment_name  |  是  |string |    钱包支付               |支付方式名称
&ensp;&ensp;└ payment_desc  |  是  |string |使用会员零钱支付               |支付方式描述
&ensp;&ensp;└ config  |  是  |string |     a:1:{s:5:\"pcode\";s:0:\"\";}               |支付方式配置
&ensp;&ensp;└ is_online  |  是  |int |     1               |是否在线支付，0：不是；1：是
&ensp;&ensp;└ enabled  |  是  |int |    1               |是否可用，0：不是；1：是
&ensp;&ensp;└ sort_order  |  是  |int |1               |支付列表中的序号
&ensp;&ensp;└ cod_regions  |  是  |string |                  |
&ensp;&ensp;└ selected  |  是  |int |1               | 默认选择
deposit_account|  是  |list |                    |个人钱包信息
&ensp;&ensp;└ account_id  |  是  |int |    6593                 |账户ID
&ensp;&ensp;└ user_id  |  是  |int |    6609                 |买家ID
&ensp;&ensp;└ account  |  是  |string |   13880532794                 |账户名称
&ensp;&ensp;└ password  |  是  |string |    06d26dac144d17f1b6ec8dbe450b7a3e                 |密码
&ensp;&ensp;└ money  |  是  |float |    99999                 |钱包余额（零钱）
&ensp;&ensp;└ frozen  |  是  |float |    0.00                 |冻结金额
&ensp;&ensp;└ real_name  |  是  |string |    xiaolisn                 |
&ensp;&ensp;└ pay_status  |  是  |string |   ON                 | 
&ensp;&ensp;└ add_time  |  是  |int |    1472062435                 | 
&ensp;&ensp;└ last_update  |  是  |int |    1472091209                 | 
&ensp;&ensp;└ storemoney  |  是  |float |    0.00                 | 
&ensp;&ensp;└ storefrozen  |  是  |float |    0.00                 | 
&ensp;&ensp;└ co_money  |  是  |float |    0.00               | 
&ensp;&ensp;└ co_frozen  |  是  |float |   0.00                 | 
&ensp;&ensp;└ super_money  |  是  |float |    0.00                |超级会员消费金
tradeNo|  是  |string |   20161202075155722442                 |交易号
 
### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "all_payments": [
      {
        "payment_id": "3",
        "store_id": "0",
        "payment_code": "deposit",
        "payment_name": "预存款",
        "payment_desc": "11111测试11111",
        "config": "a:1:{s:5:\"pcode\";s:0:\"\";}",
        "is_online": "1",
        "enabled": "1",
        "sort_order": "0",
        "cod_regions": "",
        "selected": 1
      },
      {
        "payment_id": "23",
        "store_id": "0",
        "payment_code": "minsheng_gateway",
        "payment_name": "民生网关支付",
        "payment_desc": "21312",
        "config": "a:3:{s:5:\"MchID\";s:3:\"123\";s:3:\"KEY\";s:4:\"3123\";s:5:\"pcode\";s:1:\"1\";}",
        "is_online": "1",
        "enabled": "1",
        "sort_order": "1",
        "cod_regions": ""
      },
      {
        "store_id": 0,
        "payment_code": "super_coupon_pay",
        "payment_name": "消费券",
        "payment_desc": "",
        "config": "a:1:{s:5:\"pcode\";s:0:\"\";}",
        "is_online": 1,
        "enabled": 1,
        "sort_order": 0,
        "cod_regions": "",
        "selected": 1
      }
    ],
  
    "deposit_account": {
      "account_id": "6593",
      "user_id": "6609",
      "account": "13880532794",
      "password": "06d26dac144d17f1b6ec8dbe450b7a3e",
      "money": "99999.96",
      "frozen": "0.00",
      "real_name": "xiaolisn",
      "pay_status": "ON",
      "add_time": "1472062435",
      "last_update": "1472091209",
      "storemoney": null,
      "storefrozen": null,
      "co_money": null,
      "co_frozen": null,
      "super_money": "2900.06"
    },
    "tradeNo": "20161202075155722442,20161205080924851135"
  }
}
</pre>

## <a name="&act=confirm_pay"/>提交支付
地址：&act=confirm_pay
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
payment_code     |  Y  |string | deposit  |支付方式编码:deposit：余额支付；alipay：支付宝支付；weixinpay：微信支付；super_coupon_pay:消费券支付
password|  Y  |string | 12345678  |支付密码
tradeNo|  Y  |string |20161129142017749546 |多个交易号用","分开,如："20161129142017749546, 20161129142017749546"

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回支付结果（支付方式不同，则返回数据也不同。余额支付：返回订单信息；银联支付：返回tn)

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
tradeInfo    |  是  |list |                    |交易详情
&ensp;&ensp;└ trade_id  |  是  |int |  40904              |交易ID
&ensp;&ensp;└ tradeNo |  是  |string |     20161129142017749546  |交易号
 

### 接口返回值示例
<pre>
银联支付：
{
  "code": 0,
  "msg": "success",
  "data": {
    "tn": "801048284499487373006"
  }
}

余额支付：
{
  "code": 0,
  "msg": "success",
  "data": {
    "tradeInfo": {
      "40904": {
        "trade_id": "40904",
        "tradeNo": "20161129142017749546",
        "outTradeNo": "",
        "payTradeNo": "",
        "merchantId": "",
        "bizOrderId": "1633358695",
        "bizIdentity": "trade10001",
        "buyer_id": "6609",
        "seller_id": "307",
        "amount": "0.01",
        "status": "ACCEPTED",
        "payment_code": "deposit",
        "payment_bank": "",
        "pay_alter": "0",
        "tradeCat": "SHOPPING",
        "payType": "SHIELD",
        "flow": "outlay",
        "fundchannel": "零钱",
        "payTerminal": "",
        "title": "支付 - 0101",
        "buyer_remark": "",
        "seller_remark": "",
        "add_time": "1480396858",
        "pay_time": "1480937511",
        "end_time": "1480471044",
        "account_type": null,
        "pay_tradeNo": null,
        "is_searched": "0"
      } 
    }
  }
}
</pre>


## <a name="&act=pay_result_sign"/>支付成功后验签
地址：&act=pay_result_sign
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
sign     |  Y  |string |   |数字签名
pay_result|  Y  |string | success  |支付返回专题
tn|  Y  |string |20161129142017749546 |预交易号
cert_id|  Y  |string |29142017749546 | 
payment_code|  Y  |string |alipay |支付方式编码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回支付结果

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
sign_result    |  是  |string |   OK  |（"OK":成功；"FAIL":失败")

 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "sign_result": "OK"
  }
}
</pre>