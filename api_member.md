文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 会员相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=member


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[注册](#register)  | N |  api |  mobile-app|&act=register         | POST    | YES     |注册
[登陆者个人信息](#info)  | N |  api |  mobile-app|&act=info         | GET/POST    | YES     |注册
[修改昵称](#edit_nick_name)  | N |  api |  mobile-app|&act=edit_nick_name         | POST    | YES     |
[修改用户名](#edit_user_name)  | N |  api |  mobile-app|&act=edit_user_name         | POST    | YES     |
[修改性别](#edit_gender)  | N |  api |  mobile-app|&act=edit_gender         | POST    | YES     |
[修改出生日期](#edit_birthday)  | N |  api |  mobile-app|&act=edit_birthday         | POST    | YES     |
[修改电子邮箱](#edit_email)  | N |  api |  mobile-app|&act=edit_email         | POST    | YES     |
[修改居住地](#edit_region)  | N |  api |  mobile-app|&act=edit_region         | POST    | YES     |
[修改推荐人](#edit_promoter)  | N |  api |  mobile-app|&act=edit_promoter         | POST    | YES     |
[修改头像](#edit_portrait)  | N |  api |  mobile-app|&act=edit_portrait         | POST    | YES     |
[验证旧手机号码](#verify_old_phone_mob)  | N |  api |  mobile-app|&act=verify_old_phone_mob         | POST    | YES     |
[验证新手机号码](#verify_new_phone_mob)  | N |  api |  mobile-app|&act=verify_new_phone_mob         | POST    | YES     |
[实名认证](#authenticate)  | N |  api |  mobile-app|&act=authenticate         | POST    | YES     |
[实名认证情况](#authentication_info)  | N |  api |  mobile-app|&act=authentication_info         | POST    | YES     |
[上传文件](#upload_file)  | N |  api |  mobile-app|&act=upload_file         | POST    | YES     |
[验证旧密码](#verify_password)  | N |  api |  mobile-app|&act=verify_password         | POST    | YES     |
[修改密码](#change_password)  | N |  api |  mobile-app|&act=change_password         | POST    | YES     |
[订单统计](#order_count)  | N |  api |  mobile-app|&act=order_count         | GET/POST    | YES     |
[升级付费会员](#upgrade)  | N |  api |  mobile-app|&act=upgrade         | GET/POST    | YES     |
[升级超级会员](#up_super)  | N |  api |  mobile-app|&act=up_super         | GET/POST    | YES     |



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


## <a name="register"/>注册
地址：&act=register
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
user_name |  Y  |string |                           |用户名
password  |  Y  |string |                           |登录密码
password_confirm   |  Y  |string |                           |确认密码
region_id   |  Y  |int |                           |地区id
region_name   |  Y  |string |                           |地区名称
phone_mob   |  Y  |string |                           |手机号码
check_code   |  Y  |string |                           |手机验证码
reference   |  Y  |string |                           |推荐人用户名或手机号码
agree   |  Y  |string |                           |是否同意注册协议，大于0表示同意
openid   |  N  |string |                           |第三方ID
type   |  N  |string |                           |登陆平台类型1微信，2QQ，默认为1

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
user_id    |  是  |int   |                     |用户ID
user_name  |  是  |string|                     |用户名
real_name  |  否  |string|                     |用户真实姓名
reg_time   |  是  |int   |                     |注册时间
last_login |  是  |int   |                     |上次登录时间
last_ip |  是  |string   |                     |上次登录ip
logins |  是  |int   |                     |登录次数
store_id |  否  |string   |                     |店铺id（如果没有则返回null）
email |  否  |string   |                     |邮箱
password |  是  |string   |                     |加密后的密码
ugrade|  是  |int   |                     |会员等级：0普通会员，1付费会员，2个代，3县代，4市代，5县代，6合作公司
is_super|  是  |int   |                     |是否超级会员：1是，0否
super_time|  是  |int   |                     |成为超级会员时间
promoter_id|  是  |int   |                     |推荐人的user_id
promoter_user_name|  否  |string   |                     |推荐人的user_name
co_id|  是  |int   |                     |所属合作公司的user_id
verify|  是  |int   |                     |实名认证状态。0未认证，1正在审核，2审核通过，3审核拒绝

## <a name="info"/>登陆者个人信息
地址：&act=info
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
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
user_id    |  是  |int   |                     |用户ID
user_name  |  是  |string|                     |用户名
real_name  |  否  |string|                     |用户真实姓名
reg_time   |  是  |int   |                     |注册时间
last_login |  是  |int   |                     |上次登录时间
last_ip |  是  |string   |                     |上次登录ip
logins |  是  |int   |                     |登录次数
store_id |  否  |string   |                     |店铺id（如果没有则返回null）
email |  否  |string   |                     |邮箱
password |  是  |string   |                     |加密后的密码
ugrade|  是  |int   |                     |会员等级：0普通会员，1付费会员，2个代，3县代，4市代，5县代，6合作公司
is_super|  是  |int   |                     |是否超级会员：1是，0否
super_time|  是  |int   |                     |成为超级会员时间
promoter_id|  是  |int   |                     |推荐人的user_id
promoter_user_name|  否  |string   |                     |推荐人的user_name
co_id|  是  |int   |                     |所属合作公司的user_id
verify|  是  |int   |                     |实名认证状态。0未认证，1正在审核，2审核通过，3审核拒绝


## <a name="edit_user_name"/>修改用户名
地址：&act=edit_user_name
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
user_name |  Y  |string |                           |用户名

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="edit_nick_name"/>修改昵称
地址：&act=edit_nick_name
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
nick_name |  Y  |string |                           |昵称

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="edit_gender"/>修改性别
地址：&act=edit_gender
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
gender |  Y  |int |                           |性别。1男，2女

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="edit_birthday"/>修改出生日期
地址：&act=edit_birthday
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
birthday |  Y  |string |                           |生日

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="edit_email"/>修改电子邮箱
地址：&act=edit_email
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
email |  Y  |string |                           |电子邮箱

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------




## <a name="edit_region"/>修改居住地
地址：&act=edit_region
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
region_id |  Y  |int |                           |地区id

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="edit_promoter"/>修改推荐人
地址：&act=edit_promoter
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
promoter_name |  Y  |string |                           |推荐人用户名或手机号

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="edit_portrait"/>修改头像
地址：&act=edit_portrait
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
portrait |  N  |string |                           |头像上传后的服务器返回的图片地址。为空表示清空头像

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="verify_old_phone_mob"/>验证旧手机号码
地址：&act=verify_old_phone_mob
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
sms_code |  Y  |string |                           |验证码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="verify_new_phone_mob"/>验证新手机号码
地址：&act=verify_new_phone_mob
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
phone |  Y  |string |                           |新手机号码
sms_code |  Y  |string |                           |验证码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="authenticate"/>实名认证
地址：&act=authenticate
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
real_name |  Y  |string |                           |姓名
card_id |  Y  |string |                           |身份证号
card_img1 |  Y  |string |                           |身份证正面图片
card_img2 |  Y  |string |                           |身份证反面图片
card_img3 |  Y  |string |                           |身份证持证件照图片

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="authentication_info"/>实名认证情况
地址：&act=authentication_info
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
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
real_name    |  是  |string   |                     |姓名
card_id |  是  |string |                           |身份证号
card_img1 |  是  |string |                           |身份证正面图片
card_img2 |  是  |string |                           |身份证反面图片
card_img3 |  是  |string |                           |身份证持证件照图片
verify |  是  |string |                           |状态。0未认证，1正在审核，2审核通过，3审核不通过
reject_reason |  否  |string |                           |拒绝原因



## <a name="upload_file"/>上传图片
地址：&act=upload_file
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
file |  Y  |file |                           |上传的图片

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  string   | 见详参 | 服务器图片地址

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="verify_password"/>验证旧密码
地址：&act=verify_password
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
old_password |  Y  |string |                           |旧密码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------

## <a name="change_password"/>修改密码
地址：&act=change_password
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
old_password |  Y  |string |                           |旧密码
new_password |  Y  |string |                           |新密码
confirm_password |  Y  |string |                           |确认新密码

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------


## <a name="order_count"/>订单统计
地址：&act=order_count
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
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
pending|  是  |int   |                     |待付款数量
accepted|  是  |int   |                     |已付款待发货数量
shipped|  是  |int   |                     |已发货数量
finished|  是  |int   |                     |待评价数量
refund|  是  |int   |                     |退款数量



## <a name="upgrade"/>升级付费会员
地址：&act=upgrade
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
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id|  是  |int   |                     |订单id
goods_name|  是  |int   |                     |商品名称
amount|  是  |float   |                     |金额



## <a name="up_super"/>升级超级会员
地址：&act=up_super
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
data       |  是  |  null   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
order_id|  是  |int   |                     |订单id
goods_name|  是  |int   |                     |商品名称
amount|  是  |float   |                     |金额