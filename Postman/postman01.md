## 在使用postman中 form-data、x-www-form-urlencoded、raw、binary的区别 ##
### from-data ###
为http请求中的multipart/form-data，它会将表单的数据处理为一条消息，以标签为单元，用分隔符分开。既可以上传键值对，也可以上传文件。当上传的字段是文件时，会有Content-Type来表名文件类型；content-disposition，用来说明字段的一些信息
  ![from-data](http://upload-images.jianshu.io/upload_images/9673971-d579903ccad749a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 >multipart表示的意思是单个消息头包含多个消息体的解决方案，multipart媒体类型对发送非文本的各媒体类型是有用的。一般多用于文件上传。

### x-www-form-urlencoded ###
为application/x-www-from-urlencoded,窗体数据被编码为名称/值对，这是标准且默认的编码格式。当action为get时候，客户端把form数据转换成一个字串append到url后面，用?分割。当action为post时候，浏览器把form数据封装到http body中，然后发送到server
  ![x-www-form-urlencoded](http://upload-images.jianshu.io/upload_images/9673971-5436056c3cb4863b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### raw ###
 可以上传任意格式的文本，可以上传text、json、xml、html等
![raw](http://upload-images.jianshu.io/upload_images/9673971-a66b16b1ecf159e6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### binary ###
  相当于Content-Type:application/octet-stream,从字面意思得知，只可以上传二进制数据，通常用来上传文件，由于没有键值，所以，一次只能上传一个文件。

## 关于HTTP动词 ##
**其实http请求完全不止于常见的get，post**，参考[RESTful架构](http://www.ruanyifeng.com/blog/2011/09/restful.html)

客户端通过HTTP动词，对服务器端资源进行操作，实现"表现层状态转化"
- GET（查询）：从服务器取出资源（一项或多项）
- POST（增加）：在服务器新建一个资源
- PUT（更新）：在服务器更新资源（客户端提供完整资源数据）
- PATCH（更新）：在服务器更新资源（客户端提供需要修改的资源数据）
- DELETE（删除）：从服务器删除资源
