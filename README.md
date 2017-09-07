# react
photo base on react
#react+webpack开发

1.webpack环境搭建
  链接   https://doc.webpack-china.org/guides/development
  
  环境搭建须知：
  
              1/基于node.js,npm         
               2/webpack全局安装          npm install webpack -g
                3/webpack前端服务器搭建    npm install --save-dev webpack-dev-server 
                
2.react.js添加
    npm install --save-dev react react-dom   //react.js

    npm install --save-dev babel-core babel-loader  babel-preset-es2015 babel-preset-react  // es6转换依赖安装

    npm install --save-dev style-loader css-loader sass-loader url-loader             //资源加载依赖
3.webpack下react环境配置

     文件说明
     
        webpack.commom.js(基本配置文件) webpack.dev.js(开发环境配置：添加错误追踪等工具) webpack.prod.js(生产环境配置:cheap-module-source-map)
        
     webpack.commom.js下配置react.js
     
        module: {
        loaders: [
            {
                test: /\.js?$/,
                exclude: /(node_modules|bower_components)/,
                loader: 'babel',
                query: {
                    presets: ['es2015', 'react']
                } //将react编译成js文件
            },
            { test: /\.css$/, loader: 'style-loader!css-loader' }, 
            //打包css文件
            { test: /\.scss$/, loader: 'style!css!sass?sourceMap'}, 
            //编译sass文件
            { test: /\.(png|jpg)$/, loader: 'url-loader?limit=8192'} 
            //对图片进行打包
        ]
    }
    
4.启动

   #npm istall 安装依赖
   
   #npm run build  编译代码
   
   #npm start    启动窗口
