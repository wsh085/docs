# 敏感词交接文档

> 提供敏感词交接文档记录，方便交接人查看

## 敏感词包含范围

* 旧敏感词管理后台
* 新敏感词管理后台
* 敏感词SDK

## 答疑联系人

* 郑美双 917520 （web前端）
* 黄永鑫 102210 （新版敏感词案子主程）
* 卢鑫 103600 （服务端）

## 组件项目说明

* [技术货架颗粒信息](https://ts.101.com/#/shelvesDetail?id=e71ea78c-7ea6-462e-9dc2-a03418007912)
* [新版敏感词设计原型](http://demo.doc.101.com/%E5%85%B1%E4%BA%AB%E5%B9%B3%E5%8F%B0/%E3%80%90ND12795%E3%80%91%E5%85%B1%E4%BA%AB%E5%B9%B3%E5%8F%B0-%E6%95%8F%E6%84%9F%E5%AD%97%E5%B1%8F%E8%94%BD%E7%BA%A7%E5%88%AB%E8%AE%BE%E8%AE%A1%EF%BC%88%E9%9D%9E%E6%B8%B8%E6%88%8F%EF%BC%89/)

### 项目启动说明

#### 旧敏感词管理台

* 用的框架和`Social管理台`一样，可参照 `Social管理台`

#### 新敏感词管理后台

* [FishPro框架文档](https://www.yuque.com/gem-mine/fish-pro)
* `npm install`
* `npm start`

#### 敏感词SDK

* [敏感词检测算法说明](https://note.youdao.com/ynoteshare1/index.html?id=f1026ffb98a93b1e6a3a526d47312435&type=note)

* [敏感词测试用例](https://note.youdao.com/ynoteshare1/index.html?id=64015724829aa186cad985b2af28fac3&type=note)

* [DFA 算法介绍](https://blog.csdn.net/weixin_43378396/article/details/105910145)

* 执行单元测试 `npm run test`

### 项目调试说明

* 正常使用 chrome devtools 工具开发调试

### 项目开发注意事项

* 无

### 项目发布注意事项

* 无，正常发布即可

## 开发经验总结及其他注意事项

* 新敏感词管理后台有接入聚合后台，具体方法可参照Social管理台

* 新敏感词管理后台有接入聚合后台，运维的权限是卢鑫那边添加，产品的权限是通过rbac权限判断

* 敏感词SDK 是否考虑内置请求库，不需要外部传request？

## 常见FAQ

* Q：敏感词SDK `new` 的时候报错了，原因是什么？

* A：可能原因是传入的request问题，request必须支持 request.get({...}) 或者 request({method, ...}) 这种调用

* Q：开通了敏感词服务，为什么聚合后台看不到菜单？

* A：需要开启RBAC，并配置权限
