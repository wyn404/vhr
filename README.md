# vhr

## 项目介绍

一个前后端分离的人力资源管理系统，项目采用SpringBoot+Vue开发。

### Demo



### 项目技术栈

##### 后端技术栈

1. Spring Boot
2. Spring Security
3. MySQL
4. Redis
5. MyBatis
6. ...

##### 前端技术栈

1. Vue
2. ElementUl
3. axios
4. vue-router
5. Vuex
6. ...

## 快速部署

1. clone项目到本地：`git clone git@github.com:wyn404/vhr.git`
2. 数据库脚本使用vhr.sql
3. 提前准备好Redis，在项目的`application.properties`文件，将Redis配置改为自己的
4. 运行vhrserver中的vhr-web模块

服务端就启动成功，此时在地址栏输入`http://localhost:8081/index.html`即可访问项目。

## 项目结构

```
vhr

|-- vhr-mapper                      
|  |-- HrMapper
|  |-- HrRoleMapper            
|  |-- MenuMapper
|  |-- MenuRoleMapper
|  |-- RoleMapper
|  \-- SysMsgMapper 

|-- vhr-model             
|  |-- Hr
|  |-- HrRole
|  |-- Menu 
|  |-- MenuRole 
|  |-- Meta
|  |-- RespBean
|  |-- Role
|  \-- SysMsg

|-- vhr-service             
|  |-- service
|  |  |-- HrService 
|  |  |-- MenuService  
|  |  \-- RoleService 
|  \-- utils
|  |  \-- HrUtils

|-- vhr-web             
|  |-- config
|  |  |-- FastDFSUtils
|  |  \-- LoginFilter 
|  |-- controller
|  |  |-- emp
|  |  |  \-- EmpBasicController
|  |  |-- HrInfoController 
|  |  |-- LoginController 
|  \-- VhrApplication

|  \-- resources
|  |  |-- static   
|  |  |-- application 
|  |  \-- fastdfs-client
```

