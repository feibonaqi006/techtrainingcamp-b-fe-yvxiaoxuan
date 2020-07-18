# my-news-master-ssr
## 一、项目介绍
仿今日头条移动端简单版my-news-master-ssr基于vue框架，使用**vue-cli3**脚手架。

将写好的vue-cli3项目平滑转为**nuxt.js**项目，对.eslintrc.js package.json等重新配置，修改路由等，实现了Vue SSR服务端渲染。
先编译 `nuxt build`,再启动服务器 `nuxt start`，`nuxt generate` 在dist文件夹内生成静态站点，
为了守护进程使用**pm2**,使用**nginx**进行负载均衡和反向代理。

使用**webpack-bundle-analyzer**可视化资源分析工具，需要在nuxt.config.js配置一下，`npm run build --report`生成分析报告，根据报告对项目进行优化。
* 将assets中的第三方插件文件以及不需编译的图片放到static中
* 配置sourceMap
* 一开始考虑开启gzip，但是本项目比较简单，开启gzip后cpu占用率过高，思考后觉得没必要。
* 第三方插件用CDN形式引入(未使用第三方插件)
* 按需引入相关插件模块
> 综上优化后 DOMContentLoaded 明显减小

## 二、功能介绍
* 实现搜索框、搜索结果页列表
* 实现swiper对搜索结果页tab横向切换
* 搭建node服务，实现静态页面部署，并实现服务端渲染
* 实现页面优化



