文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 商品列表相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=glist


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[精品推荐](#goods_list-01)  | N |  api |  mobile-app|&act=recommend_list            | GET    | YES     |精品推荐
[商品列表](#goods_list-02)  | N |  api |  mobile-app|&act=goods_list                | GET    | YES     |普通商品列表(排序)
[店铺商品列表](#goods_list-03)|N |  api |  mobile-app|&act=store_goods_list          | GET    | YES     |获取某个店铺下的商品列表
[首页活动商品](#goods_list-04)|N |  api |  mobile-app|&act=get_active_banner_goods   | GET    | YES     |首页banner活动商品列表
[根据bannerid获取活动商品列表](#goods_list-05)|N |  api |  mobile-app|&act=get_active_goods_list| GET   | YES     |根据banner id获取活动商品列表
[获取后台推荐的商品列表](#goods_list-06)|N |  api |  mobile-app|&act=get_recommend_goods_list| GET   | YES     |获取后台推荐的商品列表



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


## <a name="goods_list-01"/>精品推荐
地址：&act=recommend_list
### 接口输入
提交方式：GET
### 描述
limit 如果不传或等于0时，获取更多

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)

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
goods_name |  是  |string |                    |商品名字
default_image|是  |string |                    |商品图片
price      |  是  |string |                    |商品价格


## <a name="goods_list-02"/>商品列表
地址：&act=goods_list
### 接口输入
提交方式：GET
### 描述
普通商品列表(排序)

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
type      |  N  |string |                           |排序类型(1降序，2升序)，默认降序
page      |  N  |string |                           |获取第N页(默认为1)
fields    |  N  |string |                           |排序字段(sales：销量，add_time：上传时间，price：价格)默认为上传时间
store_id  |  N  |string |                           |店铺ID
key_words |  N  |string |                           |搜索关键词
cate_id   |  N  |string |                           |分类ID

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
goods_name |  是  |string |                    |商品名字
default_image|是  |string |                    |商品图片
price      |  是  |string |                    |商品价格
sales      |  是  |string |                    |商品销量


## <a name="goods_list-03"/>店铺商品列表
地址：&act=store_goods_list
### 接口输入
提交方式：GET
### 描述
获取某个店铺下的商品列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)
store_id  |  Y  |string |                           |店铺ID
field     |  N  |string |                           |排序字段 price:价格 sales:销售量 add_time:最新商品(默认)
type      |  N  |string |                           |排序类型是降序还是升序 0降序(默认) 1升序
cate_id   |  N  |string |                           |分类ID

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
goods_name |  是  |string |                    |商品名字
default_image|是  |string |                    |商品图片
price      |  是  |string |                    |商品价格
sales      |  是  |string |                    |商品销量


## <a name="goods_list-04"/>首页活动商品
地址：&act=get_active_banner_goods
### 接口输入
提交方式：GET
### 描述
首页banner活动商品列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
banner     |  是  |string |                    |活动banner图
url        |  是  |string |                    |活动banner跳转连接
goods_id   |  是  |string |                    |商品ID
goods_name |  是  |string |                    |商品名字
default_image|是  |string |                    |商品图片
price      |  是  |string |                    |商品价格
original_price |  是  |string |                |商品原价格


## <a name="goods_list-05"/>根据bannerid获取活动商品列表
地址：&act=get_active_goods_list
### 接口输入
提交方式：GET
### 描述
根据banner id获取活动商品列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
banner     |  是  |string |                    |活动banner图
goods_id   |  是  |string |                    |商品ID
goods_name |  是  |string |                    |商品名字
default_image|是  |string |                    |商品图片
price      |  是  |string |                    |商品价格
original_price |  是  |string |                |商品原价格


## <a name="goods_list-06"/>获取后台推荐的商品列表
地址：&act=get_recommend_goods_list
### 接口输入
提交方式：GET
### 描述
获取后台推荐的商品列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
rec_id    |  Y  |string |                           |推荐ID。17：人气好货
page      |  N  |string |                           |获取第N页(默认为1)

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
goods_name |  是  |string |                    |商品名字
default_image|是  |string |                    |商品图片
price      |  是  |string |                    |商品价格


