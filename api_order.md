文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=order

## 接口文档

## <a name="list"/>订单接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[获取运费列表](&act=get_shipping_list)| N |  api |  mobile-app|&act=get_shipping_list| POST| YES |获取运费列表
[提交所选商品](&act=buy_goods)    | N |  api |  mobile-app|&act=buy_goods    | POST    | YES     |提交所选商品
[提交订单](&act=confirm_buy)    | N |  api |  mobile-app|&act=confirm_buy    | POST    | YES     |提交订单
[根据订单号查询订单详情](&act=get_order_detail)    | N |  api |  mobile-app|&act=get_order_detail| POST| YES|根据订单号查询订单详情
[面对面支付订单提交](&act=face_pay)    | N |  api |  mobile-app|&act=face_pay| POST| YES|面对面支付订单提交
[修改订单地址](&act=modify_order_address)    | N |  api |  mobile-app|&act=modify_order_address| POST| YES|修改订单地址


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


## <a name="&act=get_shipping_list"/>获取运费列表
地址：&act=get_shipping_list
### 接口输入
提交方式：POST
### 描述 

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
store_id_list |  Y  |string |12577,274|店铺id，多家店铺用逗号分开


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
&ensp;&ensp;└ data  |  是  |list |                     |买家地址ID
&ensp;&ensp;&ensp;&ensp;└ shipping_id  |  是  |int |     392  |运费ID
&ensp;&ensp;&ensp;&ensp;└ store_id  |  是  |int |     66   |店铺ID号
&ensp;&ensp;&ensp;&ensp;└ shipping_name  |  是  |string | 顺丰          |运费名称
&ensp;&ensp;&ensp;&ensp;└ shipping_desc  |  是  |string |   顺丰  |运费描述
&ensp;&ensp;&ensp;&ensp;└ first_price  |  是  |string | 12  |首件价格
&ensp;&ensp;&ensp;&ensp;└ step_price  |  是  |string |  4  |附加价格

 
### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": [
    {
      "shipping_id": "9",
      "store_id": "274",
      "shipping_name": "火锅",
      "shipping_desc": "好吃得很",
      "first_price": "1.00",
      "step_price": "1.00",
      "cod_regions": null,
      "enabled": "1",
      "sort_order": "255"
    },
    {
      "shipping_id": "214",
      "store_id": "12577",
      "shipping_name": "沙发",
      "shipping_desc": "",
      "first_price": "480.00",
      "step_price": "0.00",
      "cod_regions": null,
      "enabled": "1",
      "sort_order": "255"
    },
    {
      "shipping_id": "213",
      "store_id": "18005",
      "shipping_name": "运费须知",
      "shipping_desc": "每增加一件 运费增加20",
      "first_price": "20.00",
      "step_price": "0.00",
      "cod_regions": null,
      "enabled": "1",
      "sort_order": "255"
    }
  ]
}
</pre>



## <a name="&act=buy_goods"/>提交所选商品
地址：&act=buy_goods
### 接口输入
提交方式：POST
### 描述 

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
shipping_id |  Y  |string |12,14,202|运费列表，每个店铺对应一个ID，以逗号分开
goods_list     |  Y  |string |[{"store_id": "537","goods_id": "246","spec_id": "309","quantity": "3"},{"store_id": "2424","goods_id": "841","spec_id": "1585","quantity": "1"},{"store_id": "2424","goods_id": "837","spec_id": "1581","quantity": "1"}]|商品列表信息，json格式


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
my_address |  是  |list |                    |买家地址列表
&ensp;&ensp;└ addrs  |  是  |list |                     |买家地址ID
&ensp;&ensp;&ensp;&ensp;└ addr_id  |  是  |int |     392               |买家地址ID
&ensp;&ensp;&ensp;&ensp;└ user_id  |  是  |int |     66               |买家ID号
&ensp;&ensp;&ensp;&ensp;└ consignee  |  是  |string |    登哥               |买家姓名
&ensp;&ensp;&ensp;&ensp;└ region_id  |  是  |int |     3               |区域ID
&ensp;&ensp;&ensp;&ensp;└ region_name  |  是  |string |     中国\t北京市\t东城               |区域名称
&ensp;&ensp;&ensp;&ensp;└ address  |  是  |string |     阿里中心13F               |详细地址
&ensp;&ensp;&ensp;&ensp;└ zipcode  |  是  |string |    629568              |邮编
&ensp;&ensp;&ensp;&ensp;└ phone_tel  |  是  |string |  028-86559888               |联系电话（座机）
&ensp;&ensp;&ensp;&ensp;└ phone_mob  |  是  |string |     13886665555               |联系电话（手机）
&ensp;&ensp;&ensp;&ensp;└ default  |  是  |int |     1               |师傅默认地址（1：默认地址；0：不是）
shipping_methods|  是  |list |                    |配送方式列表
&ensp;&ensp;└ shipping_id  |  是  |list |                     |配送方式ID
&ensp;&ensp;&ensp;&ensp;└ shipping_id  |  是  |int |     392               |配送方式ID
&ensp;&ensp;&ensp;&ensp;└ store_id  |  是  |int |     66               |商铺ID
&ensp;&ensp;&ensp;&ensp;└ shipping_name  |  是  |string |    顺丰               |配送方式名称
&ensp;&ensp;&ensp;&ensp;└ shipping_desc  |  是  |string |  顺丰最快              |配送方式说明
&ensp;&ensp;&ensp;&ensp;└ first_price  |  是  |float |    11.00               |首件邮费
&ensp;&ensp;&ensp;&ensp;└ step_price  |  是  |float |    0.00          |附加邮费
&ensp;&ensp;&ensp;&ensp;└ enabled  |  是  |int |    1              |是否可用
&ensp;&ensp;&ensp;&ensp;└ sort_order  |  是  |int |  4               |序号
&ensp;&ensp;&ensp;&ensp;└ logist_fees  |  是  |string |   12.00                 |附加费总额

 
### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "data": {
      "my_address": {
        "38": {
          "addr_id": "38",
          "user_id": "6609",
          "consignee": "刘晶",
          "region_id": "127",
          "region_name": "中国\t山西省\t运城市",
          "address": "23时代发生地方",
          "zipcode": "0500505",
          "phone_tel": "18132620802",
          "phone_mob": "18132620802",
          "default": null
        }
      "shipping_methods": {
        "10": {
          "shipping_id": "10",
          "store_id": "307",
          "shipping_name": "顺丰",
          "shipping_desc": "",
          "first_price": "10.00",
          "step_price": "0.00",
          "cod_regions": null,
          "enabled": "1",
          "sort_order": "255",
          "logist_fees": 10
        }
      }     
    }
  }
}
</pre>

## <a name="&act=confirm_buy"/>提交订单
地址：&act=confirm_buy
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
addr_id     |  Y  |int | 2041                          |收货地址ID
shipping_id|  Y  |int |122，155     |配送方式ID，多家店铺以逗号分开
get_order_id |  Y  |int |1                           |1:只返回订单号，0或者不传：返回详细列表
goods_list     |  Y  |string |[{"store_id": "537","goods_id": "246","spec_id": "309","quantity": "3","shipping_id":"15"},{"store_id": "2424","goods_id": "841","spec_id": "1585","quantity": "1","shipping_id":"12"},{"store_id": "2424","goods_id": "837","spec_id": "1581","quantity": "1","shipping_id":"12"}]|商品列表信息，json格式

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id    |  是  |int |      486              |订单号
quantity    |  是  |int |       2             |商品数量
amount    |  是  |float |      86.4              |金额
store_id    |  是  |int |     537               |店铺ID
store_name    |  是  |int |   碧斯诺兰专卖店                 |店铺名称
type    |  是  |int |       null             | 
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": [
    {
      "order_id": 486,
      "quantity": 3,
      "amount": 86.4,
      "store_id": "537",
      "store_name": "蓝月亮",
      "type": null
    },
    {
      "order_id": 487,
      "quantity": 5,
      "amount": 439.4,
      "store_id": "2424",
      "store_name": "碧斯诺兰专卖店",
      "type": null
    }
  ]
}

</pre>

## <a name="&act=get_order_detail"/>根据订单号查询订单详情
地址：&act=get_order_detail
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 2041                          |订单ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回订单详情

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_info    |  是  |list |                    |订单详情
&ensp;&ensp;└ order_id  |  是  |int |     2041      |订单ID


### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "order_info": {
      "order_id": "489",
      "order_sn": "1634083431",
      "type": "material",
      "extension": "normal",
      "seller_id": "2424",
      "seller_name": "碧斯诺兰专卖店",
      "buyer_id": "6609",
      "buyer_name": "xiaolisn",
      "buyer_email": "",
      "status": "11",
      "add_time": "1474876525",
      "payment_id": null,
      "payment_name": null,
      "payment_code": "",
      "out_trade_sn": "",
      "pay_time": null,
      "pay_message": "",
      "ship_time": null,
      "invoice_no": null,
      "finished_time": "0",
      "goods_amount": "439.40",
      "discount": "0.00",
      "order_amount": "439.40",
      "evaluation_status": "0",
      "evaluation_time": "0",
      "anonymous": "0",
      "postscript": "",
      "pay_alter": "0",
      "express_company": "",
      "store_id": "2424",
      "store_name": "碧斯诺兰专卖店",
      "owner_name": "李良波",
      "owner_card": "510131198104207927",
      "region_id": "358",
      "region_name": "中国\t四川省\t成都",
      "address": "蒲江",
      "zipcode": "611630",
      "tel": "18048520567",
      "sgrade": "1",
      "apply_remark": "",
      "credit_value": "1",
      "praise_rate": "100.00",
      "domain": "",
      "state": "1",
      "close_reason": "",
      "end_time": "0",
      "certification": "",
      "sort_order": "65535",
      "recommended": "0",
      "theme": "default|style4",
      "wap_theme": "",
      "store_banner": null,
      "store_logo": null,
      "description": null,
      "image_1": "data/files/mall/application/store_2424_1.jpg",
      "image_2": "data/files/mall/application/store_2424_2.jpg",
      "image_3": "",
      "im_qq": "",
      "im_ww": "",
      "im_msn": "",
      "enable_groupbuy": "0",
      "enable_radar": "1",
      "latlng": "",
      "rewardpool_rate": "0.0000",
      "order_add_time": "1480985981"
    },
    "order_detail": {
      "goods_list": {
        "547": {
          "rec_id": "547",
          "order_id": "489",
          "goods_id": "841",
          "goods_name": "碧斯诺兰CC气垫霜",
          "spec_id": "1585",
          "specification": "",
          "price": "268.00",
          "quantity": "1",
          "goods_image": "data/files/store_2424/goods_98/small_201610052044585463.jpg",
          "evaluation": "0",
          "comment": "",
          "credit_value": "0",
          "is_valid": "1",
          "status": ""
        },
        "548": {
          "rec_id": "548",
          "order_id": "489",
          "goods_id": "837",
          "goods_name": "碧斯诺兰女神卫生巾",
          "spec_id": "1581",
          "specification": "",
          "price": "85.00",
          "quantity": "1",
          "goods_image": "data/files/store_2424/goods_64/small_201610011647449625.jpg",
          "evaluation": "0",
          "comment": "",
          "credit_value": "0",
          "is_valid": "1",
          "status": ""
        }
      },
      "order_extm": {
        "order_id": "489",
        "consignee": "刘晶",
        "region_id": "127",
        "region_name": "中国\t山西省\t运城市",
        "address": "23时代发生地方",
        "zipcode": "0500505",
        "phone_tel": "18132620802",
        "phone_mob": "18132620802",
        "shipping_id": "1",
        "shipping_name": "",
        "shipping_fee": "0.00"
      },
      "order_logs": []
    }
  }
}
</pre>


## <a name="&act=face_pay"/>面对面支付订单提交
地址：&act=face_pay
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
seller_id     |  Y  |int | 2041     |店铺ID
seller_name|  Y  |string |122                           |店铺名称
amount |  Y  |float |122.23                           |金额
remark|  N |string |吃火锅  |支付备注
get_order_id |  N  |int | 1  |1:只返回订单号order_id；0或不传：返回订单详情

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id    |  是  |int |      486              |订单号
quantity    |  是  |int |       2             |商品数量
amount    |  是  |float |      86.4              |金额
store_id    |  是  |int |     537               |店铺ID
store_name    |  是  |int |   碧斯诺兰专卖店                 |店铺名称
type    |  是  |int |       null             | 
 

### 接口返回值示例
<pre>
只返回订单号order_id
{
  "code": 0,
  "msg": "success",
  "data": "534"
}

返回订单详情
{
  "code": 0,
  "msg": "success",
  "data": [
    {
      "order_id": 533,
      "quantity": 1,
      "amount": 100,
      "store_id": 218,
      "store_name": "面对面火锅",
      "type": null
    }
  ]
}


## <a name="&act=modify_order_address"/>修改订单地址
地址：&act=modify_order_address
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 2041     |订单ID
addr_id|  Y  |string |122                           |地址ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id    |  是  |int |      486              |订单号
quantity    |  是  |int |       2             |商品数量
amount    |  是  |float |      86.4              |金额
store_id    |  是  |int |     537               |店铺ID
store_name    |  是  |int |   碧斯诺兰专卖店                 |店铺名称
type    |  是  |int |       null             | 
 

### 接口返回值示例
<pre>
只返回订单号order_id
{
  "code": 0,
  "msg": "success",
  "data": "534"
}

返回订单详情
{
  "code": 0,
  "msg": "success",
  "data": [
    {
      "order_id": 533,
      "quantity": 1,
      "amount": 100,
      "store_id": 218,
      "store_name": "面对面火锅",
      "type": null
    }
  ]
}
</pre>