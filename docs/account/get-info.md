# Get User Info

::: tip
This API can obtain user-disclosed information. When cookies are passed in, the user's undisclosed information can be obtained.
:::


## Request Address

`GET` API Address:

``` url:no-line-numbers
https://api.qinglite.com/account
```

Request Example: [https://api.qinglite.com/account?uid=1](https://api.qinglite.com/account?uid=1 "Click Me to Test")


## Request Parameters

| Value   | Type  | Must     | Example           | Remark            |
| :-----: | :---: | :------: | :---------------: | :---------------: |
| uid     | Int   | √ True   | 1                 | Account Unique ID |


## Resulting Explanation

| Value    | Type    | Example                 | Remark                          |
| :------: | :-----: | :---------------------: | :-----------------------------: |
| uid      | Int     | 1                       | User account unique UID         |
| username | Str     | Prk                     | User account nickname           |
| bio      | Str     | Web engineer            | User signature                  |
| sex      | Int     | 1                       | [Sex](/rule/sex.html)           |
| location | Str     | PRC                     | User DIY self-location          |
| level    | Int     | 1                       | User account level \[1-6\]      |
| face     | Str     | https://xxx.com/xxx.jpg | User account avatar             |
| vip      | Array   | \[\]                    | User account VIP info           |
| follows  | Int     | 233                     | Number of follows               |
| fans     | Int     | 233                     | Number of fans                  |
| official | Array   | \[\]                    | Platform official certification |
| ban      | Array   | \[\]                    | Banned                          |

waited updating... ...


## Resulting Example

``` json
{
	"code": 0,
	"msg": "0",
	"data": {
		"uid": 1,
		"username": "Prk",
		"bio": "QingLite Founder",
		"sex": 1,
		"location": "Shanghai, PRC",
		"level": 1,
		"face": "https://assets-cdn1.qinglite.net/avatar/1/96398103e6200d7f8ae416c17ed2adf7c3ce904d.jpg/webp",
		"vip": [
            0,
			null
        ],
		"follows": 1,
		"fans": 3,
		"official": [
            1,
			"轻文社创始人、站长"
        ],
		"ban": [
            false,
			null
        ],
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