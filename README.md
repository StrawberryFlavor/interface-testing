# 关于接口测试
## 什么是接口测试 ##
接口测试是测试系统组件间接口的一种测试，接口测试主要用于检测外部系统与系统之间以及内部各个子系统之间的交互点，测试的重点是要检查数据的交换，传递和控制管理过程，以及系统间的相互逻辑依赖关系等

## 为什么要做接口测试 ##
1. 如今的系统复杂度不断上升，传统的测试方法成本急剧增加且测试效率大幅下降，接口测试可以提供这种情况下的解决方案

2. 接口测试相对容易实现自动化持续集成，且相对UI自动化也比较稳定，可以减少人工回归测试人力成本与时间，缩短测试周期，支持后端快速发版需求。接口持续集成是为什么能低成本高收益的根源

3. 现在很多系统前后端架构是分离的，从安全层面来说：
	- 只依赖前端进行限制已经完全不能满足系统的安全要求（绕过前面实在太容易）， 需要后端同样进行控制，在这种情况下就需要从接口层面进行验证
	- 前后端传输、日志打印等信息是否加密传输也是需要验证的，特别是涉及到用户的隐私信息，如身份证，银行卡等

## 目录引导 ##

### [postman使用随笔记录 ](https://github.com/StrawberryFlavor/interface-testing/tree/master/Postman)
- [**postman使用心得（一）：postman基础理论**](https://github.com/StrawberryFlavor/interface-testing/blob/master/Postman/postman%E5%BF%83%E5%BE%97%EF%BC%88%E4%B8%80%EF%BC%89.md)



- [**postman使用心得（二）：postman接口测试断言**](https://github.com/StrawberryFlavor/interface-testing/blob/master/Postman/postman%E5%BF%83%E5%BE%97%EF%BC%88%E4%BA%8C%EF%BC%89.md)



- [**postman使用心得（三）：轻便快捷的接口自动化持续集成实现方式**](https://github.com/StrawberryFlavor/interface-testing/blob/master/Postman/postman%E5%BF%83%E5%BE%97%EF%BC%88%E4%B8%89%EF%BC%89.md)