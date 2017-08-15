
# webpack
## 1.webpack简单入门
### 如何安装webpack
1.使用npm全局安装  
  
`npm install webpack -g `  
  
  
2.使用vue-cli直接生成一个完整的webpack项目  
  
`vue init webpack `
  
    
 ### webpack是什么?
   
 webpack是一个 __模块加载工具/打包工具__
 
![webpack](http://webpack.github.io/assets/what-is-webpack.png "webpack")
 ### 什么是 webpack-dev-server  
   ` npm install webpack-dev-server -g `
 webpack-dev-server 是一个轻量级的热重载(修改文件源码后,自动刷新页面同步) __Node服务器__
   
 
   
### vue-cli的目录结构
项目结构
|-- build                            // 项目构建(webpack)相关代码  
|   |-- build.js                     // 生产环境构建代码  
|   |-- check-version.js             // 检查node、npm等版本  
|   |-- dev-client.js                // 热重载相关  
|   |-- dev-server.js                // 构建热加载本地服务器  
|   |-- utils.js                     // 构建工具相关  
|   |-- webpack.base.conf.js         // webpack基础配置  
|   |-- webpack.dev.conf.js          // webpack开发环境配置  
|   |-- webpack.prod.conf.js         // webpack生产环境配置  
|-- config                           // 项目开发环境配置  
|   |-- dev.env.js                   // 开发环境变量   
|   |-- index.js                     // 项目一些配置变量   
|   |-- prod.env.js                  // 生产环境变量   
|   |-- test.env.js                  // 测试环境变量    
|-- src                              // 源码目录    
|   |-- components                     // vue公共组件  
|   |-- store                          // vuex的状态管理  
|   |-- App.vue                        // 页面入口文件  
|   |-- main.js                        // 程序入口文件，加载各种公共组件  
|-- static                           // 静态文件，比如一些图片，json数据等  
|   |-- data                           // 群聊分析得到的数据用于数据可视化  
|-- .babelrc                         // ES6语法编译配置  
|-- .editorconfig                    // 定义代码格式  
|-- .gitignore                       // git上传需要忽略的文件格式  
|-- README.md                        // 项目说明  
|-- favicon.ico   
|-- index.html                       // 入口页面  
|-- package.json                     // 项目基本信息  
  
   
#### 如何去安装一个webpack插件(webpack加载器)
  
`npm install css-loader --save-dev`
  
  
### HTML WebPack Plugin  
   
  简单介绍  
   
这是一个Webpack插件,可以简化HTML文件的创建,即在打包过程中将依赖直接注入HTML文本  
  
  `npm install html-webpack-plugin --save-dev`  
    
[官方说明文档](https://github.com/jantimon/html-webpack-plugin)   
  
  
  ### Webpack Hot Middleware
  
    简单介绍   
   
这是一个Webpack插件,用于热重载  
  
  `npm install webpack-hot-middleware --save-dev`  
    
[官方说明文档](https://github.com/glenjamin/webpack-hot-middleware#installation--usage)   
  
  
  #### 如何配置webpack 基础配置文件 webpack.base.conf.js  

 ```Javascript
 module.exports = {  
  entry: {  
    app: './src/main.js'  //entry 指定页面入口文件  
  },  
  output: {  
    path: config.build.assetsRoot,//输出结果储存到哪里  
    filename: '[name].js',  
    publicPath: process.env.NODE_ENV === 'production'  
      ? config.build.assetsPublicPath  
      : config.dev.assetsPublicPath  
  },  
  resolve: {  //模块解析
    extensions: ['.js', '.vue', '.json'], //关联的后缀名 用于模块查找  
    alias: {        
      'vue$': 'vue/dist/vue.esm.js',  
      '@': resolve('src'),  
      'assets': path.resolve(__dirname, '../src/assets')  
      // 'jquery': 'jquery/dist/jquery.min.js'  用于设置别名,简化import路径  
    }, 
    plugins: [] //添加插件
  }
```  
  
  
  

