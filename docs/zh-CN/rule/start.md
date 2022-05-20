# 开始

轻文社创始人 [Prk](https://imprk.me 'Prk的网站')要求 API 要统一。包括 API 在不同的情况下需要传递不同的请求方法，都是有明确规定的！对请求地址的要求也是严格要求的。接下来，文档将告诉您有关规范要求的信息。


## 统一化不同服务的请求地址

如果你有使用过哔哩哔哩弹幕网，你会发现其与其衍生产品（哔哩哔哩直播）使用了两个不同的 API 地址，有些请求杂乱无章。这样后期维护会比较麻烦！为了解决这个问题，轻文社决定将所有服务的 API 地址整合到同一个中。

```URL:no-line-numbers
https://api.qinglite.com
```

当有不同的业务需求时，您可以通过不同的一级路由获取到您想要的资源！例如，以下 API 地址分别用于请求 [用户账户信息](/zh-CN/account/get-info.html '获取用户账户信息') 和 [动态信息](/zh-CN/dynamic/get-info.html '获取用户动态信息') ：

```URL:no-line-numbers
https://api.qinglite.com/account
https://api.qinglite.com/dynamic
```


## 统一化请求方式

我们最常用的请求方式有 `GET`、`POST`、`DELETE`、`PUT`、`PATCH` 等，目前轻文社的业务只需要 `GET` 和 `POST` 两种请求方式。`GET` 方法用于获取数据；`POST` 方法用于操作数据。

例如，以下 API 地址用于获取用户数据的：

```URL:no-line-numbers
https://api.qinglite.com/account?uid=1
```

而下面的 API 地址是用来提交数据的：

```URL:no-line-numbers
https://api.qinglite.com/login
```


## 统一化编码格式

`UTF-8` 是一种用于电子通信的可变宽度字符编码。该名称由 Unicode 标准定义，源自 Unicode（或通用编码字符集）转换格式 – 8 位。这种编码格式可以有效防止出现乱码。因此，轻文社将这种编码格式作为请求的编码格式。


## 统一化响应格式

`XML` 已经过时了！`JSON` 已经能够代替它的地位。`JSON` 现在是 “万王之王”。轻文社将 `JSON` 定义为返回的数据格式。


## 返回结果解释

::: tip
在返回的数据中，“`data`” 中的值就是您想要获取的数据。

“`code`” 的值是状态码，下面会提到。

“`msg`” 的值是一条错误消息。当 “`code`” 的值不是正常值时，“`msg`” 会显示错误信息。在某些特殊情况下，“`msg`” 的值不一定是错误消息。

“`time`” 参数的值为 Unix 时间戳，是东八区（UTC+8）时间。
:::


| 键名    | 类型     | 例子              | 备注               |
| :-----: | :-----: | :---------------: | :---------------: |
| code    | 数字     | 0                 | 状态码            |
| msg     | 字符串   | 0                 | 状态信息           |
| data    | 数组     | {}                | API 数据          |
| time    | 数字     | 114514            | Unix 时间戳       |


## DEMO
<CodeGroup>
    <CodeGroupItem title="PHP" active>

```php
<?php
/**
 * Name: Request DEMO PHP
 * Author: Prk
 * Website: https://imprk.me
 * Date: 2022-05-19
 * Location: Shanghai, People's Republic of China
 */
    $a = json_decode (
        file_get_contents (
            'https://api.qinglite.com/'
        ),
        true
    );
    echo $a;
?>
```

  </CodeGroupItem>
  <CodeGroupItem title="JavaScript">

```js
/**
 * Name: Request Demo JavaScript
 * Author: Prk
 * Website: https://imprk.me
 * Date: 2022-05-19
 * Location: Shanghai, People's Republic of China
 */
    var a = {}
    fetch (
        'https://api.qinglite.com/'
    )
        .then (
            api => api.json()
        )
        .then (
            json => {
                a = json
            }
        )
    console.log (
        a
    )
```

  </CodeGroupItem>
  <CodeGroupItem title="Vue">

```vue
<template>
    <div class="demo">
        {{ a }}
    </div>
</template>

<script>
    export default {
        name: 'demo',
        setup() {

            let a = {}

            // Fetch / jQuery Ajax / Axios Requests

            return {
                a
            }
        }
    }
</script>
```

  </CodeGroupItem>
</CodeGroup>