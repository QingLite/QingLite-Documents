# Start

QingLite founder [Prk](https://imprk.me 'Prk\'s WebSite')'s requirement for the API is that it must be unified. Including that the API needs to pass different request methods in different situations, it is clearly stipulated! The requirements for the request address are also strictly required. Next, the document will tell you about the specification request.


## Unification of request addresses for different services

If you have used Bilibili, you will find that there are two API addresses for this product and derivative products (Bilibili Live), and some requests are disorganized. This will become more troublesome for post-maintenance! In order to solve this problem, QingLite decided to integrate the API addresses of all services into the same one.

```URL:no-line-numbers
https://api.qinglite.com
```

When there are different business needs, you can find the resources you want through different first-level routes! For example, the following API addresses are for requesting [account information](/get/account.html 'Get User Account Information') & [dynamic information](/get/dynamic.html 'Get User Dynamic Information') respectively:

```URL:no-line-numbers
https://api.qinglite.com/account
https://api.qinglite.com/dynamic
```


## Unified request method

The most common request methods we use are `GET`, `POST`, `DELETE`, `PUT`, `PATCH`, etc. At present, QingLite's business only needs 2 request methods: `GET` and `POST`. The `GET` request method is used to obtain data; the `POST` request method is used to manipulate the data.

For example, the following API address is used to obtain user data:

```URL:no-line-numbers
https://api.qinglite.com/account?uid=1
```

And the following API address is used to submit data:

```URL:no-line-numbers
https://api.qinglite.com/login
```


## Encoding Format

`UTF-8` is a variable-width character encoding used for electronic communication. Defined by the Unicode Standard, the name is derived from Unicode (or Universal Coded Character Set) Transformation Format – 8-bit. This encoding format can effectively prevent garbled characters from appearing. Therefore, QingLite takes this encoding format as the encoding format of the request.


## Resulting Format

`XML` has become obsolete! Then came `JSON` in its place. `JSON` is now the "king of kings". QingLite defines `JSON` as the returned data format.


## Resulting Explanation

::: tip
In the returned data, the value in "data" is the data you want to get.

The value of "code" is the status code, described below.

The value of "msg" is an error message. When the value of "code" is not a normal value, then "msg" will display an error message. In some exceptional cases, the value of "msg" is not necessarily an error message.

The value of the "time" parameter is the Unix timestamp, which is the East Eighth District (UTC+8) time.
:::


| Value   | Type    | Example           | Remark            |
| :-----: | :-----: | :---------------: | :---------------: |
| code    | Int     | 0                 | Status Code       |
| msg     | Str     | 0                 | Status Message    |
| data    | Array   | {}                | API Data          |
| time    | Int     | 114514            | Unix Timestamp    |


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