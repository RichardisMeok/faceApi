#### 接口版本：

|版本号|制定人|制定日期|修订日期|
|:----    |:---|:----- |-----   |
|1.0.0 |Richard  |2019-11-27 |  2019-11-27|

#### 发送请求URL:
/manager/send_sms.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 请求示例:

```
{
 "phone":"186xxxx"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|phone |是  |String | 电话号码（电话登录必须） |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "操作成功",
    "data":null
}


```

**错误时返回:**


```
{
    "code": 400,
    "msg": "无此账号或用户名密码错误",
    "data": null
}
```

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
 "phone":"186xxxx",
 "smsCode":"xxx"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|openId |是  |String | wxopenId（单独必须） |
|phone |是  |String | 电话号码（电话登录必须） |
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
    "code": 400,
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
    "code": 400,
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
 "keyword":"张三",
 "page":1,
 "limit":10
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
    "errorInfo":"未检测到人脸"
}]
}


```

**错误时返回:**


```
{
    "code": 400,
    "msg": "暂无权限",
    "data": null
}
```

#### 上传用户照片URL:
/manager/upload_imgs.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |multipart/form-data |请求类型   |

#### 请求方式：

- POST


#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|token |是  |String | token |
|file{N} |是  |file | 用户照片，多张照片file1,file2,file3 |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "操作成功",
    "data":{"images":["url1","url2","url3"]
}
}


```

**错误时返回:**


```
{
    "code": 4001,
    "msg": "暂无权限",
    "data": null
}
```


#### 修改用户照片URL:
/manager/update_user_face.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 示例数据

```
{
    "token":"5eb64b0db4ed4e8c9ee9597a81edca47",
    "rfid":"1118439851",
    "facePaths":[
        "https://zixng2.oss-cn-beijing.aliyuncs.com/static/kaoqin/face/2cff663918294eeebfc566a445909dc4.jpg"
    ]
}


```


#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|token |是  |String | token |
|rfid |是  |String | 用户卡号 |
|facePaths |是  |array | 用户照片 |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "SUCCESS",
    "msg": null,
    "data": "操作成功",
    "serverTime": 1575135424052
}


```

**错误时返回:**


```
{
    "code": 400,
    "msg": "暂无权限",
    "data": null
}
```


#### 获取设备列表URL:
/manager/get_devices.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 示例数据

```
{"token":"5eb64b0db4ed4e8c9ee9597a81edca47","projectId":1}

```


#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|token |是  |String | token |
|projectId |是  |int | 项目id |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "SUCCESS",
    "msg": null,
    "data":  [
        {
            "id": 4,
            "deviceName": null,
            "mac": "xx",
            "deviceType": null,
            "inOut": null,
            "projectCode": "18",
            "projectId": 1,
            "nirPreview": 1,
            "lightTimeout": 10,
            "pollingTime": 10,
            "reboot": 1,
            "needRefresh": 0,
            "baseUrl": "xx",
            "onlineState": true
        },
        {
            "id": 5,
            "deviceName": null,
            "mac": "xx",
            "deviceType": null,
            "inOut": null,
            "projectCode": "18",
            "projectId": 1,
            "nirPreview": 1,
            "lightTimeout": 10,
            "pollingTime": 10,
            "reboot": 1,
            "needRefresh": 0,
            "baseUrl": "xx9",
            "onlineState": false
        },
        {
            "id": 6,
            "deviceName": null,
            "mac": "xx",
            "deviceType": null,
            "inOut": null,
            "projectCode": "1",
            "projectId": 1,
            "nirPreview": 1,
            "lightTimeout": 10,
            "pollingTime": 10,
            "reboot": 1,
            "needRefresh": 0,
            "baseUrl": "hxx",
            "onlineState": false
        },
        {
            "id": 8,
            "deviceName": null,
            "mac": "xx",
            "deviceType": null,
            "inOut": null,
            "projectCode": "23",
            "projectId": 1,
            "nirPreview": 1,
            "lightTimeout": 10,
            "pollingTime": 10,
            "reboot": 1,
            "needRefresh": 0,
            "baseUrl": "xx",
            "onlineState": false
        }
    ],
    "serverTime": 1575213437382
}


```

**错误时返回:**


```
{
    "code": 400,
    "msg": "暂无权限",
    "data": null
}
```


#### 获取设备列表URL:
/manager/update_device.do

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-type |是  |application/json |请求类型   |

#### 请求方式：

- POST

#### 示例数据

```
     {
           "token":"xxx",
            "deviceId": 4,
            "deviceName": xx,
            "inOut": null, //1进，2出
            "nirPreview": 1,//开启红外 1，开启 0关闭
            "lightTimeout": 10,//补光延迟秒
            "pollingTime": 10,//获取数据轮询时间
            "reboot": 1,//1重启，0不重启
            "needRefresh": 0,//1 刷新，-1正在刷新，0未执行刷新
            "baseUrl": "xx"//服务端基础地址
           
        }

```


#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|token |是  |String | token |
|projectId |是  |int | 项目id |


#### 返回示例:

**正确时返回:**

```
{
    "code": 200,
    "message": "SUCCESS",
    "msg": null,
    "data":""
}


```

**错误时返回:**


```
{
    "code": 400,
    "msg": "暂无权限",
    "data": null
}
```



