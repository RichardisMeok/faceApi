#### 接口版本：

|版本号|制定人|制定日期|修订日期|
|:----    |:---|:----- |-----   |
|1.0.0 |谭成  |2019-11-27 |  2019-11-27|

#### 登录请求URL:
/manager/user_login.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 请求示例:

```
{
 "openId":"xxxxxxxx",
 "userPhone":"186xxxx",
 "smsCode":"xxx"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|openId |是  |String | wxopenId（单独必须） |
|userPhone |是  |String | 电话号码（电话登录必须） |
|smsCode |是  |String | 请求类型（电话登录必须） |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "操作成功",
    "data":{"token":"xxxxx"}
}


```

**错误时返回:**


```
{
    "code": -1,
    "msg": "无此账号或用户名密码错误",
    "data": null
}
```


#### 获取项目列表URL:
/manager/get_projects.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 请求示例:

```
{
 "token":"xxxxxxxx",
 "projectType":1,
 "keyword":"小学"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|token |是  |String | token |
|projectType |是  |int | 项目类型 |
|keyword |否  |int | 模糊匹配关键字 |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "操作成功",
    "data":[{
    "id":1,
    "projectCode":"school-1",
    "projectName":"南区小学",
    "projectType":"1" //1:学校，2工地
}]
}


```

**错误时返回:**


```
{
    "code": -1,
    "msg": "暂无权限",
    "data": null
}
```


#### 获取项目列表URL:
/manager/get_users.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 请求示例:

```
{
 "token":"xxxxxxxx",
 "projectId":1,
 "keyword":"张三"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|token |是  |String | token |
|projectId |是  |long | 项目Id |
|keyword |否  |int | 模糊匹配关键字 |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "操作成功",
    "data":[{
    "createTime":15789556622,
    "groupId":23,
    "groupName":"高三一班",
    "groupNo":"23",
    "id":122355,
    "idCardNum":"51095525886662",
    "imageData":null,  //为空代表未录入base64
    "imagePath":null,  //为空代表未录入url
    "projectCode":"1",
    "projectId":1,
    "rfid":"001558866",
    "timeSetStr":null,
    "userName":"张三",
    "userNo":"15",
}]
}


```

**错误时返回:**


```
{
    "code": -1,
    "msg": "暂无权限",
    "data": null
}
```