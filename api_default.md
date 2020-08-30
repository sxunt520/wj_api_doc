文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

## 相关接口

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=default


## <a name="list"/>接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[登录](#login)  | N |  api |  mobile-app|&act=login            | POST    | YES     |
[发送验证码](#send_code)  | N |  api |  mobile-app|&act=sendcode            | POST    | YES     |
[检测版本号](#check_version)  | N |  api |  mobile-app|&act=check_version            | POST    | YES     |

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


## <a name="login"/>登录
地址：&act=login
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
user_name |  Y  |string |                           |登录名或手机号
password  |  Y  |string |                           |登录密码（第三方登陆可以不要）
captcha   |  N  |string |                           |图形验证码
openid    |  N  |string |                           |第三方ID
mobile    |  N  |string |                           |手机号
type      |  N  |string |                           |默认为1，1微信，2QQ

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
is_set_pay_password|  是  |int   |                     |是否设置了支付密码？1是，0否


## <a name="send_code"/>发送验证码
地址：&act=sendcode
### 接口输入
提交方式：POST
### 描述

参数名     |必填  |类型   |参数                        |说明
----------|-----|-------|---------------------------|----------------
from |  Y  |string |                           |发送验证码的来源。bind绑定,register注册，find_password找回密码，phone_verify修改手机号时验证老手机号，phone_modify修改手机号时验证新手机号
captcha   |  Y  |string |                           |图形验证码
phone_mob  |  Y  |string |                           |手机号码
user_id  |  N  |int |                           |用户id

### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构
字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------



## <a name="check_version"/>检测版本号
地址：&act=check_version
### 接口输入
提交方式：GET
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
version_num|  是  |string |                    |版本号
url        |  是  |string |                    |下载地址
