# bilibili-API

## 视频信息api

### https://api.bilibili.com/x/web-interface/view?aid={aid}cid={cid}

**参数**：

* aid: 视频的av号
* cid: 视频的弹幕库号（多p的视频则cid是1p视频的弹幕库号）可不填

**响应体**：

```json
{ 
  "code": 0,	//响应代码 
  "message": "0", 
  "ttl": 1,      
  "data": {		//返回的数据
    "aid": 65144388,	//视频av号
    "videos": 1, 	//该视频有多少p
    "tid": 27,    	//分区id
    "tname": "综合", 	 //子分区名字
    "copyright": 1, 	//版权，1为未经允许不能转载
    "pic": "", 		//视频封面
    "title": "", 	//视频标题
    "pubdate": 1566646253,	 //发布时间的时间戳
    "ctime": 1566631298, 	 //创建时间的时间戳
    "desc": "",  	//视频的描述
    "state": 0,  
    "attribute": 16768,  //分区号
    "duration": 572,     //视频的长度(秒)
    "mission_id": 11740,  
    "rights": {		//一些权限
      "bp": 0,
      "elec": 0,
      "download": 1,
      "movie": 0,
      "pay": 0,
      "hd5": 1,
      "no_reprint": 1,
      "autoplay": 1,
      "ugc_pay": 0,
      "is_cooperation": 0,
      "ugc_pay_preview": 0
    },
    "owner": {  		//up主信息
      "mid": 730732,	//up主uid
      "name": "", 		 //up主昵称
      "face": "" 		 //up主头像
    },
    "stat": {		 //视频的一些信息统计
      "aid": 65144388,  	//视频的av号
      "view": 329792,    	//播放量
      "danmaku": 1656,  	//弹幕数
      "reply": 923,     	//评论数
      "favorite": 20258,  	//收藏数
      "coin": 42323,  		//硬币数
      "share": 793,    		//分享数
      "now_rank": 0,  		//现在排名
      "his_rank": 48,  		//历史排名
      "like": 45113,  		//点赞数
      "dislike": 0     		//点踩数
    },
    "dynamic": "",   		//up主发布视频时顺带发布的动态信息
    "cid": 113060527,   	//弹幕库id
    "dimension": {
      "width": 1920,   		//视频的宽度
      "height": 1080,  		//视频的高度
      "rotate": 0
    },
    "no_cache": false,  	//缓存
    "pages": [		//当前视频p的弹幕库信息，有多p的视频则有多条信息
      {
        "cid": 113060527, 	//弹幕库id
        "page": 1,        	//第几p
        "from": "vupload",   //视频来源，上传
        "part": "Doraemon_SF_fixed_x264", //up主上传该视频时的文件名
        "duration": 572,  	//当前p视频的长度
        "vid": "",
        "weblink": "",
        "dimension": {
          "width": 1920,   	//视频的宽度
          "height": 1080,  	//视频的高度
          "rotate": 0
        }
      }
    ],
    "staff": [   	//如果该视频是合作视频则会多出‘staff’属性，这是一个列表，存放合作的所有up主信息
        {
          "mid": 391679,   		//up主uid
          "title": "UP主", 	    //合作中的描述，第一个一般是up主
          "name": "",   		//up主名称
          "face": "", 			//up主头像
          "vip": {  			//大会员信息
                "type": 2,
                "status": 1,
                "vip_pay_type": 0,
                "theme_type": 0
          },
          "official": {		//官方认证
                "role": 1,
                "title": "",
                "desc": ""
          },
          "follower": 2138376   //粉丝数
    	},
    ],
    "subtitle": {
      "allow_submit": true,
      "list": [
        
      ]
    },
    "label": {
      "type": 1
    }
  }
}
```

## 视频信息api_2

### https://api.bilibili.com/x/article/archives?ids={}

这个api中的**ids**参数可以写多个av号，**av号**可以用**逗号(,)**分割，最多可以传100个av号

如：https://api.bilibili.com/x/article/archives?ids=50000005,50000006

```json
{
    "code": 0,    	//状态码
    "message": "0",	//消息码
    "ttl": 1, 
    "data": { 	//数据
        "50000005": {	//视频av号
            "aid": 50000005,	//视频av号
            "videos": 1,		//视频p数
            "tid": 31,			//子分区id
            "tname": "翻唱",		//子分区
            "copyright": 1,		//版权，1为未经允许不能转载
            "pic": "",			//视频图片封面
            "title": "",		//视频名称
            "pubdate": 1555855819,	//发布日期，时间戳
            "ctime": 1555855819,	//创建日，时间戳
            "desc": "",			//视频描述
            "state": 0,			//未知
            "attribute": 16579,	//属性id
            "duration": 808,	//视频长度(秒)
            "rights": {		//权限，应该是用来控制H5播放器的一些信息
                "bp": 0,
                "elec": 0,
                "download": 0,
                "movie": 0,
                "pay": 0,
                "hd5": 0,
                "no_reprint": 1,
                "autoplay": 1,
                "ugc_pay": 0,
                "is_cooperation": 0,
                "ugc_pay_preview": 0
            },
            "owner": {		//up主信息
                "mid": 389634516,	//up主uid
                "name": "",			//up主名称
                "face": "" 			//up主头像
            },
            "stat": {		//视频统计信息
                "aid": 50000005,	 //视频av号
                "view": 686,    	 //播放量
                "danmaku": 0,   	 //弹幕数
                "reply": 4,     	 //评论
                "favorite": 1,  	 //收藏
                "coin": 0,      	 //硬币
                "share": 0, 		 //分享
                "now_rank": 0,   	 //现在排名
                "his_rank": 0,   	 //历史排名
                "like": 5,       	 //点赞
                "dislike": 0     	 //点踩
            },
            "dynamic": "",  //投稿视频时发布的动态信息
            "cid": 87525032,   		//弹幕库id
            "dimension": {  		//视频分辨率信息
                "width": 1280,
                "height": 720,
                "rotate": 0
            }
        }
```





## 视频信息统计api

### https://api.bilibili.com/x/web-interface/archive/stat?aid={}

### 参数：

- aid：视频av号

```json
{
    "code": 0,
    "message": "0",
    "ttl": 1,
    "data": {
        "aid": 66303882,    //视频av号
        "view": 346052,     //播放量
        "danmaku": 3320,    //弹幕数
        "reply": 1840,      //评论
        "favorite": 19075,  //收藏
        "coin": 36834,      //硬币
        "share": 13487,     //分享
        "like": 32860,      //点赞
        "now_rank": 0,      //现在排名
        "his_rank": 98,     //历史排名
        "no_reprint": 1,    //？？？
        "copyright": 1,     //版权
        "argue_msg": ""     //？？？
    }
}
```



## 弹幕库api

### https://api.bilibili.com/x/v1/dm/list.so?oid={oid}

### 参数：

- oid：弹幕库id

```xml
<?xml version="1.0" encoding="UTF-8"?>
<i>
    <chatserver>chat.bilibili.com</chatserver>
    <chatid>114779843</chatid>  <!--弹幕池id-->
    <mission>0</mission>
    <maxlimit>500</maxlimit>   <!--最大弹幕限制-->
    <state>0</state>
    <real_name>0</real_name>
    <source>k-v</source>
    <!--d标签的p属性的第一个值是视频的第几秒发送的，标签文本是弹幕，有多少个d标签就有多少条弹幕-->
    <d p="96.67500,1,25,16777215,1567260763,0,20afe05e,21033694440456194">2333</d>
</i>
```





## 视频排行榜api

### https://api.bilibili.com/x/web-interface/ranking?rid={rid}&day={day}&type={type}&arc_type={type}

### 参数

- rid:：分区

- day：排行的天数（1、3、7、30）

- type：榜单类型

- arc_type：投稿时间

  #### **rid：**

  | 0    | 全站     |
  | ---- | -------- |
  | 1    | 动画     |
  | 168  | 国创相关 |
  | 3    | 音乐     |
  | 129  | 舞蹈     |
  | 4    | 游戏     |
  | 36   | 科技     |
  | 188  | 数码     |
  | 160  | 生活     |
  | 119  | 鬼畜     |
  | 155  | 时尚     |
  | 5    | 娱乐     |
  | 181  | 影视     |

  #### **type：**

  | 1    | 全站榜 |
  | ---- | ------ |
  | 2    | 原创榜 |
  | 3    | 新人榜 |

  #### **arc_type：**

  | 0    | 全部投稿 |
  | ---- | -------- |
  | 1    | 近期投稿 |

  

  ### 纪录片榜：https://www.bilibili.com/index/rank/all-3-177.json

  ### 电影榜：https://www.bilibili.com/index/rank/all-3-23.json

  ### 电视剧榜：https://www.bilibili.com/index/rank/all-3-11.json

  

  **这四个api返回的数据格式都相同，数据解析:**

```json
{
    "code": 0,
    "message": "0",
    "ttl": 1,
    "data": {
        "note": "统计所有投稿在 2019年08月30日 - 2019年08月31日 的数据综合得分，每日更新一次",   //说明
        "list": [   			//这个列表是存放排行榜中所有视频的一些信息
            {
                "aid": "65844602",  //视频av号
                "author": "老番茄",  //up主名称
                "coins": 478320,    //硬币数
                "duration": "23:56",  //视频长度
                "mid": 546195,      //up主uid
                "others":[	//该up主其他上榜的视频信息
                    0: {
                          "aid": ,
                          "coins": ,
                          "duration": ,
                          "pic": ,
                          "play": ,
                          "pts": ,
                          "rights": {} ,
                          "title": ,
                          "video_review": 
            	    },
                ],        
                "pic": "",		//视频封面图片
                "cid": 114232032,   //弹幕库id
                "play": 1887861,    //播放量
                "pts": 6235632,     //综合得分
                "title": "",	//视频标题
                "trend": null,	 //未知
                "video_review": 52453,  //弹幕数
                "rights": {		//视频的一些权限信息？
                    "bp": 0,
                    "elec": 0,
                    "download": 0,
                    "movie": 0,
                    "pay": 0,
                    "hd5": 0,
                    "no_reprint": 1,
                    "autoplay": 1,
                    "ugc_pay": 0,
                    "is_cooperation": 0,
                    "ugc_pay_preview": 0
               }	
            }
        ]
    }
}
```



## up主充电人数api

### https://elec.bilibili.com/api/query.rank.do?mid={}

### 参数：

- mid：up主uid

```json
{
    "code": 0,		//响应码
    "data": { 		//响应数据
        "display_num": 0, //未知？？  
        "count": 9,       //本月充电人数
        "total_count": 3366,  //总充电人数
        "list": [],       //充电用户的信息
        "user": null   
    }
}
```



## up主粉丝数api

### https://api.bilibili.com/x/relation/stat?vmid={}

### 参数：

- vmid：up主uid

```json
{
    "code": 0,
    "message": "0",
    "ttl": 1,
    "data": {
        "mid": 391679,    //up主uid
        "following": 0,   //关注人数
        "whisper": 0,     //？？
        "black": 0,       //黑名单？
        "follower": 2136861   //粉丝数
    }
}
```



## up主相簿api

### https://api.bilibili.com/x/space/album/index?mid={}&ps={}

### 参数：

- mid：up主uid
- ps：显示相簿的数量，设置1000都可以

```json
{
    "code": 0,
    "message": "0",
    "ttl": 1,
    "data": [
        {
            "doc_id": 32580598,    //相簿文章id 
            "poster_uid": 391679,  //up主uid
            "title": "",	//标题？？
            "description": "",     //描述
            "pictures": [],  	   //相簿中的图片
            "count": 6,            //图片数
            "ctime": 1566030436,   //创建时间
            "view": 1625789,       //点击量
            "like": 4549           //点赞量
        },
```



## up主视频相簿音频等数目api

###  https://api.bilibili.com/x/space/navnum?mid={}

### 参数：

- mid：up主uid

```json
{
    "code": 0,
    "message": "0",
    "ttl": 1,
    "data": {
        "video": 896,   //up主视频总数
        "bangumi": 17,  //订阅番剧数
        "cinema": 0,    //电影？？
        "channel": {    //频道数
            "master": 7,
            "guest": 7
        },
        "favourite": {   //收藏夹数
            "master": 38,
            "guest": 38
        },
        "tag": 5,     //分区？？
        "article": 0,  //文章数
        "playlist": 0,  //播放列表？？
        "album": 24,   //相簿数
        "audio": 0    //音频数
    }
}
```



## up主播放总数和文章点击总数api

###  https://api.bilibili.com/x/space/upstat?mid={}

### 参数：

- mid：up主uid

```json
{
    "code": 0,
    "message": "0",
    "ttl": 1,
    "data": {
        "archive": {
            "view": 110507798   //视频播放总数
        },
        "article": {
            "view": 0      //文章点击总数
        }
    }
}
```





## up主发布的视频api

###  https://space.bilibili.com/ajax/member/getSubmitVideos?mid=391679&pagesize=100&tid=&page=1&keyword=&order=pubdate

### 参数：

- mid：up主uid
- pagesize：一页显示的数据条数，最大100
- tid：根据分区id查找
- page：查询第几页，一页100条，需根据up主的视频总数来决定，一般1就可以
- keyword：根据关键字来查找，匹配***title***、***description***、***author***里的字
- order：排序方式，默认是***pubdate***

```json
{
    "status": true,
    "data": {
        "tlist": {	//分区列表，存放up主在某个分区投稿的数量，
            "1": {
                "tid": 1,	//分区id
                "count": 2, 	//投稿数量
                "name": "动画"    //分区名称
            }, 
        },
        "vlist": [	//视频列表
            {
                "comment": 1823,   //该视频的评论数
                "typeid": 193,     //该视频的子分区id
                "play": 338538,    //播放量
                "pic": "",		//视频封面图片
                "subtitle": "",	//子标题
                "description": "",	//视频描述
                "copyright": "",	//版权
                "title": "",	//视频标题
                "review": 0,	//？？？
                "author": "A路人",   //up主名称
                "mid": 391679,       //up主uid
                "is_union_video": 1,  //是否是合作视频，1为是，0为否
                "created": 1567340683,  //发布时间
                "length": "04:39",    //视频长度
                "video_review": 3250,  //弹幕数
                "is_pay": 0,           //？？？
                "favorites": 18754,    //收藏数
                "aid": 66303882,       //视频av号
                "hide_click": false    //隐藏点击？？
            },
        ],
        "count": 165,	//up主视频总数
        "pages": 2 	//视频页数
    }
}
```

