###### **my-news-master-ssr**
**一、项目介绍**
仿今日头条移动端简单版my-news-master-ssr基于vue框架，使用vue-cli3脚手架，实现了功能一、二。

将写好的vue-cli3项目平滑转为nuxt.js项目，对.eslintrc.js package.json等重新配置，修改路由等，实现了Vue SSR服务端渲染。
先编译 nuxt build,再启动服务器 nuxt start，nuxt generate 在dist文件夹内生成静态站点，
为了守护进程使用pm2,使用nginx进行负载均衡和反向代理，实现功能三。

使用webpack-bundle-analyzer可视化资源分析工具，需要在nuxt.config.js配置一下，npm run build --report生成分析报告，根据报告对项目进行优化。

将assets中的第三方插件文件以及不需编译的图片放到static中
配置sourceMap
一开始考虑开启gzip，但是本项目比较简单，开启gzip后cpu占用率过高，思考后觉得没必要。
第三方插件用CDN形式引入(未使用第三方插件)
按需引入相关插件模块
综上优化后DOMContentLoaded明显减小

**二、功能介绍**
实现搜索框、搜索结果页列表
实现swiper对搜索结果页tab横向切换
搭建node服务，实现静态页面部署，并实现服务端渲染
实现页面优化



