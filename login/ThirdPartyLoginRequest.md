# Third Party Login Request
## 1. Request Address
`https://api.qinglite.com/login`
## 2. Request Method
`GET`
## 3. Encoding Format
`UTF-8`
## 4. Resulting Format
`JSON` or `JSONP`
## 5. Need to pass parameters
| Value | Type | Must | Example | Remark |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| type | Str | √ True | qq | Third Party Login Methods |
## 6. Request Example
[`https://api.qinglite.com/login?type=qq`](https://api.qinglite.com/login?type=qq "Click me to jump")
## 7. Resulting Example
```JSON
{
	"code": 0,
	"msg": "0",
	"data": "https://graph.qq.com/oauth2.0/authorize?response_type=code&client_id=123456&redirect_uri=https%3A%2F%2Fpassport.qinglite.com%2Flogin_return&state=19f4%2FQmd%2BAR7eN3d%2BpLROEZ%2BzjGPYV4Q%2BuFJf%2BNhuxxx"
}
```
## 8. Resulting Explanation
| Value | Type | Example | Remark |
| ----------- | ----------- | ----------- | ----------- |
| code | Int | 0 | Status Code |
| msg | Str | 0 | Status Message |
| data | Str | https://graph.qq.com/xxxx | Login Address |
## 9. Available Login Methods
| Value | Name |
| ----------- | ----------- |
| qq | ＱＱ |
| wx | WeChat |
| alipay | AliPay |
| sina | Weibo |
| baidu | Baidu |
| huawei | Huawei |
| google | Google |
| microsoft | Microsoft |
| facebook | Facebook |
| twitter | Twitter |
| github | GitHub |
| dingtalk | DingTalk |
| gitee | Gitee |
