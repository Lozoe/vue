# my-first-vue-project

> This is a vue.js practice project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```
# vuejs

#### 环境搭建
```bash
1. 使用npm 或者cnpm（https://npm.taobao.org/）包管理器
eg.   npm install -g cnpm --registry=https://registry.npm.taobao.org
2. 安装vue和template(例如webpack or browserify)
# 全局安装 vue-cli
$ sudo cnpm install -g vue-cli
# 全局安装 webpack
$ sudo cnpm install -g webpack
```
#### 初始化项目
```bash
# 创建一个基于 webpack 模板的新项目
$  sudo vue init webpack my-first-vue-project
# 安装依赖
$ cd my-project
$ npm install
# 开启服务，浏览器访问项目 http://localhost:8080
$ npm run dev
```
#### 自定义事件
```bash
# $on() 监听事件
# $emit()  出发事件
# $dispatch() 派发事件，事件沿着父链冒泡 events
# $broadcast() 广播事件，事件向下传导给所有后代 events
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

