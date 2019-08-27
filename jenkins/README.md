### 简介
  Jenkins是一个独立的开源软件项目,基于Java开发的一种持续集成工具,可用于自动化各种任务,如构建，测试和部署软件.

### 特点
  开源免费;支持分布式的build;可视化的管理页面;插件丰富;tips提示

### 启动
  简单启动项目,war包自带Jetty服务器
```
java -jar jenkins.war
```
  使用docker来拉起服务
```
docker pull jenkins/jenkins
docker run -d -p 49001:8080 -v $PWD/jenkins:/var/jenkins_home -t jenkins/jenkins
```

自带插件
```
maven、git、ant、jdk
```
管理插件
``` 
1、web UI中使用“插件管理器”
2、使用Jenkins CLI install-plugin命令
```   
创建管理员账户
```
admin
```
Jenkinsfile
```
包含Jenkins Pipeline定义的文本文件
```
### 常用功能
```
源码管理、构建触发器、
```

### 配置

  面向生产环境配置
  ```
  Linux服务器的配置
    - 1G内存
    - 50G数据盘
  容器部署
    - Tomcat
  创建业务用户
    - jenkins
  守护程序路径
    - /etc/init.d/jenkins
  日志输出路径
    - /var/log/jenkins/jenkins.log
  参数路径 
    - /etc/default/jenkins
  侦听端口xxxx设置
  ```
### API
  ```
  获取
  http://127.0.0.1:8080/jenkins/api/
  
  支持个格式XML、JSON、PYTHON
  
  获取JOB相关信息
  http://127.0.0.1:8080/jenkins/api/json?pretty=true
  
  获取Build相关信息(信息过滤)
  http://127.0.0.1:8080/jenkins/{build_number}/api/json?pretty=true
  
  执行Build[POST],认证、参数传递
  http://127.0.0.1:8080/jenkins/build
  
  获取和更新描述信息
  http://127.0.0.1:8080/jenkins/description
  
  禁用和启动Job
  http://127.0.0.1:8080/jenkins/disable｜enable
  
  删除JOB
  http://127.0.0.1:8080/jenkins/job/doDelete
  
  配置文件
  http://127.0.0.1:8080/jenkins/job/conofig.xml
  
  站点
  http://127.0.0.1:8080/jenkins/api
  
  拷贝Job，添加参数name、 mode[copy] 、from
  http://127.0.0.1:8080/jenkins/createItem
  
  重启
  http://127.0.0.1:8080/jenkins/restart
  ```  
  
### 安全管理
  ```
  授权策略及其配置
  访问控制
    - 安全域即“认证”
    - 授权配置“户和/或组控制”
    - 矩阵授权策略
  跨站点请求伪造
    - 检查CSRF令牌
  ```
### 相关词汇
  
  ```
    Agent(机器或容器)、Artifact（不可变文件）、Build（构建）、Label（标签）、Master（主节点）、Node（pipeline执行机器）、Project（工程）
    Publisher（发布报告）、Stage（阶段）、Trigger（触发器）、Update Center（托管插件和插件元数据的库存）、Upstream（配置的Pipeline或项目）
  ```
