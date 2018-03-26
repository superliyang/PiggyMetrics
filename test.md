#### 接口说明
注册登录并返回用户信息
#### 请求方式
|方式|URL|其他|
|---|--------------|---|
|POST/GET|/passport/loginreg/registerAndGetUInfo||

#### 请求参数
|字段|	类型|	是否必填|	描述|	取值|
|----|--|--|-----------------------|----|
|userName|		String|	N|	用户名|	userName、mobile、email必须有一个不能为空|
|email|		String|	N|	邮箱	||
|mobile|		String|	N|	手机	||
|passportPwd|		String|	Y|	密码	密码||
|passportFromType|		int|	Y|	用户类型|（B端、C端）	0：个人、1：企业|
|realName|		String|	N|	真实姓名|	自定义|
|countryCode|		String|	N|	国别号|	mobile不为空时必填|
|fromType|		int|	N|	来源系统|	自定义|
|refer|		String|	N|	推广地址、来源|	自定义|
|scodeType|		int|	Y|	验证码类型（手机验证码、图形验证码）|	1：图形验证码、2：手机验证码、3：邮箱验证码|
|code|		String|	Y|	验证码|	通过验证码获取|
|codeId|		String|	N|	图形验证码时不能为空（原abs）|	验证码类型为图形验证码时不能为空|
|clientType|		String|	Y|	客户端（PC、移动等等）|	自定义|
|deviceID|		String|	N|	设备号（移动标识）|	自定义|
|userAgent|		String|	N|	浏览器信息（PC标识）|	自定义|
|clientIp|		String|	Y|	用户IP|	自定义|
|businessSystem|		int|	Y|	业务系统标识|	自定义|


#### 响应参数
|字段| | |类型|	描述|
|--|--|--|--|--|
|code| | |String| 错误码|
|data| | | | |
| |at| |String|access_token|
| |rt| |String|refresh_token|
| |expireTime| |int|expireTime|
| |userInfo||String|用户信息|
| | |realName|String|真实姓名|
| | |userId|int|用户ID|
| | |userStatus|int|用户状态|
|message|||String| 错误描述|
|taskId| | |String| |
|time| | |date| |
#### 示例

##### 请求示例
```
userName=huaxian0111&passportFromType=0&countryCode=00886&passportPwd=123123&clientIp=10.10.10.10&clientType=a&businessSystem=1&deviceID=abc123123android&mobile=17900000088&code=407251&scodeType=2
```

#### 响应示例
```
{
    "code": 200,
    "data": {
        "at": "463a3ba3ff5e42c4a0842085d98872b6",
        "expireTime": 43200,
        "rt": "45a2c008250345f08aa435521706d8f6",
        "userInfo": {
            "realName": null,
            "userId": 60005929,
            "userStatus": 1
        }
    },
    "message": "成功",
    "taskId": "42ff0de497f44343adeb6544adcd0b85",
    "time": 1522045024338
}
```

