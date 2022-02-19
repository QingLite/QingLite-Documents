# Login to QingLite
## 1. Request Address
`https://api.qinglite.com/login`
## 2. Request Method
`POST`
## 3. Encoding Format
`UTF-8`
## 4. Resulting Format
`JSON` or `JSONP`
## 5. Need to pass parameters
| Value | Type | Must | Example | Remark |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| phone | Str | √ True | 13800000000 | User login phone number |
| password | Str | √ True | dGhpc2lzcGFzc3dvcmQ= | User login password (Base64 encode) |
## 6. Request Example
`https://api.qinglite.com/login?phone=13800000000&password=dGhpc2lzcGFzc3dvcmQ=`
## 7. Resulting Example
```JSON
{
	"code": 0,
	"msg": "0",
	"data": {
		"token": ""
	}
}
```
## 8. Resulting Explanation
waited updating... ...
