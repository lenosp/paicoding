quick-forum
---

社区工程原型

## 结构说明

- forum-web: Web前端入口，包括权限身份校验、全局异常处理等
- forum-ui：前端资源包
- forum-service: 核心的服务包，db操作，服务封装在这里
- forum-core: 通用模块，如工具包util， 如通用的组件放在这个模块（以包路径对模块功能进行拆分，如搜索、缓存、推荐等）

## 本地部署教程

> [本地开发环境手把手教程](docs/本地开发环境配置教程.md)

## 云服务器部署教程

> [环境搭建 & 基于源码的部署教程](docs/安装环境.md)

## todo

1. 权限限制（包括菜单权限）

- controller 很多接口，有一些是需要登录的，要有校验
    - @Auth(role = "login")
    - @AUth(role = "admin")

2. 文章阅读之后，各种计数、 评论目前还没有串起来 @楼仔

- 第一版mysql
- 第二版mongodb
- 第三版redis

3. 用户登录、登出 （不存在用户注销） @一灰

- 个人公众号登录，只能拿到uuid，拿不到用户信息(用户名 + 头像) --》 随机分配一个，头像用户名，跳转用户详情
- 扫公众号二维码，关注之后，输入 “关键词”， 我们返回一串 数字， 然后在登录界面输入数字之后，登录

5. 图片上传 -- 需要一个独立的图片上传接口 （直接使用七牛云的oss） --> @楼仔
6. 搜索  `一期可以考虑使用db的like语法` @楼仔
- 第一版mysql
- 第二版es


7. 消息模块
8. 文章排序规则（目前只提供了按照时间的排序，后续需要添加热度、xxx排序）@一灰
9. 公告侧边栏：先整一个写死的几个板块 @一灰
10. admin后台 -- 先设计（前后端分离）
11. 添加文章时，自动保存，历史版本
12. 定时发布 --> 定时任务 + 时间轮 + 延迟消息 
13. 评论前端页面