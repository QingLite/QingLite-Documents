# Get QingLite Account Info
## 1. Request Address
`https://api.qinglite.com/account`
## 2. Request Method
`GET`
## 3. Encoding Format
`UTF-8`
## 4. Resulting Format
`JSON` or `JSONP`
## 5. Need to pass parameters
| Value | Type | Must | Example | Remark |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| uid | Int | √ True | 1 | User account unique UID |
## 6. Request Example
[`https://api.qinglite.com/account?uid=1`](https://api.qinglite.com/account?uid=1 "Click Me to Test")
## 7. Resulting Example
```JSON
{
	"code": 0,
	"msg": "0",
	"data": {
		"uid": 1,
		"username": "Prk",
		"bio": "游戏区UP主丨霸格联盟创始人丨cprk.cc",
		"sex": 1,
		"location": "Guangzhou Guangdong, PRC",
		"level": 0,
		"face": "https://assets-cdn1.qinglite.net/avatar/1/96398103e6200d7f8ae416c17ed2adf7c3ce904d.jpg/webp",
		"vip": {
			"vip_type": 0,
			"vip_status": null
		},
		"follows": 1,
		"fans": 3,
		"official": {
			"type": 1,
			"text": "轻文社创始人、站长"
		},
		"ban": {
			"is": false,
			"text": "这个人还没有被封禁呐！"
		},
		"is_creator": false,
		"data": {
			"likes": null,
			"view": null,
			"article": {
				"view": null,
				"likes": null
			},
			"book": {
				"view": null,
				"likes": null
			},
			"dub": {
				"view": null,
				"likes": null
			}
		},
		"attentions": []
	}
}
```
## 8. Resulting Explanation
1) Standard API Returns  

| Value | Type | Example | Remark |
| ----------- | ----------- | ----------- | ----------- |
| code | Int | 0 | Status Code |
| msg | Str | 0 | Status Message |
| data | Array | \[\] | Data |

2) Data Explanation  

| Value | Type | Example | Remark |
| ----------- | ----------- | ----------- | ----------- |
| uid | Int | 1 | User account unique UID |
| username | Str | Prk | User account nickname |
| bio | Str | Web backend engineer | User signature |
| sex | Int | 1 | 0: Hidden, 1: Male, 2: Female |
| location | Str | PRC | User DIY self-location |
| level | Int | 1 | User account level \[1-6\] |
| face | Str | https://xxx.qinglite.net/avatar/xxx.jpg/webp | User account avatar |
| vip | Array | \[\] | User account VIP info |
| - vip_type | Int | 1 | 0: No VIP,1: Ordinary VIP, 2: Annual VIP |
| - vip_status | Int | null | wait... ... |
| follows | Int | 233 | Number of follows |
| fans | Int | 233 | Number of fans |
| official | Array | \[\] | Platform official certification |
| - type | Int | 1 | 0: No official certification, 1: Personal cert, 2: Enterprises cert, 3: Gov cert |
| - text | Str | 轻文社创始人、站长 | 1 |
waited updating... ...
