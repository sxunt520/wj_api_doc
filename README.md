文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=

## 约定
接口报文默认外层始终有且至少有code和msg字段, 分别为状态码和状态消息.
1.接口访问正常情况, code始终返回0; 错误的时候返回非0, 视服务端情况为准;
2.msg字段返回接口访问情况信息, 如果出错, 服务端会返回错误情况, 供客户端酌情使用;
3.如果服务端状态正常,并且需要返回数据, 将数据报文放入data字段, 不需要返回时或访问失败, 服务端不保持该字段;
4.鉴权 Y：YES，需要已header方式传递token；N：NO不需要传递token；M：Maybe，可能需要传递token；
5.以下涉及到图片等多媒体资源，其返回地址都为绝对地址。


### 全局错误码
> errcode| errmsg                         | 说明
> ------ |--------------------------------|----------------
> 0      | success                        | 请求成功
> 101    | not login                      | 您未登录
> 102    | wrong password                 | 密码错误
> 103    | not exist                      | 该用户不存在
> 104    | wrong combine                  | 用户名密码不匹配
> 105    | oauth failed                   | 连接登录失败
> 106    | already exist                  | 用户名已被注册过
> 201    | function not exist             | 请求的方法不存在
> 202    | request field missing          | 缺少请求字段
> 203    | wrong field format             | 请求字段格式错误
> 204    | request not match              | 非法请求（不匹配）
> 205    | request time out               | 请求超时
> 206    | request hack ip                | 请求被禁止
> 207    | request wrong token            | 您操作速度过快，请稍后重新尝试
> 208    | wrong not found                | 暂无数据
> 209    | works times beyond limit       | 超过今日限制数量
> 210    | works illegal words            | 包含违禁词汇
> 211    | low score                      | 您的积分不足
> 212    | captcha validation error       | 验证码不正确
> 213    | operation failed               | 操作失败


### 接口返回值示例
示例1, 接口访问成功, 服务端不带数据:
<pre>
{
    "code":0,
    "msg":"success"
}
</pre>

示例2, 接口访问失败:
<pre>
{
    "code":50401,
    "msg":"unauthorized"
}
</pre>

示例3, 服务端返回单条数据:
<pre>
{
    "code":0,
    "msg":"success",
    "data":{
        "id":1,
        "name":"name"
    }
}
</pre>

示例4, 服务端返回多组数据:
<pre>
{
    "code":0,
    "msg":"success",
    "data":[{
        "id":1,
        "name":"name"
    },{
        "id":2,
        "name":"name2"
    }]
}
</pre>

示例5, 服务端返回多组字典数据:
<pre>
{
    "code":0,
    "msg":"success",
    "data":{
        "user":{
            "id":1,
            "name":"name"
        },
        "privilege":{
            "id":2,
            "name":"name2"
        }
    }
}
</pre>

### 全局Header参数
Header参数名 |示例                                 |说明
------------|------------------------------------|---------------------------
Accept      |application/json                    |输入参数格式，缺省为json

