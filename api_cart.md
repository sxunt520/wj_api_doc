文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=cart

## 接口文档

## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[加入购物车](&act=add_goods)    | N |  api |  mobile-app|&act=add_goods    | POST    | YES     |商品加入购物车
[从购物车单个删除商品](&act=drop_goods)    | N |  api |  mobile-app|&act=drop_goods    | POST    | YES     |从购物车删除商品（单个）
[从购物车批量删除商品](&act=drop_goods_batch)    | N |  api |  mobile-app|&act=drop_goods_batch    | POST    | YES     |从购物车删除商品（批量）
[修改购物车商品数量](&act=update_goods)| N |  api |  mobile-app|&act=update_goods    | POST    | YES     |修改购物车商品数量
[获取购物车商品数量](&act=get_goods_count)    | N |  api |  mobile-app|&act=get_goods_count    | POST    | YES     |获取购物车商品列表
[获取购物车商品列表](&act=get_goods_list)    | N |  api |  mobile-app|&act=get_goods_list    | POST    | YES     |获取购物车商品列表
[判断商品是否已经收藏](&act=get_is_collect)    | N |  api |  mobile-app|&act=get_is_collect    | POST    | YES     |判断商品是否已经收藏


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



## <a name="&act=add_goods"/>加入购物车
地址：&act=add_goods
### 接口输入
提交方式：POST
### 描述
quantity 如果不传则默认为1

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
spec_id     |  Y  |int | 106                          |商品规格ID
quantity     |  Y  |int |1                           |加入购物车数量
get_goods_list|  N  |int |1                           |0.只返回操作状态；1.返回购物车所有商品

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
cart_info    |  是  |list |                    |购物车情况
&ensp;&ensp;└ quantity  |  是  |int |     3               |购物车中商品总数量
&ensp;&ensp;└ amount   |  是  |float |    188.00                |购物车中商品总金额
&ensp;&ensp;└ kinds   |  是  |int |       2             |购物车中商品种类数量
cart_detail    |  是  |list |                    |购物车中商品详情
&ensp;&ensp;└store_id   |  是  |list |    18                |店铺ID
&ensp;&ensp;&ensp;&ensp;└store_name  |  是  |string |   某热水器直营专卖店                 |店铺名称
&ensp;&ensp;&ensp;&ensp;└amount   |  是  |float |      188.00              |购物车中该店铺商品总金额
&ensp;&ensp;&ensp;&ensp;└quantity   |  是  |int |      1              |购物车中该店铺商品数量    
&ensp;&ensp;&ensp;&ensp;└kinds      |  是  |int |      1              |购物车中该店铺商品种类数量      
&ensp;&ensp;&ensp;&ensp;└goods      |  是  |list |                    |购物车中该店铺商品详细信息
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└rec_id |  是  |int |   100                 |该商品在购物车中ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└user_id|  是  |int |    609                |用户ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└session_id|  是  |int | dab06fb8165c405b09a4                   |sessionID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_id |  是  |int |   69                 |店铺ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_id|  是  |int |   28                 |商品ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_name|  是  |int |HANNOVER即热式厨房热水宝上出水电热水器|商品名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└spec_id|  是  |int | 23      |规格ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└specification|  是  |int |红色                   |规格名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└price|  是  |int |  188.00                  |商品价格
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└quantity|  是  |int | 1                   |商品数量
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_image|  是  |int |data/files/small_201607151023367293.png|商品图片地址
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_name|  是  |int |某热水器直营专卖店|店铺名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└subtotal|  是  |int |  188.00                  |该商品金额

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "cart_info": {
      "quantity": 3,
      "amount": 36660,
      "kinds": 3
    },
    "cart_detail": {
      "307": {
        "store_name": "汉诺威、首乐热水器直营专卖",
        "amount": 2860,
        "quantity": 2,
        "goods": [
          {
            "rec_id": "2038",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "61",
            "goods_name": "HANNOVER/汉诺威GD8小厨宝 即热式厨房热水宝上出水电热水器（红/蓝/黑色）",
            "spec_id": "106",
            "specification": "",
            "price": "880.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_16/small_201607151023367293.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 880
          },
          {
            "rec_id": "2039",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "60",
            "goods_name": "HANNOVER/汉诺威MF1即热式电热水器 家用速热超薄洗澡机热水器（白/银/金色）",
            "spec_id": "105",
            "specification": "",
            "price": "1980.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_84/small_201607151014443290.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 1980
          }
        ],
        "kinds": 2
      },
      "1621": {
        "store_name": "",
        "amount": 33800,
        "quantity": 1,
        "goods": [
          {
            "rec_id": "2040",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "1621",
            "goods_id": "109",
            "goods_name": "雅贝经济版",
            "spec_id": "159",
            "specification": "颜色:白色 尺码:3520*1570*1490",
            "price": "33800.00",
            "quantity": "1",
            "goods_image": "data/files/store_1621/goods_122/small_201607281652027662.png",
            "store_name": "",
            "subtotal": 33800
          }
        ],
        "kinds": 1
      }
    }
  }
}
</pre>

## <a name="&act=drop_goods"/>从购物车中单个删除商品
地址：&act=drop_goods
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
rec_id     |  Y  |int | 2041                          |购物车记录ID
get_goods_list|  N  |int |1                           |0.只返回操作状态；1.返回购物车所有商品

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
cart_info    |  是  |list |                    |购物车情况
&ensp;&ensp;└ quantity  |  是  |int |     3               |购物车中商品总数量
&ensp;&ensp;└ amount   |  是  |float |    188.00                |购物车中商品总金额
&ensp;&ensp;└ kinds   |  是  |int |       2             |购物车中商品种类数量
cart_detail    |  是  |list |                    |购物车中商品详情
&ensp;&ensp;└store_id   |  是  |list |    18                |店铺ID
&ensp;&ensp;&ensp;&ensp;└store_name  |  是  |string |   某热水器直营专卖店                 |店铺名称
&ensp;&ensp;&ensp;&ensp;└amount   |  是  |float |      188.00              |购物车中该店铺商品总金额
&ensp;&ensp;&ensp;&ensp;└quantity   |  是  |int |      1              |购物车中该店铺商品数量    
&ensp;&ensp;&ensp;&ensp;└kinds      |  是  |int |      1              |购物车中该店铺商品种类数量      
&ensp;&ensp;&ensp;&ensp;└goods      |  是  |list |                    |购物车中该店铺商品详细信息
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└rec_id |  是  |int |   100                 |该商品在购物车中ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└user_id|  是  |int |    609                |用户ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└session_id|  是  |int | dab06fb8165c405b09a4                   |sessionID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_id |  是  |int |   69                 |店铺ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_id|  是  |int |   28                 |商品ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_name|  是  |int |HANNOVER即热式厨房热水宝上出水电热水器|商品名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└spec_id|  是  |int | 23      |规格ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└specification|  是  |int |红色                   |规格名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└price|  是  |int |  188.00                  |商品价格
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└quantity|  是  |int | 1                   |商品数量
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_image|  是  |int |data/files/small_201607151023367293.png|商品图片地址
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_name|  是  |int |某热水器直营专卖店|店铺名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└subtotal|  是  |int |  188.00                  |该商品金额

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "cart_info": {
      "quantity": 2,
      "amount": 2860,
      "kinds": 2
    },
    "cart_detail": {
      "307": {
        "store_name": "汉诺威、首乐热水器直营专卖",
        "amount": 2860,
        "quantity": 2,
        "goods": [
          {
            "rec_id": "2038",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "61",
            "goods_name": "HANNOVER/汉诺威GD8小厨宝 即热式厨房热水宝上出水电热水器（红/蓝/黑色）",
            "spec_id": "106",
            "specification": "",
            "price": "880.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_16/small_201607151023367293.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 880
          },
          {
            "rec_id": "2039",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "60",
            "goods_name": "HANNOVER/汉诺威MF1即热式电热水器 家用速热超薄洗澡机热水器（白/银/金色）",
            "spec_id": "105",
            "specification": "",
            "price": "1980.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_84/small_201607151014443290.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 1980
          }
        ],
        "kinds": 2
      }
    }
  }
}
</pre>

## <a name="&act=drop_goods_batch"/>从购物车中批量删除商品
地址：&act=drop_goods_batch
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
rec_id_list     |  Y  |string | "2041,2042,2043"                          |购物车记录ID
get_goods_list|  N  |int |1                           |0.只返回操作状态；1.返回购物车所有商品

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
cart_info    |  是  |list |                    |购物车情况
&ensp;&ensp;└ quantity  |  是  |int |     3               |购物车中商品总数量
&ensp;&ensp;└ amount   |  是  |float |    188.00                |购物车中商品总金额
&ensp;&ensp;└ kinds   |  是  |int |       2             |购物车中商品种类数量
cart_detail    |  是  |list |                    |购物车中商品详情
&ensp;&ensp;└store_id   |  是  |list |    18                |店铺ID
&ensp;&ensp;&ensp;&ensp;└store_name  |  是  |string |   某热水器直营专卖店                 |店铺名称
&ensp;&ensp;&ensp;&ensp;└amount   |  是  |float |      188.00              |购物车中该店铺商品总金额
&ensp;&ensp;&ensp;&ensp;└quantity   |  是  |int |      1              |购物车中该店铺商品数量    
&ensp;&ensp;&ensp;&ensp;└kinds      |  是  |int |      1              |购物车中该店铺商品种类数量      
&ensp;&ensp;&ensp;&ensp;└goods      |  是  |list |                    |购物车中该店铺商品详细信息
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└rec_id |  是  |int |   100                 |该商品在购物车中ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└user_id|  是  |int |    609                |用户ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└session_id|  是  |int | dab06fb8165c405b09a4                   |sessionID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_id |  是  |int |   69                 |店铺ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_id|  是  |int |   28                 |商品ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_name|  是  |int |HANNOVER即热式厨房热水宝上出水电热水器|商品名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└spec_id|  是  |int | 23      |规格ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└specification|  是  |int |红色                   |规格名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└price|  是  |int |  188.00                  |商品价格
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└quantity|  是  |int | 1                   |商品数量
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_image|  是  |int |data/files/small_201607151023367293.png|商品图片地址
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_name|  是  |int |某热水器直营专卖店|店铺名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└subtotal|  是  |int |  188.00                  |该商品金额

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "cart_info": {
      "quantity": 2,
      "amount": 2860,
      "kinds": 2
    },
    "cart_detail": {
      "307": {
        "store_name": "汉诺威、首乐热水器直营专卖",
        "amount": 2860,
        "quantity": 2,
        "goods": [
          {
            "rec_id": "2038",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "61",
            "goods_name": "HANNOVER/汉诺威GD8小厨宝 即热式厨房热水宝上出水电热水器（红/蓝/黑色）",
            "spec_id": "106",
            "specification": "",
            "price": "880.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_16/small_201607151023367293.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 880
          },
          {
            "rec_id": "2039",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "60",
            "goods_name": "HANNOVER/汉诺威MF1即热式电热水器 家用速热超薄洗澡机热水器（白/银/金色）",
            "spec_id": "105",
            "specification": "",
            "price": "1980.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_84/small_201607151014443290.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 1980
          }
        ],
        "kinds": 2
      }
    }
  }
}
</pre>


## <a name="&act=update_goods"/>修改商品数量
地址：&act=update_goods
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
spec_id_list     |  Y  |string | [{"spec_id": "309","quantity": "3"},{"spec_id": "1585","quantity": "1"]|商品规格ID和数量
get_goods_list|  N  |int |1                           |0.只返回操作状态；1.返回购物车所有商品

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
cart_info    |  是  |list |                    |购物车情况
&ensp;&ensp;└ quantity  |  是  |int |     3               |购物车中商品总数量
&ensp;&ensp;└ amount   |  是  |float |    188.00                |购物车中商品总金额
&ensp;&ensp;└ kinds   |  是  |int |       2             |购物车中商品种类数量
cart_detail    |  是  |list |                    |购物车中商品详情
&ensp;&ensp;└store_id   |  是  |list |    18                |店铺ID
&ensp;&ensp;&ensp;&ensp;└store_name  |  是  |string |   某热水器直营专卖店                 |店铺名称
&ensp;&ensp;&ensp;&ensp;└amount   |  是  |float |      188.00              |购物车中该店铺商品总金额
&ensp;&ensp;&ensp;&ensp;└quantity   |  是  |int |      1              |购物车中该店铺商品数量    
&ensp;&ensp;&ensp;&ensp;└kinds      |  是  |int |      1              |购物车中该店铺商品种类数量      
&ensp;&ensp;&ensp;&ensp;└goods      |  是  |list |                    |购物车中该店铺商品详细信息
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└rec_id |  是  |int |   100                 |该商品在购物车中ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└user_id|  是  |int |    609                |用户ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└session_id|  是  |int | dab06fb8165c405b09a4                   |sessionID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_id |  是  |int |   69                 |店铺ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_id|  是  |int |   28                 |商品ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_name|  是  |int |HANNOVER即热式厨房热水宝上出水电热水器|商品名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└spec_id|  是  |int | 23      |规格ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└specification|  是  |int |红色                   |规格名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└price|  是  |int |  188.00                  |商品价格
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└quantity|  是  |int | 1                   |商品数量
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_image|  是  |int |data/files/small_201607151023367293.png|商品图片地址
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_name|  是  |int |某热水器直营专卖店|店铺名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└subtotal|  是  |int |  188.00                  |该商品金额

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "cart_info": {
      "quantity": 2,
      "amount": 2860,
      "kinds": 2
    },
    "cart_detail": {
      "307": {
        "store_name": "汉诺威、首乐热水器直营专卖",
        "amount": 2860,
        "quantity": 2,
        "goods": [
          {
            "rec_id": "2038",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "61",
            "goods_name": "HANNOVER/汉诺威GD8小厨宝 即热式厨房热水宝上出水电热水器（红/蓝/黑色）",
            "spec_id": "106",
            "specification": "",
            "price": "880.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_16/small_201607151023367293.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 880
          },
          {
            "rec_id": "2039",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "60",
            "goods_name": "HANNOVER/汉诺威MF1即热式电热水器 家用速热超薄洗澡机热水器（白/银/金色）",
            "spec_id": "105",
            "specification": "",
            "price": "1980.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_84/small_201607151014443290.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 1980
          }
        ],
        "kinds": 2
      }
    }
  }
}
</pre>

## <a name="&act=get_goods_count"/>获取购物车商品数量
地址：&act=get_goods_count
### 接口输入
提交方式：GET/POST

参数：无

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  int   | 见详参 | 购物车商品数量

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------

## <a name="&act=get_goods_list"/>获取购物车商品列表
地址：&act=get_goods_list
### 接口输入
提交方式：POST

参数：无

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购物车剩余商品列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
cart_info    |  是  |list |                    |购物车情况
&ensp;&ensp;└ quantity  |  是  |int |     3               |购物车中商品总数量
&ensp;&ensp;└ amount   |  是  |float |    188.00                |购物车中商品总金额
&ensp;&ensp;└ kinds   |  是  |int |       2             |购物车中商品种类数量
cart_detail    |  是  |list |                    |购物车中商品详情
&ensp;&ensp;└store_id   |  是  |list |    18                |店铺ID
&ensp;&ensp;&ensp;&ensp;└store_name  |  是  |string |   某热水器直营专卖店                 |店铺名称
&ensp;&ensp;&ensp;&ensp;└amount   |  是  |float |      188.00              |购物车中该店铺商品总金额
&ensp;&ensp;&ensp;&ensp;└quantity   |  是  |int |      1              |购物车中该店铺商品数量    
&ensp;&ensp;&ensp;&ensp;└kinds      |  是  |int |      1              |购物车中该店铺商品种类数量      
&ensp;&ensp;&ensp;&ensp;└goods      |  是  |list |                    |购物车中该店铺商品详细信息
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└rec_id |  是  |int |   100                 |该商品在购物车中ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└user_id|  是  |int |    609                |用户ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└session_id|  是  |int | dab06fb8165c405b09a4                   |sessionID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_id |  是  |int |   69                 |店铺ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_id|  是  |int |   28                 |商品ID号
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_name|  是  |int |HANNOVER即热式厨房热水宝上出水电热水器|商品名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└spec_id|  是  |int | 23      |规格ID
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└specification|  是  |int |红色                   |规格名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└price|  是  |int |  188.00                  |商品价格
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└quantity|  是  |int | 1                   |商品数量
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└goods_image|  是  |int |data/files/small_201607151023367293.png|商品图片地址
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└store_name|  是  |int |某热水器直营专卖店|店铺名称
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└subtotal|  是  |int |  188.00                  |该商品金额
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;└is_collect|  是  |int | 0 |0：未收藏；1：已经收藏

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "cart_info": {
      "quantity": 2,
      "amount": 2860,
      "kinds": 2
    },
    "cart_detail": {
      "307": {
        "store_name": "汉诺威、首乐热水器直营专卖",
        "amount": 2860,
        "quantity": 2,
        "goods": [
          {
            "rec_id": "2038",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "61",
            "goods_name": "HANNOVER/汉诺威GD8小厨宝 即热式厨房热水宝上出水电热水器（红/蓝/黑色）",
            "spec_id": "106",
            "specification": "",
            "price": "880.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_16/small_201607151023367293.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 880
            "is_collect": "0",
          },
          {
            "rec_id": "2039",
            "user_id": "6609",
            "session_id": "dab06fb8165c405b09a4110b3962231f",
            "store_id": "307",
            "goods_id": "60",
            "goods_name": "HANNOVER/汉诺威MF1即热式电热水器 家用速热超薄洗澡机热水器（白/银/金色）",
            "spec_id": "105",
            "specification": "",
            "price": "1980.00",
            "quantity": "1",
            "goods_image": "data/files/store_307/goods_84/small_201607151014443290.png",
            "store_name": "汉诺威、首乐热水器直营专卖",
            "subtotal": 1980
          }
        ],
        "kinds": 2
      }
    }
  }
}
</pre>



## <a name="&act=get_is_collect"/>判断商品是否已经收藏
地址：&act=get_is_collect
### 接口输入
提交方式：POST

参数

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id|  Y  |int |1                           |商品ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  string | 1 | 1:已经收藏；0：没有收藏


### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": "0"
}
</pre>


