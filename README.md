# vhr

## 项目介绍

一个前后端分离的人力资源管理系统，项目采用SpringBoot+Vue开发。

### Demo

[![Watch the video](Watch the video)](https://user-images.githubusercontent.com/45954853/184365323-b04718a4-3ba0-48cd-b4e4-d8b9b555d362.mp4)

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
2. 数据库脚本使用`vhr.sql`
3. 提前准备好Redis，在项目的`application.properties`文件，将Redis配置改为自己的
4. 运行`vhr-web`模块

服务端就启动成功，此时在地址栏输入`http://localhost:8081/index.html`即可访问项目。

## 项目结构

```
vhr

|-- vhr-mapper                     数据访问访问层，与数据库连接
|  |-- DepartmentMapper            部门
|  |-- EmployeeMapper              员工基本信息
|  |-- HrMapper                    管理员
|  |-- HrRoleMapper                管理员角色
|  |-- JobLevelMapper              职称  
|  |-- MenuMapper                  菜单
|  |-- MenuRoleMapper              菜单角色
|  |-- Nation                      民族
|  |-- PoliticsstatusMapper        政治面貌
|  |-- PositionMapper              职位
|  |-- RoleMapper                  角色
|  |-- SalaryMapper                工资
|  \-- SysMsgMapper                系统消息

|-- vhr-model                      实体类
|  |-- CharMsg                     在线聊天
|  |-- Department                  部门
|  |-- Employee                    员工基本信息
|  |-- Hr                          管理员信息
|  |-- HrRole                      管理员角色对应关系
|  |-- JobLevel                    职称
|  |-- Menu                        菜单
|  |-- MenuRole                    菜单角色对应关系
|  |-- Meta                        管理员权限
|  |-- Nation                      民族
|  |-- Politicsstatus              政治面貌
|  |-- Position                    职位
|  |-- RespBean                    响应bean，返回操作状态
|  |-- RespPageBean                根据页面显示数据
|  |-- Role                        角色
|  |-- Salary                      工资
|  \-- SysMsg                      系统消息

|-- vhr-service                    业务逻辑层
|  |-- service
|  |  |-- DepartmentService        部门的显示，添加等
|  |  |-- EmployeeService          员工信息过多，按页数显示数据
|  |  |-- HrService                管理员的权限，获取管理员的数量
|  |  |-- JobLevelService          职称信息
|  |  |-- MenuService              根据管理员权限显示菜单
|  |  |-- NationService            民族信息
|  |  |-- PoliticsstatusService    政治面貌信息
|  |  |-- PositionService          职位信息
|  |  |-- RoleService              根据SpringSecurity将角色开头添加ROLE_
|  |  \-- SalaryService            工资信息
|  \-- utils
|  |  \-- HrUtils                  获取当前用户登录的用户信息

|-- vhr-web                        控制层
|  |-- config
|  |  |-- CustomFilter...Source    调用安全元数据源的过滤器，设置ROLE_开头
|  |  |-- CustomUrl...Manager      URL决策管理器，判断用户权限
|  |  |-- LoginFilter              登录过滤器，查看用户是否有权限登录
|  |  |-- SecurityConfig           web安全配置适配器，多端登录下线Q
|  |  |-- VerificationCode         登录验证码
|  |  \-- WebSocketConfig          web-socket消息代理配置器
|  |-- controller
|  |  |-- config
|  |  |  \-- System...Controller    根据用户权限获取菜单
|  |  |-- emp
|  |  |  \-- EmpBasicController     员工信息的增删改查等
|  |  |-- system
|  |  |  |-- basic
|  |  |  |  \-- PermissController   员工信息许可
|  |  |  \-- HrController           管理员操作
|  |  |-- ChatController            获取通讯录名单
|  |  |-- HrInfoController          管理员信息管理
|  |  |-- LoginController           登录控制器，获取后端验证码，用户是否登录
|  |  \-- WsController              聊天对象发送
|  |-- VhrApplication               应用程序启动入口
|  \-- resources
|  |  |-- static                    前端npm run build后的文件
|  |  \-- application               MySQL、redis的端口配置
```

