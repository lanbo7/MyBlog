---
title: webpack学习
date: '2023-04-18'
tags: ['webpack']
summary:
---
<TOCInline toc={props.toc} exclude="Overview" toHeading={3} /> 
# 首先我们可以进入项目，先执行npm init -y 命令
然后就可以在项目上见到package.json文件，

```json
{
  "name": "demo_01",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "devDependencies": {
    "@babel/core": "^7.20.5",
    "@babel/preset-env": "^7.20.2",
    "babel-loader": "^9.1.0",
    "html-webpack-plugin": "^5.5.0",
    "webpack": "^5.75.0",
    "webpack-cli": "^5.0.0",
    "webpack-dev-server": "^4.11.1",
    "css-loader": "^6.7.2",
    "style-loader": "^3.3.1"
  },
  "scripts": {
    "build": "webpack",
    "watch": "webpack --watch",
    "dev": "webpack serve --open"
  },
  "dependencies": {
    "jquery": "^3.6.4"
  },
  "browserslist": [
    "defaults"
]
}
```
## 随后执行 yarn install 或者 npm install 命令下载package.json中指定的依赖

### 下面创建 webpack.config.js文件(配置文件) 注意：由于webpack是基于node开发，所以引入依赖符合commonjs规范，也就是使用require关键字
```javascript
const path = require("path")
// 引入html插件
const HTMLPlugin = require("html-webpack-plugin")

module.exports = {
    mode: "development", // 设置打包的模式，production表示生产模式  development 开发模式
    // entry: "./hello/hello.js", // 用来指定打包时的主文件 默认 ./src/index.js
    // entry: ["./src/a.js", "./src/b.js"],
    // entry: {
    //     a: "./src/a.js",
    //     b: "./src/b.js"
    // },
    // entry: "./src/a.js",

    output: {
        // path: path.resolve(__dirname, "dist"), // 指定打包的目录，必须要绝对路径
        // filename: "main.js", // 打包后的文件名
        // filename:"[name]-[id]-[hash].js",
        clean: true // 自动清理打包目录
    }, // 配置代码打包后的地址
    /* 
    webpack默认情况下，只会处理js文件，如果我们希望它可以处理其他类型的文件，则要为其引入loader

    - 以css为例：
        - 使用css-loader可以处理js中的样式
        - 使用步骤：
            1.安装：yarn add css-loader -D
            2.配置：
                module: {
                    rules: [
                        {
                            test: /\.css$/i,
                            use: "css-loader"
                        }
                    ]
                }
*/
    module: {
        rules: [
            {
                test: /\.css$/i,
                use: ["style-loader", "css-loader"]
            },
            {
                test: /\.(jpg|png|gif)$/i,
                type: "asset/resource" // 图片直接资源类型的数据，可以通过指定type来处理
            },
            {
                test: /\.m?js$/,
                exclude: /(node_modules|bower_components)/,
                use: {
                    loader: "babel-loader",
                    options: {
                        presets: ["@babel/preset-env"]
                    }
                }
            }
        ]
    },

    plugins: [
        new HTMLPlugin({
            // title: "Hello Webpack",
            template: "./src/index.html"
        })
    ],

    devtool: "inline-source-map"
}
```
## 以下是如何引用项目中的样式以及静态资源（图片等）

````javascript
import './style/index.css'
import An from './assets/an.jpg'
import Fpx from './assets/timg.jpg'
document.body.insertAdjacentHTML("beforeend","<h1>今天天气还不错，风才12级</h1>")
document.body.insertAdjacentHTML(
    "beforeend",`<img src="${An}"/>` 
)
document.body.insertAdjacentHTML(
    "beforeend",`<img src="${Fpx}"/>` 
)
````
