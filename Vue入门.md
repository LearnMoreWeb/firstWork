## Vue入门

### 1. 介绍

#### 1.1 MVVM

#### 1.2 第一个实例



### 2. vue安装

#### npm

> node安装
>
> npm安装
>
> cnpm安装

`cnpm install vue`

#### 	vue-cli

 	> 全局安装 vue-cli

`cnpm install --global vue-cli`

> 创建基于 `webpack` 模板的项目

`vue init webpack my-project`

#### webpack

##### 简介

> *webpack* 是一个现代 JavaScript 应用程序的*静态模块打包器(module bundler)*

##### 入口

```javascript
module.exports = {
  entry: './path/to/my/entry/file.js'
};
```

##### 出口

````
const path = require('path');

module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  }
};

````

##### loader

> *loader* 让 webpack 能够去处理那些非 JavaScript 文件（webpack 自身只理解 JavaScript）。loader 可以将所有类型的文件转换为 webpack 能够处理的有效[模块](https://www.webpackjs.com/concepts/modules)，然后你就可以利用 webpack 的打包能力，对它们进行处理

##### 插件（plugins）

```
const HtmlWebpackPlugin = require('html-webpack-plugin'); // 通过 npm 安装
const webpack = require('webpack'); // 用于访问内置插件
const path = require('path');

const config = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  },
  plugins: [
    new webpack.optimize.UglifyJsPlugin(),
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};

module.exports = config;

```



### 3. 目录结构

| 目录/文件        | 说明                                       |
| ------------ | ---------------------------------------- |
| build        | 项目构建(webpack)相关代码                        |
| config       | 配置目录，包括端口号等。我们初学可以使用默认的。                 |
| node_modules | npm 加载的项目依赖模块                            |
| src          | 这里是我们要开发的目录，基本上要做的事情都在这个目录里。里面包含了几个目录及文件：assets: 放置一些图片，如logo等。components: 目录里面放了一个组件文件，可以不用。App.vue: 项目入口文件，我们也可以直接将组件写这里，而不使用 components 目录。main.js: 项目的核心文件。 |
| static       | 静态资源目录，如图片、字体等。                          |
| test         | 初始测试目录，可删除                               |
| .xxxx文件      | 这些是一些配置文件，包括语法配置，git配置等。                 |
| index.html   | 首页入口文件，你可以添加一些 meta 信息或统计代码啥的。           |
| package.json | 项目配置文件。                                  |
| README.md    | 项目的说明文档，markdown 格式                      |

### 4. 正式开始

#### 1. 指令

- v-text	{{}}
- v-html
- v-show
- v-if
- v-else
- v-if-else
- v-for
- v-on
- v-bind        :
- v-model
- v-pre
- v-cloak
- v-once

#### 2. 选项/数据

- data

- props

- computed

  > 计算属性的结果会被缓存，除非依赖的响应式属性变化才会重新计算。注意，如果某个依赖 (比如非响应式属性) 在该实例范畴之外，则计算属性是**不会**被更新的。

- methods

- watch

#### 3. 全局 API

- nextTick()

  > 你在Vue生命周期的`created()`钩子函数进行的DOM操作一定要放在`Vue.nextTick()`的回调函数中。（或者使用`mounted`钩子函数）

  > 在数据变化后要执行的`某个操作`，而这个`操作`需要使用随数据改变而改变的DOM结构的时候，这个`操作`都应该放进`Vue.nextTick()`的回调函数中。

#### 4. 生命周期

- created()
- mounted()
- activated()![Vue 实例生命周期](https://cn.vuejs.org/images/lifecycle.png)

#### 5. 实例属性/方法/事件

- vm.$refs
- vm.$emit()

#### 6. 特殊属性

- key
- ref
- slot
- scope

### 5. Vue全家桶

#### 1. vue-cli

> 构建工具

#### 2. vue-router

> 路由

####3. vuex

> 状态管理工具

#### 4. axios

> http请求包