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
源码管理
  - Github
  - GitLab
  - Gerrit
  - Subversion
构建触发器
  - crontab时间
  - 实现Gerrit event 触发Jenkins构建
  - Pull requests触发Jenkins构建
  - Merge Request等相关事件触发Jenkins构建
  - 支持在Jira issue的状态等变化时触发Jenkins构建
构建通知
  - Email Extension
  - Mailer
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
    - LDAP
    - 安全域即“认证”
    - 授权配置“户和/或组控制”
    - 矩阵授权策略
  跨站点请求伪造
    - 检查CSRF令牌
  ```
  
### 应用场景
```
  持续、自动地构建/测试软件项目
  监控一些定时执行的任务
  
  案例：
    -  企业级Jenkins之数据备份方案
       Jenkins基于文件系统的,配置和数据都存储在文件系统上,Jenkins Home目录的数据备份和恢复方案是Jenkins运维保障.
        - Jenkins Backup 插件进行备份
        - 基于Rsync工具将 Jenkins 数据同步到远程服务器进行备份
        - 使用Git工具时,通过.gitignore文件过滤掉无须备份的文件
    - 企业级Jenkins之精细化权限管理
      Role Strategy Plugin插件维护者、配置管理员、研发/测试用户的权限隔离与控制
      集成LDAP实现用户统一认证与用户组管理
      Job 规范化管理
    - 企业级Jenkins之精准化通知
      邮件发送
      日志解析
      快速定位问题，通知问题当事人
    - 资源消耗较大
      持续集成、质量门等实践
      实现多层质量门禁
      包括提交验证
      代码准入
      制品升级等
      将代码提交到Gerrit中-----手动执行预编译任务------冒烟测试-----自动化预编译结果也会回写到Gerrit中以便进行Code Review-------持续构建每天会运行12次------推送到生产制品库-------可用性测试
      
```
### 相关词汇
  
  ```
    Agent(机器或容器)、Artifact（不可变文件）、Build（构建）、Label（标签）、Master（主节点）、Node（pipeline执行机器）、Project（工程）
    Publisher（发布报告）、Stage（阶段）、Trigger（触发器）、Update Center（托管插件和插件元数据的库存）、Upstream（配置的Pipeline或项目）
  ```
