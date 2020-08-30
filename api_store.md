文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 店铺相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=store


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[店铺列表](#store_list-01)  | N |  api |  mobile-app|&act=index                     | GET    | YES     |店铺列表
[根据店铺ID获取列表](#store_list-02)|N|api|  mobile-app|&act=get_store_list           | GET    | YES     |根据分类ID获取店铺列表
[提交店铺评论](#store_list-03)| Y |  api |  mobile-app|&act=do_store_comment         | GET    | YES     |提交店铺评论
[店铺评论列表](#store_list-04)|N |  api |  mobile-app|&act=store_comment_list        | GET    | YES     |店铺评论列表
[店铺详情](#store_list-05)  | N |  api |  mobile-app|&act=store_detail              | GET    | YES     |店铺详情
[城市所有列表](#store_list-06)| N |  api |  mobile-app|&act=store_city               | GET    | YES     |城市所有列表
[城市级列表](#store_list-07) | N  |  api |  mobile-app|&act=get_city_list           | GET    | YES     |市级所有列表
[获取首页推荐店铺](#store_list-08) | N  |  api |  mobile-app|&act=get_comm_store      | GET    | YES     |获取首页推荐店铺(不带经纬度)
[店铺搜索列表](#store_list-09)| N  |  api |  mobile-app|&act=searche_store           | GET    | YES     |店铺搜索列表
[获取店铺认证图片](#store_list-10)| N  |  api |  mobile-app|&act=get_certification_img| GET    | YES     |获取店铺认证图片
[根据城市名获取ID](#store_list-11)| N  |  api |  mobile-app|&act=get_city_id          | GET    | YES     |根据城市名获取城市ID


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


## <a name="store_list-01"/>店铺列表
地址：&act=index
### 接口输入
提交方式：GET
### 描述
店铺列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)
lng       |  Y  |string |                           |经度
lat       |  Y  |string |                           |纬度
city_id   |  Y  |string |                           |城市ID(经续度和city_id必须有一个)
recommend |  N  |string |                           |获取推荐店铺

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
praise_rate|  是  |string |                    |店铺好评率
store_name |  是  |string |                    |店铺名称
sgrade     |  是  |string |                    |店铺等级
store_logo |  是  |string |                    |店铺logo
lat        |  是  |string |                    |纬度
lng        |  是  |string |                    |经度
store_id   |  是  |string |                    |店铺ID
distance   |  是  |string |                    |距离
recommended|  是  |string |                    |是否推荐
physical_store|  是  |string |                 |实体店 1为实体店
sincerity  |  是  |string |                    |1为诚信认证
hygiene_license|  是  |string |                |1为卫生许可证认证

## <a name="store_list-02"/>根据店铺ID获取列表
地址：&act=get_store_list
### 接口输入
提交方式：GET
### 描述
根据店铺ID获取列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)
lng       |  Y  |string |                           |经度
lat       |  Y  |string |                           |纬度
cate_id   |  Y  |string |                           |分类ID
city_id   |  Y  |string |                           |城市ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
praise_rate|  是  |string |                    |店铺好评率
store_name |  是  |string |                    |店铺名称
sgrade     |  是  |string |                    |店铺等级
store_logo |  是  |string |                    |店铺logo
lat        |  是  |string |                    |纬度
lng        |  是  |string |                    |经度
store_id   |  是  |string |                    |店铺ID
distance   |  是  |string |                    |距离
recommended|  是  |string |                    |是否推荐
physical_store|  是  |string |                 |实体店 1为实体店
sincerity  |  是  |string |                    |1为诚信认证
hygiene_license|  是  |string |                |1为卫生许可证认证


## <a name="store_list-03"/>提交店铺评论
地址：&act=do_store_comment
### 接口输入
提交方式：POST
### 描述
提交店铺评论

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
store_id   |  Y  |string |                           |店铺ID
credit_value| Y  |string |                           |店铺评分

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
N


## <a name="store_list-04"/>店铺评论列表
地址：&act=store_comment_list
### 接口输入
提交方式：GET
### 描述
店铺评论列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)
store_id  |  Y  |string |                           |店铺ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
content    |  是  |string |                    |评论内容
user_name  |  是  |string |                    |用户名
portrait   |  是  |string |                    |用户头像
evaluation |  是  |string |                    |等级
comment_time| 是  |string |                    |评论时间


## <a name="store_list-05"/>店铺详情
地址：&act=store_detail
### 接口输入
提交方式：GET
### 描述
店铺评论列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
store_id  |  Y  |string |                           |店铺ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
praise_rate|  是  |string |                    |店铺好评率
image_1    |  是  |string |                    |店铺图片1
image_2    |  是  |string |                    |店铺图片2
image_3    |  是  |string |                    |店铺图片3
store_logo |  是  |string |                    |店铺logo
store_name |  是  |string |                    |店铺名
sgrade     |  是  |string |                    |店铺等级
tel        |  是  |string |                    |电话
address    |  是  |string |                    |地址
description|  是  |string |                    |描述
collect_num|  是  |string |                    |店铺关注总数
recommended|  是  |string |                    |是否推荐
physical_store|  是  |string |                 |实体店 1为实体店
sincerity  |  是  |string |                    |1为诚信认证
hygiene_license|  是  |string |                |1为卫生许可证认证

## <a name="store_list-06"/>城市所有列表
地址：&act=store_city
### 接口输入
提交方式：GET
### 描述
城市所有列表

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
region_id  |  是  |string |                    |城市ID
region_name|  是  |string |                    |城市名
parent_id  |  是  |string |                    |城市父ID
sort_order |  是  |string |                    |排序ID
en_name    |  是  |string |                    |城市拼音


## <a name="store_list-07"/>城市级列表
地址：&act=get_city_list
### 接口输入
提交方式：GET
### 描述
市级所有列表

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
region_id  |  是  |string |                    |城市ID
region_name|  是  |string |                    |城市名
parent_id  |  是  |string |                    |城市父ID
en_name    |  是  |string |                    |城市拼音


## <a name="store_list-08"/>获取首页推荐店铺
地址：&act=get_comm_store
### 接口输入
提交方式：GET
### 描述
获取首页推荐店铺(不带经纬度)

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
limit     |  N  |string |                           |获取第N条

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
store_name |  是  |string |                    |店铺名
sgrade     |  是  |string |                    |等级
store_logo |  是  |string |                    |店铺logo
store_id   |  是  |string |                    |店铺ID


## <a name="store_list-09"/>店铺搜索列表
地址：&act=searche_store
### 接口输入
提交方式：GET
### 描述
店铺搜索列表

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
page      |  N  |string |                           |获取第N页(默认为1)
lng       |  N  |string |                           |经度
lat       |  N  |string |                           |纬度
key_words |  Y  |string |                           |店铺关健字

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
store_name |  是  |string |                    |店铺名称
sgrade     |  是  |string |                    |店铺等级
store_logo |  是  |string |                    |店铺logo
store_id   |  是  |string |                    |店铺ID
lat        |  是  |string |                    |纬度
lng        |  是  |string |                    |经度
distance   |  是  |string |                    |距离


## <a name="store_list-10"/>获取店铺认证图片
地址：&act=get_certification_img
### 接口输入
提交方式：GET
### 描述
获取店铺认证图片

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
store_id  |  Y  |string |                           |店铺ID

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
uploaded_image |  是  |string |                |图片路径
name       |  是  |string |                    |图片名称


## <a name="store_list-11"/>根据城市名获取ID
地址：&act=get_city_id
### 接口输入
提交方式：GET
### 描述
根据城市名获取城市ID

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
city_name |  Y  |string |                           |城市名称


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
region_id  |  是  |string |                    |城市ID
region_name|  是  |string |                    |城市名
parent_id  |  是  |string |                    |城市父ID
