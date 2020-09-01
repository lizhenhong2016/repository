# 在vue.js框架安装,npm安装less和less-loadernpm或者stylus和stylus-loader

vue-cli 构建的项目默认是不支持 less 的，需要自己添加。

首选，安装 less 和 less-loader ，在项目目录下的这个文件下安装**node\_modules**运行如下命令

npm install less less-loader --save-dev

安装成功后，可以先写一个less样式看看生效没。如果没生效打开build/webpack.base.conf.js，在module.exports =的对象的 module.rules 后面添加一段

module.exports = {

 // 此处省略无数行，已有的的其他的内容

 module: {

 rules: \[

 // 此处省略无数行，已有的的其他的规则

 {

 test: /\.less$/,

 loader: "style-loader!css-loader!less-loader",

 }

 \]

 }

}

最后，在代码中的 style 标签中 加上lang="less"属性即可~

&lt;style lang="less"&gt;里面写less样式  
  
&lt;/style&gt;

 引入less样式&lt;style lang="less" src="./styles.less"&gt;&lt;/style&gt;

  


  


作者：醉枫々染墨

  


链接：https://www.jianshu.com/p/4ecdec613e47

  


来源：简书

  


著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



