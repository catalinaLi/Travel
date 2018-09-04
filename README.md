# Travel(A learning front-end Vue.js project)

## 前端演进过程

关于前端开发的演进过程大家可以看这一篇文章[萌新也能懂的现代 JavaScript 开发](https://zhuanlan.zhihu.com/p/31044340)

对于现代前端开发工具进行一个简单的总结：

- webpack模块打包工具
	把整个的 moment.min.js 文件下载到 HTML 中，定义了一个全局变量 moment，对于所有在 moment.min.js 之后下载的文件都可用（无论是否真的需要它）。

- babel用于编写下一代 JavaScript 的编译器
	把下一代的 JavaScript 中还未在所有浏览器实现的新特性（ES6 和之后）编译成更早更兼容的 JavaScript( ES5) 。

- npm包管理工具
	跟踪依赖项和版本、自动构建工具执行npm脚本包括最小化代码文件、优化图片、运行测试。

## 移动端开发注意事项

- 设置<meta>固定设备比禁止双手放大

``` JavaScript
<meta name="viewport" 
      content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">
```

- 移动端点击（click）事件延迟问题
	1.使用`npm install fastclick --save`安装fastclick.js
	2.在main.js中引入fastclick
		import fastClick from 'fastclick'
	3.在main.js使用fastclick
		fastClick.attach(document)

- 初始化移动端不同手机样式不同的问题
	引入reset.css

- 移动端解决1像素边框在多倍屏显示成多像素问题
	引入border.css

## Stylus

### Stylus的安装

1. 使用`npm install stylus --save`进行依赖包安装
2. 使用`npm install stylus-loader --save`进行依赖包安装

### Stylus的使用

在要使用的<styles/>标签里添加lang属性值为stylus,如果想让stylus只在当前组件生效则需再添加一个scope属性

``` Css
<style lang='stylus' scoped>
</style>

```

### Stylus变量的使用
我们可以新建一个varibles.styl的文件，在其中使用$定义变量，例如项目中的`$bgColor = #00bcd4`

如果使用这个变量则需要先引入，例如：
```
  @import '~styles/varibles.styl'
```

然后就可以使用了:`background: $bgColor`

## flex布局
flex布局可以参考[Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

## rem自适应布局

我们可以简单的看一下这篇文章[rem自适应布局的回顾总结](https://www.cnblogs.com/doseoer/p/5621923.html)

rem是根据html的font-size大小来变化,在我们这个项目中的reset.css中设置了html的font-size为50px。

## iconfont的使用
关于字体图标我们可以使用阿里[iconfont官网](http://www.iconfont.cn/home/index)提供的。使用方法如下：

1. 挑选心仪的字体图标并下载
2. 将字体文件和css整合到项目中，需要注意的是如果css和字体文件位置不在一起需要修改iconfont.css中的url的字体文件的位置
3. 在代码中通过span标签使用字体图标

```
<!-- &#xe632;是通过官网复制字体图标代码 -->
<span class="iconfont">&#xe632;</span>
```
## webpack的使用
- 添加路径变量
    在`webpack.base.conf.js`文件中的`resolve`中的alias定义路径变量
    ```
      resolve: {
        extensions: ['.js', '.vue', '.json'],
        alias: {
          'vue$': 'vue/dist/vue.esm.js',
          '@': resolve('src'),
          'styles': resolve('src/assets/styles'),
        }
      }
    ```

## Sublime快捷键

```
  Ctrl+Enter                将光标移到当前行的下一行
  Ctrl+Shift+Enter          将光标移到当前行的下一行
  Ctrl+Shift+Ente           在上一行插入新行
  Ctrl+Shift+D              复制光标所在整行，插入到下一行
  Ctrl+Shift+↓              将光标所在行插入到下一行之后
  Ctrl+Shift+K              删除当前行
  Ctrl+PageDown             向左切换当前窗口的标签页。
  Ctrl+PageUp               向右切换当前窗口的标签页。
```

## Sublime snippet代码片段