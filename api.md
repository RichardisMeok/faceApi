#### 接口版本：

|版本号|制定人|制定日期|修订日期|
|:----    |:---|:----- |-----   |
|1.0.0 |Richard  |2019-09-22 |  2019-09-22|


#### 备注:
|code|msg|备注|
|:----    |:---|:----- |
|0 |成功  | |
|-1|非法设备 | &nbsp;|


### 获取人脸：
#### 请求URL:

- http://ip:port/v1/get_person.do

#### 请求方式：

- POST

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-Type |是  |string |请求类型： application/json   |

#### 请求示例:

```
{
"device_no": "aa：bb:cc:dd",
"last_employee_number": 0
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|device_no |是  |String |  设备唯一标识 |
|last_employee_number |是  |Long |  设备本地最大人员id |


#### 返回示例:

**正确时返回:**

```
{
    "code": 0,
    "msg": "请求成功",
    "data": [
		{
			"employee_number":1,
			"card_no":["112234556"],
			"name":"张三",			
			"image":["data:image/jpeg;base64,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"]
		}
	]
}


```

**错误时返回:**

```
{
    "code": -1,
    "msg": "非法设备",
    "data": null
}
```

#### 返回参数说明:

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|employee_number |Long   |人员id  |
|card_no |String数组（为后续扩展支持，一个人多张卡）   |rfid卡号  |
|image |String数组（为以后多照片扩展）   | 照片base64字符串 |



### 上传失败人脸：
- ***每5分钟上传一次（重复上传）***
#### 请求URL:

- http://ip:port/v1/upload_failed_person.do

#### 请求方式：

- POST

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-Type |是  |string |请求类型： application/json   |

#### 请求示例:

```
{
"device_no": "aa：bb:cc:dd",
"failed_data": [{
	"employee_number":1,
	"reason"："图片存在相似记录",
	"code":1
},{
	"employee_number":2,
	"reason"："图片解析失败",
	"code":2
}]
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|device_no |是  |String |  设备唯一标识 |
|failed_data |是  |Object数组 |  失败数据，详见示例数据 |
|code |是  |错误码 |  参考已有sdk定义 |


#### 返回示例:

**正确时返回:**

```
{
    "code": 0,
    "msg": "请求成功",
    "data":null
}


```

**错误时返回:**

```
{
    "code": -1,
    "msg": "非法设备",
    "data": null
}
```



### 获取是否需要重新更新状态：
- ***每5分钟获取一次***
#### 请求URL:

- http://ip:port/v1/get_reset_status.do

#### 请求方式：

- POST

#### 请求头：

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|Content-Type |是  |string |请求类型： application/json   |

#### 请求示例:

```
{
"device_no": "aa：bb:cc:dd"
}

```

#### 请求参数:

|参数名|是否必须|类型|说明|
|:----    |:---|:----- |-----   |
|device_no |是  |String |  设备唯一标识 |


#### 返回示例:

**正确时返回:**

```
{
    "code": 0,
    "msg": "请求成功",
    "data":{
		"need_refresh":1
	}
}


```

**错误时返回:**

```
{
    "code": -1,
    "msg": "非法设备",
    "data": null
}
```
#### 返回参数说明:

|参数名|类型|说明|
|:-----  |:-----|-----|
|need_refresh |int   |1：需要立即从头获取（将本地清空） 0：无需从头获取 |

