# WEB  (updating...)

## HTML + CSS

### 行内元素/块级元素√

对比

- 块级元素
  - 单独占一行(宽度默认100%)
  - 总在新航上开始
  - 高度/行高以及内外边距都可控
  - 可以容纳内联元素/块元素
- 内联元素
  - 和其它元素在同一行
  - 高/行高/内外边距不可变
  - 宽度是文本/图片宽度 ；不可改变
  - 只能容纳文本/内联元素

常见元素

- 块元素
  - address
  - blockqueote引用
  - center居中对齐块
  - dir目录列表
  - div
  - dl定义列表
  - fieldset表单控制组
  - form
  - h1/2/3/4/5/6
  - hr
  - isindex ?
  - menu 菜单列表
  - noframes 不支持frame的浏览器显示此区块内容
  - noscript 不支持script的浏览器显示此内容
  - ol排序列表
  - p
  - pre 格式化文本
  - table
  - ul 非排序列表
- 内联元素
  - a 锚点
  - abbr 缩写
  - big 大字体
  - small 小字体
  - br 换行
  - cite 引用
  - code 代码
  - em 强调
  - i 斜体
  - strong 粗体
  - img 
  - input
  - span 常用容器 定义文本内区块
  - label  表格标签
  - select 项目选择
  - u 下划线
  - val 变量
  - sub 下标
  - sup 上标

块级元素和内联元素的转换

- display
  - 块元素：block
  - 行元素：inline
  - 行内块级元素：inline-block
- float
  - 设置为left/right时 会变成block  去除行内元素之间的空白
- position
  - absolute/fixed 会变成block

### 列表/表格/表单√

- 列表

  - 有序列表ol

    ```html
    <ol type='列表类型' start='起始编号'>
         <li> ... </li>
    </ol>
    ```

    type取值

    - 1 数字(默认)
    - a 小写字母
    - A 大写字母
    - i 小写罗马数字
    - I 大写罗马数字

  - 无序列表ul 

    ```html
    <ul type='列表类型'>
        <li> ... </li>
    </ul>
    ```

    type取值

    - disc 实心圆(默认)
    - circle 空心圆
    - square 实心矩形

  - 定义列表dl

    ```html
    <dl>
        <dt> 一个术语 </dt> <dd> 这个术语的定义 </dd>
    </dl>
    ```

  列表之间可以嵌套

- 表格
  - 标签
    - table 
    - caption 顶部标题
    - thead 表头
    - tbody 主体
      - tr 行
      - td 列
    - tfoot 表尾
  - 属性
    - width / height
    - align
    - border
    - cellpadding / cellspacing
  - 不规则表格
    - colspan 跨列
    - rowspan 跨行
  - 嵌套表格
- 表单
  - 元素
    - form
      - method 取值get/post；get是将数据放在url里 并对数据大小有限制 不安全；post是不将数据显示在url中 传输数据一般无限制 且安全
      - action 数据提交到哪里
      - name 表单名称
  - 控件元素
    - input
      - type: text/password/radio/checkbox `设置单选时要将name设置一致`
      - name 提交表单数据时必须要有name噢
      - required  / readonly
      - value 默认值
      - checked  单/多选时的默认值
      - maxlength
    - select
      - selected 默认选中项
      - size 一次可以看到几个选项
      - option 列表项
    - textarea
      - cols 宽
      - rows 高
    - label 实现点击选项按钮和点击文本一样的效果 使用for来绑定另一个元素的id

### CSS常用属性

### CSS选择器√

- 类选择器

  ==.==类名

- id选择器

  ==#==id名

- 标签选择器

  标签名

- 分组选择器

  标签1, 标签2, 标签31

- 后代选择器

- 属性选择器

  [属性类目='属性名称']

  如：[name='para1']

- 通用选择器

  ==*==

- 兄弟选择器

  指并列两个类型节点时 对后者的属性设置

  如 p==+==a 则对前有p节点的a节点进行样式设置

- 父子选择器

  ==>==

### 背景/边框/边距

### 大小/定位/锚点/透明

### CSS层叠/继承/盒子模型/溢出/元素类型

### 宽高自适应√

- 宽度自适应

  - 外层盒子百分百 内层盒子百分比

- 高度自适应

  - 外层盒子百分百

  - tips: 

    1. 父元素高度由子元素撑开 若子元素都浮动 则父元素不会被撑开 

       解决办法是清除浮动

       - 给父元素添加最后一个块级子元素
       - 给父元素添加overflow:hidden
       - 伪元素清除 .clearfix:after{ content: ''; display: block; overflow:hidden; visibility:hidden; clear:both; zoom:1}

    2. 预防子元素没有内容 撑不开父元素

       解决办法是 给父元素添加最小高度min-height

### 浏览器内核√

- ie   trident
- firefox   gecko
- opera   presto
- safari/chrome webkit

### 浏览器兼容√

- 图片有边框(IE8以下)

  img{border:0 none}

- 图片有间隙

  img{display:block}

- 双倍浮向

  {display:inline-block}

- 默认高度

  {font-size:0}

- 表单元素行高不一致

  {vertical-align: middle}

- 表单元素样式不一致

  外层嵌套一个元素 将表单元素的样式赋给外层元素

- 百分比bug

  如果都左浮动 最后一个清楚右浮动 clear:left

- margin塌陷

  第一个子元素与父元素存在上间距 给第一个子元素添加margin-top则会错误的渲染到父元素上

- margin合并

  垂直摆放时 上一个元素的margin-bottom和下一个元素的margin-top会发生合并 并取较大值

- 透明度

  opacity: 0-1;

  filter: alpha(opacity=0-100) (ie)

- 手型

  cursor: pointer;

  cursor: hand; (ie)

## JS

### 数据类型/变量

### 运算符/流程控制/语句

### 函数/数组

### String/Date

### BOM/DOM

### 事件及处理机制√

#### DOM事件流

某元素产生一个事件时，该事件会在元素节点与根节点之间按特定的顺序传播，路径所经过的节点都会收到该事件；

事件顺序有两种类型：

- 冒泡型事件
- 捕获型事件

[参考文档](https://www.jianshu.com/p/496a223f9f26)

### cookie及存储√

- cookie定义

  浏览器把用户信息以文件形式存储到本地硬盘的技术

- cookie作用

  存储客户数据

- cookie与变量的区别

  变量是临时存储到内存中的 是暂时性存储

  cookie是存储到硬盘的 是长期存储

- cookie的注意事项

  - 不同浏览器存放位置不同 不通用
  - 文件存储是以域名形式区分的
  - 数据可以设置名字(为了存储大量数据和方便操作)
  - 一个域名下存放的cookie数量是有限的 不同浏览器存放的个数不同
  - 每个cookie中存放内容大小有限 不同浏览器存放内容大小不同

- 从cookie中取数据

  ```js
  document.cookie  //name=tmp; age = tmp
  ```

- 向cookie中写数据

  ```js
  document.cookie = 'username = tmp';
  document.cookie = 'age = tmp';
  ```

- cookie长期存储数据

  写数据时加一个过期时间

  ```js
  var oDate = new Date();
  oDate.setDate(oDate.getDate() + 5);
  document.cookie = 'username = tmp; expires = ' + oDate; 
  ```

- ie兼容问题

  需要将oDate转换成string类型

- 存储特殊字符问题

  cookie存储对中文/转义字符的支持不友好，存放是最好==编码存放==(encodeURL / decodeURL)

  ```js
  var oDate = new Date();
  oDate.setDate(oDate.getDate() + 5);
  document.cookie = 'username =' + encodeURL('HELLO WORLD') + '; expires = ' + oDate.toGMTString();
  alert(decodeURL(document.cookie))
  ```

- 封装读取单个cookie值

  ```js
  function getCookie(key){
      var arr = document.cookie.split(';');
      arr.map((cur)=>{
          let str = cur.split('=');
          if(str[0] == key){
              return decodeURL(str[1]);
          }
      })
  }
  ```

- 封装写入cookie的办法

  ```js
  function setCookie(key, value , t){
      var oDate = new Date();
      oDate.setDate(oDate.getDate() + t);
      document.cookie = key + '=' + encodeURL(value) + '; expires=' + oDate.toGMTString();
  }
  ```

### 正则√

- 字符串方法

  - str.search(正则表达式)
  - str.replace(正则表示式,替换的新内容)

- 正则语法

  - /检索式/修饰符 

  - 修饰符

    - i   不区分大小写
    - g   全局匹配
    - m   多行匹配

  - 模式

    - [] 方括号
      - [abc]  表示查找方括号之间的任何字符
      - [0-9]  查找任何从0到0的数字
      - [x|y]   查找任何以|分隔的选项
    - \   元字符
      - \d   查找数字
      - \s    查找空白字符
      - \b    匹配单词边界
      - \uxxxx     查找以十六进制数xxxx规定的unicode字符
    - +*?   量词
      - n+  匹配任何包含==至少一个==n的字符串
      - n*  匹配任何包含==零或多个==n的字符串
      - n?   匹配任何包含==零或一个==n的字符串

  - RegExp对象

    - test() 校验字符串是否匹配某个模式 返回**布尔值**

      ```js
      let patt = /e/
      patt.test("You are the best");  //true
      ```

    - exec()  校验字符串是否匹配某个模式 返回**与之匹配的的数组**

- 一些实例

  - 是否带有小数

    ```js
    function isDemical(str){
    	return /^\d+\.+\d$/.test(str)
    }
    ```

  - 是否中文名称组成
    ```js
    function isChina(str){
    	return /^[\u4E00-\u9FA5]{2,4}$/.test(str)
    }
    ```
  - 是否全由8位数字组成
    ```js
    function isStuNo(str){
    	return /^[0-9]{8}$/.test(str)
    }
    ```
  - 校验电话格式
    ```js
    function isTel(str){
    	return /^((0\d{2,3}-\d{7,8})|(1[3584]\d{9}))$/.test(str)
    }
    ```
  - 校验邮件格式
    ```js
    function isEmail(str){
    	return /^\w+@[a-zA-Z0-9]{2,10}(?:\.[a-z]{2,4}){1,3}$/.test(str)
    }
    ```
### Ajax

### 原型与面向对象

#### 工厂模式

解决多个对象声明的问题

```
function createObj(name,age){
	var obj = new Object();
	obj.name = name;
	obj.age = age;
	obj.run = function(){
		return this.name + this.age
	}
	return obj;
}
```

产生的问题：无法判断实例的类型

#### 构造函数(ES6)

解决了重复实例化&对象识别的问题；

```js
function Box(name,age){
    this.name = name;
    this.age = age;
    this.run = function(){
        return this.name + this.age;
    }
}
```

与工厂模式的不同：

- 没有显式的创建对象(new Object())
- 直接将属性和方法赋值给对象
- 没有 return

构造函数的一些规范：

- 函数名和实例化构造名相同且首字母大写
- 通过new运算符创造对象

执行过程：

- 调用构造函数时，因为new了构造函数，所以后台执行了new Object
- 构造函数的作用域给新对象
- 执行构造函数内的代码
- 返回新对象(即使无return语句)

this作用域

- 作为构造函数使用时 this表示当前作用域对象的引用
- 普通模式调用时 this表示全局函数的引用(window)

#### 原型

- 来源

  prototype通过调用构造函数 而创建对象的原型对象；

- 优势

  所有对象实例共享属性/方法(不必在构造函数中定义对象信息，而是直接将这些信息添加到原型中)(方法的引用地址一致)

- 

## HTML5 + CSS3

### 语义化标签

### H5新增的元素与属性

### 表单域增强元素

### 盒模型/阴影/弹性盒模型

### CSS3选择器

### 文字字体相关样式

### CSS3位移与表型处理

### CSS3 2D转换与过渡动画

### CSS3 3D转换与关键帧动画

### 媒体查询与响应式设计

### 视频与音频

### canvas基础

### 文件支持与二进制数据

## WebApp页面布局

### 移动端页面设计规范/移动端切图

### 流式布局/等比缩放布局(rem布局)/响应式布局/flex布局

### viewport / rem / vw

### 移动端reset / 1px border / 图片格式及优化

### 淘宝移动端页面适配方案

## ES6+

### 块级作用域绑定

### 函数新特性与箭头函数

### 扩展对象功能

### 解构与symbol

### set与map

### 迭代器与生成器

### JS的类与面向对象

### Promise与异步编程

### 模块化

### 作用域链/闭包/this/ES6新特性

## Node.js

### 模块与包管理工具

### HTTP模块 / events模块

### fs模块 / stream模块

### 核心模块使用 / 第三方模块使用

### RESTFulAPI /  读取图片文件 / npm scripts

## 浏览器相关

### 浏览器架构与渲染流程

### 事件循环

### 从输入url到站时的过程

### http1/2/3 https 状态码及连接建立过程

### 同源策略same-origin policy 与 用户代理UA

### 跨域及解决方案

### 浏览器数据本地存储方法

### webwork及客户端通信

### web安全及内存泄漏

### HTTP缓存

### cookie/session/token的区别

## 前端工程化与模块化

### webpack基础原理及打包流程

### commonJS / AMD / CMD / ES6模块化

## 框架

### VUE

#### MVVM模式 / 前端组件化 / 单文件组件

#### 组件间传值 / Vue实例 / 实例生命周期

#### 模板语法 / 计算属性 / 侦听器

#### 样式绑定 / 条件渲染 / 列表渲染

#### Vue中的set方法 / 父子组件传值

#### 插槽 / 作用域插槽 / 动态组件

#### vue动画

#### Element UI

### VUE Router

#### 原理

#### 动态路由及嵌套路由

#### 命名路由及命名视图

#### 重定向 / 别名 / 传参

#### 导航守卫及路由元信息

#### 数据获取 / 滚动状态保持 / 路由懒加载

### VUEX

#### 原理及State

#### Getter / Mutation

#### Action / Module

## 混合开发

### Webview

### JSBridge

