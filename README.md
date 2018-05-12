# testAutoDeploy    hi

可参考案例: [Integrating GitHub with Jenkins for Continuous Integration and Deployment](https://blog.doordash.com/integrating-github-with-jenkins-for-continuous-integration-and-deployment-7cae2c2161cb)

需要开发中间gateway 负责接收webhook通知, 并调用jenkins api, 以及返回build 状态

## 目标

1. 配置 jenkins 跟 git 联动  基本OK 
2. jenkins 触发 docker image build 操作
3. 新image 发布到 registry, 并使用docker swarm 部署到集群上
4. 启动测试自动化执行  测试用例的执行方式?
5. benchmark 执行方式

### 5.10
1. 配置 swarm 集群的运行方式(非负载均衡 host mode), 配置文件目录, 配置多组件
2. 服务更新 


### 5.9

1. 使用 docker machine 创建多个 docker 宿主机  OK
2. 构建 docker swarm 集群  OK
3. 部署服务image, 并保证服务正常运行  OK


### 问题
1. golang 的依赖模块如何安装? -- (copy源码之后执行go install; 放到vendor中直接copy)
2. docker 中的服务如何访问外部服务 ? 指定同局域网的 ip 地址
3. golang 服务, 可以跟redis 打到一块, 成为一个image



### notice

1. 使用 docker 部署, docker 更新, 数据文件需要保存, 需要外挂目录

### 账户信息
Jenkins
pana/pana
admin/

服务器jenkins 密码
admin/fbcd3b2308d141e789604dd5ca95e740



### 文档

* [jenkins docker doc](https://github.com/jenkinsci/docker/blob/master/README.md)
* [Docker持续部署图文详解](http://www.infoq.com/cn/articles/effective-ops-part-06)
* [docker 入门教程 101](http://dockone.io/article/101)
* [Docker 三剑客之 Docker Swarm](https://www.cnblogs.com/xishuai/p/docker-swarm.html)
* [Docker Swarm架构、特性与基本实践](https://blog.csdn.net/kenkao/article/details/78809330)
* [Docker 从入门到实践](https://yeasy.gitbooks.io/docker_practice/content/)
* [Docker挂载本地目录](https://blog.csdn.net/magerguo/article/details/72514813)
* [如何使用docker 安装jenkins](https://blog.csdn.net/boling_cavalry/article/details/78942408) 反向代理需要配置
* [实战：向GitHub提交代码时触发Jenkins自动构建](https://blog.csdn.net/boling_cavalry/article/details/78943061)
* [Setup Jenkins for Go Project](https://zpjiang.me/2017/08/09/Setup-Jenkins-for-Go-Projects/)



### docker swarm

* Swarm 集群网络的创建与部署。
* Swarm 的服务发现、负载均衡等，
* 使用 Swarm 来配置跨主机容器网络，并在上面部署应用
* [swarm Bypass the routing mesh](https://docs.docker.com/engine/swarm/ingress/#bypass-the-routing-mesh)
