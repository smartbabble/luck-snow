### 简介
Gerrit实际上是一个Git服务器，它为在其服务器上托管的Git仓库提供一系列权限控制，


### 链接
http://60.205.93.190/gerrit/#/admin/projects/

### 记录
克隆并自动获取commit-msg钩子文件
仅克隆远程仓库commit后会产生Change-Id

### 打tag
git push origin refs/tags/{标签名}

### 冲突版本

### Change
Change一般配置成只有在Code-Review +2 以及Verified +1 的情况下才可以Submit
为了保证减少冲突和依赖,你也可以基于一个正在code review的Change开发新的feature
