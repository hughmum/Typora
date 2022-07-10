IOC AOP 简化开发



## Framework系统架构

![image-20220709124243632](https://gitee.com/hughmum/typere-drawing-bed/raw/master/img/image-20220709124243632.png)

- 核心容器
- 整合
- AOP
- 事务

使用对象时在程序中不要主动使用new独享，转换为由外部提供对象

IOC控制反转，对象的创建控制权有程序转移到外部

操作思路

在app2中，

先获取ioc容器，通过配置文件名，并作为参数；

第四步获取bean，通过容器获取，并转换类型

然后调用



DI流程

删除 set 配置

111
