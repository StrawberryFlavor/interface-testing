# postman使用心得（二） #

## 在使用postman做接口测试的时候，可以在tests中对该接口进行断言设置 ##
![json字符串解析断言](http://p4uuxwp7i.bkt.clouddn.com/%E6%8E%A5%E5%8F%A3%E8%BF%94%E5%9B%9E.png)

上面的图为使用postman断言方法之一，使json解析key的值进行校验	
```
tests["Your test name"] = jsonData.value === 100;
```
**其中 Your test name 为断言名，jsonData.value表示为对json进行解析，=== 100 表示为key的value值**
```
{
  "ok": true,
  "data": {
    "user": {
      "user_no": "888",
      "type": "1",
      "user_name": "W HE",
      "fullname": "W HE",
      "nickname": "",
      "login_name": "1258@qq.com",
      "headimg": "",
      "is_payed": true,
      "is_certified": false
    },
    "redirect_url": "/team/search"
  }
}
```
>jsonData["data"]["user"]["user_name"] === "W HE"  

## 附： ##


| 常用的postman断言         |     解释           |  对应脚本          |
| -------------- | -------------- | ---------- |
| Response body:Contains string  | response包含字符串 | tests["Body matches string"] = responseBody.has("string_you_want_to_search"); |
| Response body:Is equal to a string | response body等于指定字符串 | tests["Body is correct"] = responseBody === "response_body_string"; |
| response body:JSON value check | json解析key的值进行校验 | tests["Your test name"] = jsonData.value === 100; |
|status code:Code is 200 | 判断状态码 |tests["Status code is 200"] = responseCode.code === 200;|
|status code:code name has string | 检查code name 是否包含内容 |	tests["Status code name has string"] = responseCode.name.has("Created");|