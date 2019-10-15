#### 登录接口：

- 统一鉴权中心登录接口

#### 接口版本：

|版本号|制定人|制定日期|修订日期|
|:----    |:---|:----- |-----   |
|1.1.0 |谭成  |2019-09-11 |  2019-09-11|

#### 请求URL:

- http://ip:port/auth/user/checkLogin.do

#### 请求方式：

- POST

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-Type |是  |string |请求类型： application/json   |

#### 请求示例:

```
{
"loginName": "test001",
"password": "e10adc3949ba59abbe56e057f20f883e",
"loginWayType":"loginname"
}

{
"phone": "18628952562",
"smsCode": "112233",
"loginWayType":"phone"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|loginName |是  |String |  用户名/手机号码/三方openID或三方唯一标识 |
|password |是  |String |  md5（用户密码）或 短信验证码 |
|loginWayType |是  |String |  一、普通登录：”loginname”;  二、手机验证码登录：”phone”; 三、第三方登录：1.”wechat”:微信登录；2.”qq”:腾讯qq登录；3.”blog”:”微博登录”;4.”alipay”:支付宝登录 |
|phone |否  |String |   手机号码 验证码登录时必传 |
|smsCode |否  |String |  手机验证码 验证码登录时必传|


#### 返回示例:

**正确时返回:**

```
{
    "code": 0,
    "msg": "请求成功",
    "data": {
        "sessionId": "7860004239230427136",
        "userId": "7849173695134621696"，
		"userCenterUserId":112233
    }
}


```

**错误时返回:**


```
{
    "code": 10003,
    "msg": "用户名或密码错误",
    "data": null
}
```

#### 返回参数说明:

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|userId |String   |&nbsp;  |

#### 备注:
|code|msg|备注|
|:----    |:---|:----- |-----   |
|0 |成功  | |
|10003|用户名或密码错误 ||