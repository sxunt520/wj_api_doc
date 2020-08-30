文档版本: *v1.0*
接口协议: *http*
报文格式: *json*
报文编码: *utf-8*

##访问接口URL
http://api.wujieshenghuo.com/index.php?app=goods

## 接口文档

## <a name="list"/>订单接口列表
接口名                     |鉴权|  类别  | 适用端     |地址                            |请求类型 | 完成情况  |  描述
--------------------------|---|-------|-----------|-------------------------------|--------|---------|-------------------
[获取商品详情](&act=get_goods_detail)| N |  api |  mobile-app|&act=get_goods_detail    | POST    | YES |获取商品详情
[获取商品规格](&act=get_goods_spec) | N |api|mobile-app|&act=get_goods_spec| POST| YES |获取商品规格
[获取商品描述](&act=get_goods_description) | N |api|mobile-app|&act=get_goods_description| POST| YES |获取商品描述（HTML格式）
[获取商品评价](&act=get_goods_comments)    | N |  api |  mobile-app|&act=get_goods_comments| POST |YES |获取商品评价
[获取商品销售记录](&act=get_sales_record)    | N |  api |  mobile-app|&act=get_goods_comments| POST |YES |获取商品销售记录
[获取咨询记录](&act=get_qa_list)    | N |  api |  mobile-app|&act=get_qa_list| POST |YES |获取咨询记录
[提交咨询](&act=submit_aq)    | N |  api |  mobile-app|&act=submit_aq| POST |YES |提交咨询
[获取商品售后服务](&act=get_sales_service)    | N |  api |  mobile-app|&act=get_sales_service| POST |YES |获取商品售后服务



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



## <a name="&act=get_goods_detail"/>获取商品详情
地址：&act=get_goods_detail
### 接口输入
提交方式：POST
### 描述 

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int |569|商品详情


### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回数据
msg        |  是  |  string | 见示例 | 返回数据
data       |  是  |  list   | 见详参 | 返回数据

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
goods |  是  |list |                    |商品详情
&ensp;&ensp;└ store_id  |  是  |int |2150|店铺ID
&ensp;&ensp;└ type|  是  |string |material|商品类型
&ensp;&ensp;└ goods_name|  是  |string |保湿紧致洁颜乳|商品名称
&ensp;&ensp;└ description|  是  |string |好，很好，非常好|商品描述
&ensp;&ensp;└ cate_id|  是  |string |1249|商品所属分类ID
&ensp;&ensp;└ cate_name|  是  |string |日化用品|商品所属分类名称
&ensp;&ensp;└ brand|  是  |string |美肤宝|品牌
&ensp;&ensp;└ spec_qty|  是  |int |2|规格数
&ensp;&ensp;└ spec_name_1|  是  |string |尺寸|规格
&ensp;&ensp;└ spec_name_2|  是  |string |颜色|颜色
&ensp;&ensp;└ if_show|  是  |string |1|商品是否展示
&ensp;&ensp;└ closed|  是  |string |1|商品是否下架
&ensp;&ensp;└ close_reason|  是  |string |无|下架理由
&ensp;&ensp;└ add_time|  是  |string |1471470665|商品上架时间
&ensp;&ensp;└ last_update|  是  |string |1471470665|商品最后更新时间
&ensp;&ensp;└ default_spec|  是  |string |795|默认规格ID
&ensp;&ensp;└ default_image|  是  |string |data/files/store_2150/goods_179/3972.png|默认展示图片
&ensp;&ensp;└ recommended|  是  |string |1|是否推荐商品
&ensp;&ensp;└ cate_id_1|  是  |string |1210|一级分类ID
&ensp;&ensp;└ cate_id_2|  是  |string |1218|二级分类ID
&ensp;&ensp;└ cate_id_3|  是  |string |0|三级分类ID
&ensp;&ensp;└ cate_id_4|  是  |string |0|四级分类ID
&ensp;&ensp;└ price|  是  |string |89|价格
&ensp;&ensp;└ tags|  是  |array | ["深层清洁","紧致抗皱", "养颜润肤"]|标签
&ensp;&ensp;└ state|  是  |string |1|商品状态
&ensp;&ensp;└ _specs|  是  |list | |商品规格列表
&ensp;&ensp;└ _images|  是  |list | |商品图片列表
&ensp;&ensp;└_scates|  是  |list | |商品销售信息
&ensp;&ensp;└is_collect|  是  |list | |是否收藏该商品（0：未收藏；1：收藏）
store_data|  是  |list |                    |店铺详情
sales     |  是  |string |                    |商品销售总数

      
 
 
### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "id": 569,
    "goods": {
      "goods_id": "569",
      "store_id": "2150",
      "type": "material",
      "goods_name": "美肤宝五珍弹力保湿紧致洁颜乳100ml",
      "description": "<p> 
      "cate_id": "1249",
      "cate_name": "日化用品",
      "brand": "美肤宝",
      "spec_qty": "0",
      "spec_name_1": "",
      "spec_name_2": "",
      "if_show": "1",
      "closed": "0",
      "close_reason": null,
      "add_time": "1471470665",
      "last_update": "1471470665",
      "default_spec": "795",
      "default_image": "data/files/store_2150/goods_179/small_201608181342593972.png",
      "recommended": "1",
      "cate_id_1": "1210",
      "cate_id_2": "1249",
      "cate_id_3": "0",
      "cate_id_4": "0",
      "price": "97.00",
      "is_collect": "0"
      "tags": [
        "深层清洁",
        "紧致抗皱",
        "养颜润肤"
      ],
      "give_integration_rate": "0.0000",
      "max_exchange": "0",
      "state": "1",
      "_specs": [
        {
          "spec_id": "795",
          "goods_id": "569",
          "spec_1": "",
          "spec_2": "",
          "color_rgb": "",
          "price": "97.00",
          "stock": "10",
          "sku": ""
        }
      ],
      "_images": [
        {
          "image_id": "1682",
          "goods_id": "569",
          "image_url": "data/files/store_2150/goods_179/201608181342593972.png",
          "thumbnail": "data/files/store_2150/goods_179/small_201608181342593972.png",
          "sort_order": "1",
          "file_id": "2742"
        },
        {
          "image_id": "1683",
          "goods_id": "569",
          "image_url": "data/files/store_2150/goods_180/201608181343003827.png",
          "thumbnail": "data/files/store_2150/goods_180/small_201608181343003827.png",
          "sort_order": "255",
          "file_id": "2743"
        }
      ],
      "_scates": [
        {
          "cate_id": "1291",
          "goods_id": "569"
        }
      ],
      "views": "89",
      "collects": "0",
      "carts": "6",
      "orders": "63",
      "sales": "23",
      "sales": "0",
      "comments": "0",
      "default_logist": {
        "start_fees": "6.00",
        "name": "顺丰"
      }
    },
    "store_data": {
      "store_id": "2150",
      "store_name": "铭成美业",
      "owner_name": "谢祥",
      "owner_card": "510131197611076410",
      "region_id": "358",
      "region_name": "中国\t四川省\t成都",
      "address": "蒲江县鹤山镇成祥街26号",
      "zipcode": "611630",
      "tel": "13908057307",
      "sgrade": "认证店铺",
      "apply_remark": "",
      "credit_value": "16",
      "praise_rate": "85.00",
      "domain": "",
      "state": "1",
      "close_reason": "",
      "add_time": "1470679249",
      "end_time": "0",
      "certification": null,
      "sort_order": "65535",
      "recommended": "0",
      "theme": "default|style4",
      "wap_theme": "",
      "store_banner": "data/files/store_2150/other/store_banner.jpg",
      "store_logo": "data/files/store_2150/other/store_logo.jpg",
      "description": "",
      "image_1": "data/files/mall/application/store_2150_1.jpg",
      "image_2": "data/files/mall/application/store_2150_2.jpg",
      "image_3": "",
      "im_qq": "",
      "im_ww": "",
      "im_msn": "",
      "enable_groupbuy": "0",
      "enable_radar": "1",
      "latlng": "",
      "rewardpool_rate": "0.0000",
      "lat": "0",
      "lng": "0",
      "geohash": "0",
      "user_name": "苟小艳",
      "email": "",
      "credit_image": "http://localhost//themes/store/default/styles/style4/images/heart_4.gif",
      "store_owner": {
        "user_id": "2150",
        "user_name": "苟小艳",
        "email": "",
        "password": "c44df035aa1ee474b3037542024079d3",
        "real_name": "苟小艳",
        "gender": "0",
        "birthday": null,
        "phone_tel": null,
        "phone_mob": "13908057307",
        "im_qq": null,
        "im_msn": null,
        "im_skype": null,
        "im_yahoo": null,
        "im_aliww": null,
        "reg_time": "1469835702",
        "last_login": "1475799465",
        "last_ip": "118.115.224.41",
        "logins": "49",
        "ugrade": "1",
        "super": "0",
        "super_time": "0",
        "portrait": null,
        "outer_id": "0",
        "activation": null,
        "feed_config": "",
        "locked": "0",
        "promoter_indentity": "146986486023",
        "promoter_id": "2149",
        "co_id": null,
        "region_id": null,
        "region_name": null,
        "agent_region_id": null,
        "agent_region_name": null,
        "agent_cate_id": null,
        "card_id": "510131197907241024",
        "card_img1": "data/files/mall/member/2150/201608091207124319.jpg",
        "card_img2": "data/files/mall/member/2150/201608091207217137.jpg",
        "card_img3": "data/files/mall/member/2150/201608091207313745.jpg",
        "verify": "2",
        "reject_reason": null
      },
      "store_navs": [],
      "goods_count": "62",
      "store_gcates": [
        {
          "cate_id": "1287",
          "cate_name": "美容系列",
          "children": [
            {
              "cate_id": "1291",
              "cate_name": "美肤宝",
              "children": []
            },
            {
              "cate_id": "1292",
              "cate_name": "凯皙漫",
              "children": []
            },
            {
              "cate_id": "1293",
              "cate_name": "九美子",
              "children": []
            },
            {
              "cate_id": "1294",
              "cate_name": "朵蔻面膜",
              "children": []
            },
            {
              "cate_id": "1295",
              "cate_name": "基因壹号",
              "children": []
            },
            {
              "cate_id": "1296",
              "cate_name": "百悦术（美白淡斑）",
              "children": []
            },
            {
              "cate_id": "1312",
              "cate_name": "莱仕",
              "children": []
            }
          ]
        },
        {
          "cate_id": "1288",
          "cate_name": "美发系列",
          "children": []
        }
      ],
      "functions": {
        "editor_multimedia": "editor_multimedia",
        "coupon": "coupon",
        "enable_radar": "enable_radar"
      }
    }
  }
}
</pre>

## <a name="&act=get_goods_spec"/>获取商品规格
地址：&act=get_goods_spec
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID
 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
spec_list    |  是  |list |    |规格种类
&ensp;&ensp;└spec_1_name  |  是  |string | 颜色 |规格1名称
&ensp;&ensp;└spec_1_arr    |  是  |list | | 规格1内容列表
&ensp;&ensp;└spec_2_name  |  是  |string | 颜色 |规格2名称
&ensp;&ensp;└spec_2_arr    |  是  |list | | 规格2内容列表
spec_info |  是  |list |    |规格内容组合
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
     "spec_list": [
      {
        "spec_name": "颜色",
        "spec_arr": [
          "蓝色",
          "金色",
          "白色",
          "黑色"
        ]
      },
      {
        "spec_name": "网络、ROM容量",
        "spec_arr": [
          "全网、16GB",
          "双网、32GB"
        ]
      }
    ],
    "spec_info": [
      {
        "spec_id": "826",
        "goods_id": "596",
        "spec_1": "蓝色",
        "spec_2": "全网、16GB",
        "color_rgb": "",
        "price": "888.00",
        "stock": "2",
        "sku": ""
      },
      {
        "spec_id": "827",
        "goods_id": "596",
        "spec_1": "金色",
        "spec_2": "全网、16GB",
        "color_rgb": "",
        "price": "888.00",
        "stock": "2",
        "sku": ""
      },
      {
        "spec_id": "828",
        "goods_id": "596",
        "spec_1": "白色",
        "spec_2": "全网、16GB",
        "color_rgb": "",
        "price": "888.00",
        "stock": "2",
        "sku": ""
      },
      {
        "spec_id": "829",
        "goods_id": "596",
        "spec_1": "白色",
        "spec_2": "双网、32GB",
        "color_rgb": "",
        "price": "672.00",
        "stock": "0",
        "sku": ""
      },
      {
        "spec_id": "1102",
        "goods_id": "596",
        "spec_1": "金色",
        "spec_2": "双网、32GB",
        "color_rgb": "",
        "price": "672.00",
        "stock": "0",
        "sku": ""
      },
      {
        "spec_id": "1588",
        "goods_id": "596",
        "spec_1": "黑色",
        "spec_2": "双网、32GB",
        "color_rgb": "",
        "price": "672.00",
        "stock": "0",
        "sku": ""
      }
    ]
  }
}
</pre>


## <a name="&act=get_goods_description"/>获取商品描述
地址：&act=get_goods_description
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID
 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回商品描述(只有这一个字段，为html格式)


## <a name="&act=get_goods_comments"/>获取商品评价
地址：&act=get_goods_comments
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID
page |  Y  |int | 2  |页码（第几页）
 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
comments    |  是  |list |    |评价内容列表
&ensp;&ensp;└buyer_id    |  是  |int | 2312 |买家ID
&ensp;&ensp;└buyer_name    |  是  |string |四**********旅|买家姓名
&ensp;&ensp;└anonymous    |  是  |int |      0  |1:匿名；0：不匿名
&ensp;&ensp;└evaluation_time    |  是  |string |   1469994469|评价时间
&ensp;&ensp;└comment    |  是  |string | 很好喝 | 评价内容
&ensp;&ensp;└evaluation    |  是  |int | 3 | 评价得分
page_info|  是  |list |    |页码信息
&ensp;&ensp;└limit   |  是  |string | 0,10 |
&ensp;&ensp;└curr_page   |  是  |int | 3 | 当前页码
&ensp;&ensp;└pageper   |  是  |int | pageper | 每页数量
&ensp;&ensp;└item_count   |  是  |int | 3 | 评价总数量
&ensp;&ensp;└page_count   |  是  |int | 3 | 总页数
&ensp;&ensp;└page_links   |  是  |list |  | 每个页面的链接地址
&ensp;&ensp;└first_link|  是  |string |第一个页面链接地址
&ensp;&ensp;└first_suspen|  是  |string | | 
&ensp;&ensp;└last_link|  是  |string | |最后一个页码链接地址
&ensp;&ensp;└last_suspen|  是  |string | | 
&ensp;&ensp;└prev_link|  是  |string | |前一个页码链接地址
&ensp;&ensp;└next_link|  是  |string | |后一个页码链接地址
more_comments |  是  |string | false   |是否还有更多页码
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "comments": [
      {
        "buyer_id": "325",
        "buyer_name": "1*********8",
        "anonymous": "0",
        "evaluation_time": "1477859412",
        "comment": "",
        "evaluation": "3",
        "rec_id": "392"
        "evalution_img":[sdf,sdf]
      },
      {
        "buyer_id": "2312",
        "buyer_name": "四**********旅",
        "anonymous": "0",
        "evaluation_time": "1473812630",
        "comment": "口活好",
        "evaluation": "3",
        "rec_id": "285"
      },
      {
        "buyer_id": "109",
        "buyer_name": "n******f",
        "anonymous": "0",
        "evaluation_time": "1473298957",
        "comment": "帅气，讲课好棒棒(⊙o⊙)",
        "evaluation": "3",
        "rec_id": "288"
      },
      {
        "buyer_id": "2535",
        "buyer_name": "l*********************5",
        "anonymous": "0",
        "evaluation_time": "1473282408",
        "comment": "可以",
        "evaluation": "3",
        "rec_id": "286"
      },
      {
        "buyer_id": "89",
        "buyer_name": "z***********5",
        "anonymous": "0",
        "evaluation_time": "1473281838",
        "comment": "熊熊老师  人长的帅   很多女性朋友都评价人帅 活好，我要联系熊熊多多交流，提升自己",
        "evaluation": "3",
        "rec_id": "283"
      },
      {
        "buyer_id": "86",
        "buyer_name": "s*****y",
        "anonymous": "0",
        "evaluation_time": "1473281808",
        "comment": "太快了，不错，物超所值，好评!",
        "evaluation": "3",
        "rec_id": "284"
      },
      {
        "buyer_id": "90",
        "buyer_name": "燕*******。",
        "anonymous": "0",
        "evaluation_time": "1473281408",
        "comment": "人帅，货美，活好！！！！卖家真的很不错！！好评。",
        "evaluation": "3",
        "rec_id": "282"
      },
      {
        "buyer_id": "99",
        "buyer_name": "夕**********下",
        "anonymous": "0",
        "evaluation_time": "1473280943",
        "comment": "店长真不错，人帅货好，下次再光顾",
        "evaluation": "3",
        "rec_id": "281"
      },
      {
        "buyer_id": "88",
        "buyer_name": "g*****g",
        "anonymous": "0",
        "evaluation_time": "1473280889",
        "comment": "长得好帅！",
        "evaluation": "3",
        "rec_id": "280"
      },
      {
        "buyer_id": "626",
        "buyer_name": "魔*******门",
        "anonymous": "0",
        "evaluation_time": "1473280556",
        "comment": "老板人好帅气上档次！好评！赞！",
        "evaluation": "3",
        "rec_id": "273"
      }
    ],
    "page_info": {
      "limit": "0,10",
      "curr_page": 1,
      "pageper": 10,
      "item_count": "14",
      "page_count": 2,
      "page_links": {
        "1": "index.php?app=goods&amp;act=get_goods_comments&amp;page=1",
        "2": "index.php?app=goods&amp;act=get_goods_comments&amp;page=2"
      },
      "first_link": "",
      "first_suspen": "",
      "last_link": "",
      "last_suspen": "",
      "prev_link": "",
      "next_link": "index.php?app=goods&amp;act=get_goods_comments&amp;page=2"
    },
    "more_comments": true
  }
}
</pre>

## <a name="&act=get_sales_record"/>获取商品销售记录
地址：&act=get_sales_record
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID
 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
comments    |  是  |list |    |评价内容列表
&ensp;&ensp;└buyer_id    |  是  |int | 2312 |买家ID
&ensp;&ensp;└buyer_name    |  是  |string |四**********旅|买家姓名
&ensp;&ensp;└anonymous    |  是  |int |      0               | 
&ensp;&ensp;└goods_id    |  是  |string |   233|商品ID
&ensp;&ensp;└specification    |  是  |string | "颜色:白 尺码:瓶" | 规格描述
&ensp;&ensp;└price    |  是  |float | 79.00 | 价格
&ensp;&ensp;└quantity    |  是  |string |  3|购买数量
&ensp;&ensp;└evaluationn    |  是  |string | 3 | 评价得分
page_info|  是  |list |    |页码信息
&ensp;&ensp;└limit   |  是  |string | 0,10 |
&ensp;&ensp;└curr_page   |  是  |int | 3 | 当前页码
&ensp;&ensp;└pageper   |  是  |int | pageper | 每页数量
&ensp;&ensp;└item_count   |  是  |int | 3 | 评价总数量
&ensp;&ensp;└page_count   |  是  |int | 3 | 总页数
&ensp;&ensp;└page_links   |  是  |list |  | 每个页面的链接地址
&ensp;&ensp;└first_link|  是  |string |第一个页面链接地址
&ensp;&ensp;└first_suspen|  是  |string | | 
&ensp;&ensp;└last_link|  是  |string | |最后一个页码链接地址
&ensp;&ensp;└last_suspen|  是  |string | | 
&ensp;&ensp;└prev_link|  是  |string | |前一个页码链接地址
&ensp;&ensp;└next_link|  是  |string | |后一个页码链接地址
more_sales |  是  |string | false   |是否还有更多页码
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "sales_list":[
       {
        "buyer_id": "2312",
        "buyer_name": "四**********旅",
        "add_time": "1469993944",
        "anonymous": "0",
        "goods_id": "233",
        "specification": "颜色:白 尺码:瓶",
        "price": "79.00",
        "quantity": "1",
        "evaluation": "3",
        "rec_id": "142"
      }
    ],
    "page_info": {
      "limit": "0,10",
      "curr_page": 1,
      "pageper": 10,
      "item_count": "1",
      "page_count": 1,
      "page_links": {
        "1": "index.php?app=goods&amp;act=get_sales_record&amp;XDEBUG_SESSION_START=14893&amp;page=1"
      },
      "first_link": "",
      "first_suspen": "",
      "last_link": "",
      "last_suspen": "",
      "prev_link": "",
      "next_link": ""
    },
    "more_sales": false
  }
}
</pre>



## <a name="&act=get_qa_list"/>获取商品咨询记录
地址：&act=get_qa_list
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID
 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
page_info|  是  |list |    |页码信息
&ensp;&ensp;└limit   |  是  |string | 0,10 |
&ensp;&ensp;└curr_page   |  是  |int | 3 | 当前页码
&ensp;&ensp;└pageper   |  是  |int | pageper | 每页数量
&ensp;&ensp;└item_count   |  是  |int | 3 | 评价总数量
&ensp;&ensp;└page_count   |  是  |int | 3 | 总页数
&ensp;&ensp;└page_links   |  是  |list |  | 每个页面的链接地址
&ensp;&ensp;└first_link|  是  |string |第一个页面链接地址
&ensp;&ensp;└first_suspen|  是  |string | | 
&ensp;&ensp;└last_link|  是  |string | |最后一个页码链接地址
&ensp;&ensp;└last_suspen|  是  |string | | 
&ensp;&ensp;└prev_link|  是  |string | |前一个页码链接地址
&ensp;&ensp;└next_link|  是  |string | |后一个页码链接地址
qa_info    |  是  |list |    |咨询内容列表
&ensp;&ensp;└user_name    |  是  |string | xiaol |买家账号
&ensp;&ensp;└question_content    |  是  |string |有沒得四驅？|咨询内容
&ensp;&ensp;└reply_content    |  是  |string |有哦 | 回复内容
&ensp;&ensp;└time_post    |  是  |string | 1475219634|提交时间
&ensp;&ensp;└time_reply |  是  |string | 1475219634 |回复时间
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": {
    "email": "",
    "page_info": {
      "limit": "0,5",
      "curr_page": 1,
      "pageper": 5,
      "item_count": "4",
      "page_count": 1,
      "page_links": {
        "1": "index.php?app=goods&amp;act=get_qa_list&amp;XDEBUG_SESSION_START=14893&amp;page=1"
      },
      "first_link": "",
      "first_suspen": "",
      "last_link": "",
      "last_suspen": "",
      "prev_link": "",
      "next_link": ""
    },
    "qa_info": {
      "56": {
        "user_name": null,
        "question_content": "有沒得四驅？",
        "reply_content": "",
        "time_post": "1475219634",
        "time_reply": "0",
        "ques_id": "56"
      },
      "59": {
        "user_name": "香兰宝贝",
        "question_content": "我刚才充的话费怎么还没有到账呀",
        "reply_content": "",
        "time_post": "1475307350",
        "time_reply": "0",
        "ques_id": "59"
      },
      "63": {
        "user_name": "高红",
        "question_content": "你好，买这车子按揭首付多少钱呢",
        "reply_content": "",
        "time_post": "1475422900",
        "time_reply": "0",
        "ques_id": "63"
      },
      "67": {
        "user_name": "13568910280",
        "question_content": "我前几天充的油费什么时候到账？",
        "reply_content": "",
        "time_post": "1475684337",
        "time_reply": "0",
        "ques_id": "67"
      }
    }
  }
}
</pre>


## <a name="&act=submit_aq"/>提交咨询
地址：&act=submit_aq
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID
content|  Y  |string | 可以便宜点不  |咨询内容
qa_type|  Y  |string | 支付方式问题|咨询分类
hide_name|  Y  |int | 1|1:匿名咨询；0：非匿名咨询
get_aq_list| N  |int | 1|1:返回咨询列表；0：只返回操作状态
 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
data|  是  |string | add_ok   |页码信息
 
 

### 接口返回值示例
<pre>
{
  "code": 0,
  "msg": "success",
  "data": "add_ok"
}
</pre>


## <a name="&act=get_sales_service"/>获取商品售后服务
地址：&act=get_sales_service
### 接口输入
提交方式：POST

参数名     |必填  |类型   |示例                       |说明
----------|-----|-------|---------------------------|----------------
goods_id     |  Y  |int | 233  |商品ID

 
### 接口输出

字段名      | 必有 |   类型   |  示例  |  说明
-----------|------|---------|-------|---------
code       |  是  |  int    | 见示例 | 返回操作状态编码
msg        |  是  |  string | 见示例 | 返回操作状态信息
data       |  是  |  list   | 见详参 | 返回购订单号列表

#### 返回data结构

字段名      |必有  |类型   |示例                  |说明
-----------|------|------|---------------------|------------
sales_service|  是  |string | test   |售后服务信息
 
 

### 接口返回值示例
{
  "code": 0,
  "msg": "success",
  "data": "sdfsdfdsfdsfds"
}
</pre>


