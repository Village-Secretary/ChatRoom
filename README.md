<font face="仿宋">

# **多人聊天室项目**

## **项目介绍**：

该项目的核心功能为让用户使用浏览器访问主界面进行多用户实时通讯。

---

## **多人聊天室项目具体功能**：

- 登录注册
- 添加好友
- 私聊
- 群聊
- 文本传输
- 图片、小文件传输
- 表情包

---

**前端语言**：JavaScript, HTML, CSS  
**后端语言**：JavaScript(node.js)  
**客户端**：Microsoft Edge浏览器  
**服务器**：阿里云服务器  
**数据库**：MySql  
**数据传输**：Json数据格式

---

## **需要了解的东西有**：
1. JavaScript
2. HTML
3. CSS
4. 服务器和客户端相关知识
5. HTTP，Socket等网络相关
6. UI设计
7. Github基本操作及多人协同开发相关知识
8. MySql数据库
9. Json数据格式
10. 云服务器搭建及项目部署

---

## **项目参考案例**：
https://fiora.suisuijiang.com/

---

## **开发相关知识文档及视频**：

**文档：**  
- [JavaScript][1][现代 JavaScript 教程](https://zh.javascript.info/)
- [服务器搭建和项目部署][2][把Node.js项目部署到阿里云服务器（CentOs）](https://segmentfault.com/a/1190000004051670)
- [聊天室入门教程][1][从0开始用Nodejs做一个聊天室](https://www.jianshu.com/p/b608a765519a)

**视频：**  
- [JavaScript][2][快速入门NodeJS之【搭建Web服务器】](https://www.bilibili.com/video/BV1KX4y1K7uz?spm_id_from=333.999.0.0)
- [Github][1][Github 新手够用指南 | 全程演示&个人找项目技巧放送](https://www.bilibili.com/video/BV1e541137Tc?spm_id_from=333.999.0.0)
- [Github][2][40 分钟学会 Git | 日常开发全程大放送&搭配Github](https://www.bilibili.com/video/BV1db4y1d79C?spm_id_from=333.999.0.0)
- [服务器搭建和项目部署][1][在家没事干？10分钟拥有真正意义上属于自己的网站！网站搭建！](https://www.bilibili.com/video/BV1D7411B7Yf/?spm_id_from=333.788.recommend_more_video.-1)

---

## **多人聊天室功能模块分析及任务分工：**

### **模块分析**：


**后端：**
- 数据管理模块
  - 数据库数据管理 
- 信息请求模块
- 请求处理模块
- 信息推送模块

**前端：**
- 登录界面模块
- 聊天主界面模块
- 数据管理模块
  - 内存数据结构管理
  - 本地静态数据管理(本地json文件)
- 信息请求模块
- 请求处理模块

### **任务分工**：

**前端**

- [ ] 登录注册界面的UI设计 <font color=#fb4551>叮当猫</font>
- [ ] 聊天主界面的UI设计  <font color=#fb4551>叮当猫</font>
- [ ] 登录注册界面的UI前端实现 <font color=#fb4551>叮当猫</font>
- [ ] 聊天主界面的UI的前端实现  <font color=#fb4551>叮当猫</font>
- [ ] ...

**后端**

- [ ] 云服务器搭建及项目环境配置 <font color=#97e1f1>抹茶加冰</font>
- [ ] 数据库的设计和建表 <font color=#97e1f1>抹茶加冰</font>
- [ ] ...

---

## **模块设计**

### **数据结构设计：**

- **用户信息[UserInfo]**

|   字段   |   含义   |   类型   |   备注   |  
|----------|----------|---------|----------|
| id | 账户 | 字符串 |
| password | 密码 | 字符串 |
| name | 昵称 | 字符串 |
| email | 邮箱 | 字符串 |
| avatar | 头像 | 字符串 | 存储图片路径 |
| self_introduction | 个人介绍 | 字符串 | 


- **聊天信息[ChatMessage]**

|   字段   |   含义   |   类型   |   备注   |  
|----------|----------|---------|----------|
| send_id | 发送账号 | 字符串 |
| recv_id | 接受账号 | 字符串 |
| type | 信息类型 | 枚举 | 用来标注聊天信息类型，如：私聊、群聊等
| message | 信息 | 字符串 | 存储聊天内容或是存储图片、文件路径 |
| send_time | 发送时间 | 整数 | 


- **请求信息[RequestInformation]**

|   字段   |   含义   |   类型   |   备注   |  
|----------|----------|---------|----------|
| send_id | 发送账号 | 字符串 |
| recv_id | 接受账号 | 字符串 |
| type | 类型 | 枚举 |
| message | 请求附带信息 | 字符串 |


### **数据库建表：**

- **关系模式：**  

>UserInfo(id, password, name, email, avatar, self_introduction)  
关系依赖:  { id -> email, email -> id, id -> password, id -> name, id -> avatar, id -> self_introduction }  
候选码: (id), (email)  

>ChatMessage(chat_id, send_id, recv_id, type, message, send_time)  
关系依赖:  { chat_id -> send_id, chat_id -> recv_id, chat_id -> type,chat_id -> message, chat_id -> send_time }  
候选码: (chat_id)  

>RequestInformation(request_id, send_id, recv_id, type, message)  
关系依赖:  { request_id -> send_id, request_id -> recv_id, request_id -> type, request_id -> message }  
候选码: (request_id)

- **范式：**
- [x] 符合第一范式
- [x] 符合第二范式
- [x] 符合第三范式
- [x] 符合第BC范式



</font>