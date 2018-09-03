# Travel(A learning front-end Vue.js project)

## 前端演进过程

关于前端开发的演进过程大家可以看这一篇文章![萌新也能懂的现代 JavaScript 开发](https://zhuanlan.zhihu.com/p/31044340)

对于现代前端开发工具进行一个简单的总结：

- webpack模块打包工具
	把整个的 moment.min.js 文件下载到 HTML 中，定义了一个全局变量 moment，对于所有在 moment.min.js 之后下载的文件都可用（无论是否真的需要它）
- babel用于编写下一代 JavaScript 的编译器
	把下一代的 JavaScript 中还未在所有浏览器实现的新特性（ES6 和之后）编译成更早更兼容的 JavaScript( ES5) 
- npm包管理工具
	跟踪依赖项和版本、自动构建工具执行npm脚本包括最小化代码文件、优化图片、运行测试

## 移动端开发注意事项

- 设置<meta>固定设备比禁止双手放大

``` JavaScript
	<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">
```

- 移动端点击（click）事件延迟问题
	1)使用`npm install fastclick --save`安装fastclick.js
	2)在main.js中引入fastclick
		import fastClick from 'fastclick'
	3)在main.js使用fastclick
		fastClick.attach(document)

- 初始化移动端不同手机样式不同的问题
	引入reset.css

- 移动端解决1像素边框在多倍屏显示成多像素问题
	引入border.css

## Sublime快捷键

```
  Ctrl + Enter            	将光标移到当前行的下一行
  Ctrl+Shift+Ente           在上一行插入新行
  Ctrl+Shift+D              复制光标所在整行，插入到下一行
  Ctrl+Shift+↓              将光标所在行插入到下一行之后
  Ctrl+Shift+K              删除当前行
```

## Sublime snippet代码片段