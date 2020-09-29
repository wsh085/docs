# 新闻组件交接文档

> 提供新闻组件交接文档记录，方便交接人查看

## 新闻组件包含范围

* 旧新闻Web端 （news-web）
* 新闻聚合插件（fish3.x）（news）
* 新闻聚合插件（fish2.x）（newsfish2）
* 新闻聚合插件H5（fish3.x）（news）
* 新闻聚合站游客访问页面

## 答疑联系人

* 郑美双 917520 （web前端）
* 倪丹 317036（测试同学）
* 何承栋 423233 （新闻服务端）
* 周颖 901425（互动服务端）
* 陈威 666551（聚合站开发）

## 组件项目说明

* [Wiki](http://wiki.sdp.nd/index.php?title=%E6%96%B0%E9%97%BB_%E6%96%B0)

### 项目启动说明

* 旧新闻Web端 （news-web）

  * `npm install`

  * `npm start`

* 新闻聚合插件

  * [web聚合站点快速开发指引](http://reference.doc.101.com/appfactory/pagecompose/guide/widget/begin.html)

### 项目调试说明

* 正常使用 chrome devtools 工具开发调试

* 旧新闻Web （news-web）断点调试线上项目（常有这个需求）:

  * 安装 Fillder 代理，并设置好 AutoResponder 的地址映射，如：

    * `regex:http://edu.e.101.com/news/$`  &nbsp;&nbsp;&nbsp;   `http://192.168.253.80:3030/`

    * `regex:http://edu.e.101.com/news/((?!v0\.).*)` &nbsp;&nbsp;&nbsp;  `http://192.168.253.80:3030/$1`

  * 修改本地项目启动的环境，`src/contants/config.js` 文件里将 `process.env.NODE_ENV` 改为对应环境名

  * 项目中添加 `debugger` 进行调试

### 项目开发注意事项

* [聚合站组件升级UC1.1方案](http://note.youdao.com/noteshare?id=5ca7a7bd14b024182ccbb3ed133be28e)

### 项目发布注意事项

* 无

## 开发经验总结及其他注意事项

* 新闻发布审核案子中，erp表单有查看新闻详情的链接，这个链接的地址由之前的开发 金敏健 使用自己的手机号在拼装门户那边创建的应用，会给后续开发带来隐患，需要安排转移到一组官方账号下。金敏健的账号：13774578573 / 123456 应用名：别动我自己的新闻

## 常见FAQ

* Q：聚合站新闻web目前有较多的控件配置，有哪些是属于新闻聚合项目维护的？

* A：新闻聚合站web 目前包含 列表、详情、分享、点赞、收藏 控件，其他均使用公共控件

* Q：聚合站新闻web有常用的测试账号？

* A：http://portal-app.beta.101.com/#/login &nbsp;&nbsp;&nbsp;  15080310652 / nd123456 &nbsp;&nbsp;&nbsp; 新闻互动验证

* Q：教育那边接入旧新闻web可以根据传入的`tenant_code`参数来自定义头尾部，这部分代码在哪里？

* A：自定义头尾部的实现逻辑是：url上带有`tenant_code`则去请求头尾部配置，请求的域名可在项目全局里搜`customWebPortalService`，然后通过解析请求回来的内容，将`html`、`css`、`js`脚本挂到页面上。替换头尾部`news-web\src\main\js\src\components\layout`，解析内容`news-web\src\main\js\src\utils`
