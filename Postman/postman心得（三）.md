# postman使用心得（三）：轻便快捷的接口自动化持续集成实现方式 #
## 环境配置 ##
1. 安装postman（[https://www.getpostman.com/](https://www.getpostman.com/)）
2. 下载安装nodejs （[https://nodejs.org/en/download/](https://nodejs.org/en/download/)）
3. 在控制台输入node，如果显示“>”，说明安装成功![node验证](https://upload-images.jianshu.io/upload_images/9673971-c09a356224ba6f13.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


4. 在控制台输入```npm install -g newman ```下载newman![下载newman.png](https://upload-images.jianshu.io/upload_images/9673971-75ccb70805f85187.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5. 验证newman版本，在控制台输入newman --version![查看newman的版本](https://upload-images.jianshu.io/upload_images/9673971-f9fbf4b9bdece790.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##postman的用例集的操作
1. 在postman的collection添加一个测试集合文件夹
![添加用例集合](https://upload-images.jianshu.io/upload_images/9673971-1575025938dda9f3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2. 导出用例集的，存为json格式
![用例集合导出](https://upload-images.jianshu.io/upload_images/9673971-15e85e60e1afafb7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3. 使用newman命令```newman run  文件地址```，运行导出的测试用例集! ![newman运行](https://upload-images.jianshu.io/upload_images/9673971-eb5822445d37f16a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4. 生成html格式的报告```newman run postman导出的用例集合.json -r html```![输出html格式](https://upload-images.jianshu.io/upload_images/9673971-4745e2f440646098.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


5. newman常用命令集（[https://github.com/postmanlabs/newman#configuring-reporters](https://github.com/postmanlabs/newman#configuring-reporters)）


## jenkins的持续集成
1. jenkins下载（[https://jenkins.io/](https://jenkins.io/)）
>安装之前需要说明：需要先安装jdk，这里我本机已经安装，此处不再赘述。安装jdk之后可以查看jdk是否安装好，jdk -version
2. 安装成功后，访问http://localhost:8080，默认端口号是8080
3. 在jenkins主页，新增一个项目![jenkins主页](https://upload-images.jianshu.io/upload_images/9673971-7e59b42c9257c940.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4. 在项目主页中打开配置![项目配置](https://upload-images.jianshu.io/upload_images/9673971-0166b302d7ade65f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5. 在配置的构建中输入命令运行路径```newman run C:\Users\windz\Desktop\test.ctb.postman_collection.json -r html```![构建配置](https://upload-images.jianshu.io/upload_images/9673971-2cc64b005ad17974.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

开始执行吧！
