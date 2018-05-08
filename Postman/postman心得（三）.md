# postman使用心得（三）：轻便快捷的接口自动化持续集成实现方式 #
## 环境配置 ##
1. 安装postman（[https://www.getpostman.com/](https://www.getpostman.com/)）
2. 下载安装nodejs （[https://nodejs.org/en/download/](https://nodejs.org/en/download/)）
3. 在控制台输入node，如果显示“>”，说明安装成功![](http://p4uuxwp7i.bkt.clouddn.com/node%20%E5%8D%9A%E5%AE%A2%E6%8B%9B%E8%81%98.png)
4. 在控制台输入```npm install -g newman ```下载newman![](http://p4uuxwp7i.bkt.clouddn.com/%E4%B8%8B%E8%BD%BDnewman.png)
5. 验证newman版本，在控制台输入newman --version![](http://p4uuxwp7i.bkt.clouddn.com/new%E7%89%88%E6%9C%AC.png)

##postman的用例集的操作###
1. 在postman的collection添加一个测试集合文件夹
![](http://p4uuxwp7i.bkt.clouddn.com/postman%E6%B7%BB%E9%9B%86%E5%90%88.png)
2. 导出用例集的，存为json格式
![](http://p4uuxwp7i.bkt.clouddn.com/postman%E5%AF%BC%E5%87%BA%E6%AD%A5%E9%AA%A4.png)
3. 使用newman命令```newman run  文件地址```，运行导出的测试用例集! ![](http://p4uuxwp7i.bkt.clouddn.com/newman%E8%BF%90%E8%A1%8Crun.png)
4. 生成html格式的报告```newman run postman导出的用例集合.json -r html```![](http://p4uuxwp7i.bkt.clouddn.com/%E6%B7%BB%E5%8A%A0%E9%9B%86%E5%90%88%E6%96%87%E4%BB%B6html.png)
5. newman常用命令集（[https://github.com/postmanlabs/newman#configuring-reporters](https://github.com/postmanlabs/newman#configuring-reporters)）


##jenkins的持续集成##
1. jenkins下载（[https://jenkins.io/](https://jenkins.io/)）
>安装之前需要说明：需要先安装jdk，这里我本机已经安装，此处不再赘述。安装jdk之后可以查看jdk是否安装好，jdk -version
2. 安装成功后，访问http://localhost:8080，默认端口号是8080
3. 在jenkins主页，新增一个项目![](http://p4uuxwp7i.bkt.clouddn.com/jenkins%E4%B8%BB%E9%A1%B5.png)
4. 在项目主页中打开配置![](http://p4uuxwp7i.bkt.clouddn.com/%E9%85%8D%E7%BD%AE.png)
5. 在配置的构建中输入命令运行路径```newman run C:\Users\windz\Desktop\test.ctb.postman_collection.json -r html```![](http://p4uuxwp7i.bkt.clouddn.com/%E6%9E%84%E5%BB%BA%E9%85%8D%E7%BD%AE.png)
开始执行吧！