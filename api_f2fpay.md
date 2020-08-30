文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=f2fpay

## 接口文档

## <a name="list"/>订单接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[给消费者发送支付请求](&act=send_order_to_buyer)|N|api |pc-web|&act=send_order_to_buyer| POST| YES |给消费者发送支付请求
[买家现金支付](&act=cash_pay)    | N |  api |  pc-web|&act=cash_pay    | POST    | YES     |买家现金支付
 
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



## <a name="&act=send_order_to_buyer"/>给消费者发送支付请求
地址：&act=send_order_to_buyer
### 接口输入
提交方式：POST
### 描述 

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
buyer_phone  |  Y  |string |13881055565|消费者电话号码
amount  |  Y  |float |102.02|消费金额
password|  Y  |string | 12345678  |支付密码


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id |  是  |int |  543  |生成的订单号
amount|  是  |float |  100.2  |消费金额
store_id|  是  |int | 606  |店铺ID
store_name|  是  |string |    |店铺账号


 
### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": [
    {
      "order_id": 545,
      "quantity": 1,
      "amount": 100,
      "store_id": "6609",
      "store_name": "xiaolisn",
      "type": null
    }
  ]
}
</pre>

## <a name="&act=cash_pay"/>买家现金支付
地址：&act=cash_pay
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
buyer_phone  |  Y  |string |13881055565|消费者电话号码
amount  |  Y  |float |102.02|消费金额
payment_code|  Y  |string |deposit|支付方式编码(余额支付：deposit；银联支付：minsheng_gateway）
password|  Y  |string | 12345678  |支付密码
 

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

 

### 接口返回值示例
<pre>


</pre>

