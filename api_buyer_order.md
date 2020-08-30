文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=buyer_order

## 接口文档

## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[获取订单列表](&act=get_orders)    | N |  api |  mobile-app|&act=get_orders    | GET    | YES     |获取订单列表
[查看订单详情](&act=view)    | N |  api |  mobile-app|&act=view    | GET    | YES     |查看订单详情
[取消订单](&act=cancel_order)| N |  api |  mobile-app|&act=cancel_order    | GET    | YES     |取消订单
[删除订单](&act=del_order)| N |  api |  mobile-app|&act=del_order    | GET    | YES     |删除订单
[确认收货](&act=confirm_order)| N |  api |  mobile-app|&act=confirm_order    | GET    | YES     |确认收货
[获取待评价商品](&act=get_evaluate_goods)| N |  api |  mobile-app|&act=get_evaluate_goods|GET|YES|获取待评价商品
[提交评价](&act=submit_evaluate)| N |  api |  mobile-app|&act=submit_evaluate    | GET    | YES|提交评价

 
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



## <a name="&act=get_orders"/>获取订单列表
地址：&act=get_orders
### 接口输入
提交方式：GET
### 描述
 

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_status|  N  |int | 11 |订单状态(11:待付款;20:待发货;30:已发货;40:已收货;0:取消），不传则表示所有状态
order_type|  N  |string |material|订单分类(material:普通订单；phone：话费充值；oil：油卡充值；oil_card:油卡办理）


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
orders |  是  |list |                    |订单列表
&ensp;&ensp;└ order_id  |  是  |int |     480                |订单号
&ensp;&ensp;└ order_sn  |  是  |int |     1633902612               |订单号
&ensp;&ensp;└ type  |  是  |string |material|订单类型(material:普通订单；phone：话费充值；oil：油卡充值）
&ensp;&ensp;└ extension  |  是  |string |    normal               |扩展字段
&ensp;&ensp;└ seller_id  |  是  |int |     537               |店铺ID
&ensp;&ensp;└ seller_name  |  是  |string |   蓝月亮专卖                 |店铺名称
&ensp;&ensp;└ buyer_id  |  是  |string |     66009               |买家ID
&ensp;&ensp;└ buyer_name  |  是  |string |    xiaolisn              |买家账号
&ensp;&ensp;└ status  |  是  |int |  11               |订单状态(11:待付款;20:待发货;30:已发货;40:已收货;0:取消）
&ensp;&ensp;└ add_time  |  是  |string |     1480935975               |下单时间
&ensp;&ensp;└ add_time2  |  是  |string |     2016-12-05 19:06:15               |下单时间
&ensp;&ensp;└ payment_id  |  是  |int |     1               |支付方式ID
&ensp;&ensp;└ payment_name  |  是  |string |     钱包支付               |支付方式名称
&ensp;&ensp;└ payment_code  |  是  |string |     desposit              |支付方式编码
&ensp;&ensp;└ pay_time  |  是  |string |    1480935975              |支付时间
&ensp;&ensp;└ pay_time2  |  是  |string |    2016-12-05 19:06:15               |支付时间
&ensp;&ensp;└ ship_time  |  是  |string |     1480935975              |发货时间
&ensp;&ensp;└ ship_time2  |  是  |string |    2016-12-05 19:06:15               |发货时间
&ensp;&ensp;└ invoice_no  |  是  |string |                   |发票
&ensp;&ensp;└ finished_time  |  是  |string |    1480935975             |完成时间
&ensp;&ensp;└ finished_time2  |  是  |string |    2016-12-05 19:06:15             |完成时间
&ensp;&ensp;└ goods_amount  |  是  |float |     85.00               |商品金额
&ensp;&ensp;└ evaluation_status  |  是  |int |     0             |评价状态。0：未评价；1：已评价
&ensp;&ensp;└ evaluation_time  |  是  |int |    1480935975              |评价时间 
&ensp;&ensp;└ evaluation_time2  |  是  |int |    2016-12-05 19:06:15              |评价时间 
&ensp;&ensp;└ anonymous  |  是  |int |     1               |是否匿名评价。0：不是；1：是
&ensp;&ensp;└ postscript  |  是  |string |     好，很好，非常好               |评语
&ensp;&ensp;└ evaluation_status  |  是  |int |     1               |评价状态。1：未评价；0：已评价
&ensp;&ensp;└ pay_alter  |  是  |int |                  |  
&ensp;&ensp;└ express_company  |  是  |string |     顺丰             |  快递公司
&ensp;&ensp;└ order_goods  |  是  |list |                |  订单商品列表
&ensp;&ensp;&ensp;&ensp;└ rec_id  |  是  |int |   534             |  记录ID
&ensp;&ensp;&ensp;&ensp;└ order_id  |  是  |int |   480             |  订单ID
&ensp;&ensp;&ensp;&ensp;└ goods_id  |  是  |int |   goods_id             |  商品ID
&ensp;&ensp;&ensp;&ensp;└ goods_name  |  是  |string |  蓝月亮洋甘菊香宝宝专用洗衣液袋装1kg              |  商品名称
&ensp;&ensp;&ensp;&ensp;└ spec_id  |  是  |int |     309           |  规格ID
&ensp;&ensp;&ensp;&ensp;└ specification  |  是  |string |                |  规格描述
&ensp;&ensp;&ensp;&ensp;└ price  |  是  |float |    28.80            |  商品价格
&ensp;&ensp;&ensp;&ensp;└ quantity  |  是  |int |   3             |  商品数量
&ensp;&ensp;&ensp;&ensp;└ goods_image  |  是  |string |data/files/small_201607291155054547.jpg|  商品图片地址
&ensp;&ensp;&ensp;&ensp;└ evaluation  |  是  |int |                |  评价得分
&ensp;&ensp;&ensp;&ensp;└ comment  |  是  |float |                |  商品说明
&ensp;&ensp;&ensp;&ensp;└ credit_value  |  是  |int |                |  商品数量
&ensp;&ensp;&ensp;&ensp;└ is_valid  |  是  |string | 0               |  商品图片地址
&ensp;&ensp;&ensp;&ensp;└ status  |  是  |int |                |  评价得分

 
### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "orders": {
      "480": {
        "order_id": "480",
        "order_sn": "1633902612",
        "type": "material",
        "extension": "normal",
        "seller_id": "537",
        "seller_name": "蓝月亮",
        "buyer_id": "6609",
        "buyer_name": "xiaolisn",
        "buyer_email": "",
        "status": "11",
        "add_time": "1480935975",
        "payment_id": null,
        "payment_name": null,
        "payment_code": "",
        "out_trade_sn": "",
        "pay_time": null,
        "pay_message": "",
        "ship_time": null,
        "invoice_no": null,
        "finished_time": "0",
        "goods_amount": "86.40",
        "discount": "0.00",
        "order_amount": "86.40",
        "evaluation_status": "0",
        "evaluation_time": "0",
        "anonymous": "0",
        "postscript": "",
        "pay_alter": "0",
        "express_company": "",
        "order_goods": {
          "534": {
            "rec_id": "534",
            "order_id": "480",
            "goods_id": "246",
            "goods_name": "蓝月亮洋甘菊香宝宝专用洗衣液袋装1kg",
            "spec_id": "309",
            "specification": "",
            "price": "28.80",
            "quantity": "3",
            "goods_image": "data/files/store_537/goods_105/small_201607291155054547.jpg",
            "evaluation": "0",
            "comment": "",
            "credit_value": "0",
            "is_valid": "1",
            "status": ""
          }
        }
      },
      "481": {
        "order_id": "481",
        "order_sn": "1633967206",
        "type": "material",
        "extension": "normal",
        "seller_id": "2424",
        "seller_name": "碧斯诺兰专卖店",
        "buyer_id": "6609",
        "buyer_name": "xiaolisn",
        "buyer_email": "",
        "status": "11",
        "add_time": "1480936070",
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
        "order_goods": {
          "535": {
            "rec_id": "535",
            "order_id": "481",
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
          "536": {
            "rec_id": "536",
            "order_id": "481",
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
        }
      }
    },
    "page": {
      "limit": "0,10",
      "curr_page": 1,
      "pageper": 10,
      "item_count": "34"
    }
  }
}
</pre>

## <a name="&act=view"/>查看订单详情
地址：&act=view
### 接口输入
提交方式：GET

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 2041     |订单ID
order_type|  Y  |string | material|订单分类(material:普通订单；phone：话费充值；oil：油卡充值；oil_card:油卡办理）

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
&ensp;&ensp;└ order_id  |  是  |int |     3               |订单ID


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


## <a name="&act=cancel_order"/>取消订单
地址：&act=cancel_order
### 接口输入
提交方式：GET

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 106                          |订单ID
order_type|  Y  |string | material|订单分类(material:普通订单；phone：话费充值；oil：油卡充值；oil_card:油卡办理）
  
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id    |  是  |int |                    |订单ID
result    |  是  |string |                    |操作结果
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "$order_id": "489",
    "result": "ok"
  }
}
</pre>

## <a name="&act=del_order"/>删除订单
地址：&act=del_order
### 接口输入
提交方式：GET

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 106  |订单ID
order_type|  Y  |string | material|订单分类(material:普通订单；phone：话费充值；oil：油卡充值；oil_card:油卡办理）
  
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id    |  是  |int |                    |订单ID
result    |  是  |string |                    |操作结果
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "$order_id": "489",
    "result": "ok"
  }
}
</pre>

## <a name="&act=confirm_order"/>确认收货
地址：&act=confirm_order
### 接口输入
提交方式：GET

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 106                          |订单ID

  
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id    |  是  |int |                    |订单ID
result    |  是  |string |                    |操作结果
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "$order_id": "489",
    "result": "ok"
  }
}
</pre>


## <a name="&act=get_evaluate_goods"/>获取待评价商品
地址：&act=get_evaluate_goods
### 接口输入
提交方式：GET

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
order_id     |  Y  |int | 106                          |订单ID
  
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_info    |  是  |list |                    |订单详情
goods_list    |  是  |list |                    |订单商品列表
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "order_info": {
      "order_id": "487",
      "order_sn": "1633953447",
      "type": "material",
      "extension": "normal",
      "seller_id": "2424",
      "seller_name": "碧斯诺兰专卖店",
      "buyer_id": "6609",
      "buyer_name": "xiaolisn",
      "buyer_email": "",
      "status": "40",
      "add_time": "1480936466",
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
      "express_company": ""
    },
    "goods_list": {
      "544": {
        "rec_id": "544",
        "order_id": "487",
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
      "545": {
        "rec_id": "545",
        "order_id": "487",
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
    }
  }
}
</pre>


## <a name="&act=submit_evaluate"/>提交评价
地址：&act=submit_evaluate
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
rec_id     |  Y  |int | 106                          |订单商品记录ID
order_id     |  Y  |int | 106                          |订单ID
goods_id |  Y  |int | 106                          |商品ID
evaluation|  Y  |int | 1                         |评价得分，好评：5，中评：3，差评：1
comment|  Y  |string | 好，很好，非常好         |评价内容
evaluation_img|Y |string | data:image/jpg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD/2 |图片base64编码，多张图片用双竖线分割

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
goods_ids    |  是  |list |goods_ids |评价的商品ID
result    |  是  |string |                    |操作结果
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",  
  "result": "ok"
}
</pre>

## <a name="&act=upload_evaluate_img"/>提交评价图片
地址：&act=upload_evaluate_img
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
rec_id     |  Y  |int | 106                          |订单商品记录ID
order_id     |  Y  |int | 106                          |订单ID
evaluation_img|  Y  |string | data:image/jpg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD/2 |图片base64编码


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 |  

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
goods_ids    |  是  |list |goods_ids |评价的商品ID
result    |  是  |string |                    |操作结果
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",  
  "result": "ok"
}
</pre>