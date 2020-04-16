# HTML学习记录

## week01

### 1、因特网和万维网

1.1、Internet因特网：全球资源的总汇，连接网络的网络

1.2、TCP/IP 协议簇：传输层/网络层协议

1.3、万维网：www（world wide web）

* HTTP超文本传输协议

  作用：接受和发布 HTMl 页面

* URL 统一资源定位符

  协议://域名:端口号/文件路径/文件名.文件后缀

  `http://www.QQ.com.cn:80/tq/index.html`

1.4、W3C 组织  负责制定 web 行业的标准

### 2、HTML 

2.1、**超文本标记语言 **(**H**yper **T**ext **M**arkup **L**anguage)

2.2、标签：对当前的内容进行规范

* 单标签<标签名/>
* 双标签<标签名></标签名>

2.3、属性：对当前的标签中的内容进一步修饰

2.4、网页

* 静态网页文件扩展名为 `.html` 或 `.htm`
* 动态网页文件扩展名为 `.jsp` 或 `.aspx`、`.asp`、`.php` 等

2.5、HTML 注释：`<!-- 注释内容 -->`

### 3、HTML 标签

3.1、`<head>` 标签



~~~~html
<!-- 设置网页编码格式 -->
<meta charset="UTF-8">

<!-- 网页根据终端设备进行适屏处理 -->
<meta name="viewport" content="width=device-width, initial-sacle=1"/>

<!-- 网页关键词 -->
<meta name="keywords" content="测试" />

<!-- 对网页的描述 -->
<meta name="description" contend="测试页面" />

<!-- 设置对浏览器Edge兼容,一般情况书写在<head>开始 -->
<meta http-equiv="X-UA-Compatible" content="IE=edge" />

<!-- 添加图标 -->
<link rel="icon" href="img/1.jpg" />

<!-- 标题标签 -->
<title>我的 第2个页面</title>
~~~~



3.2、`<body>` 标签

* 背景：`background` 设置网页的背景图

* 文本：`text` 设置网页的文本颜色

* 左边距：`leftmargin` 设置网页中的内容到左边距之间的距离

* 左边距：`topmargin` 设置网页中的内容到顶部距之间的距离

* 颜色属性：`bgcolor` 设置网页的背景颜色

3.3、`<h1>-<h6>` 标题标签

* 该标签属于块级标签，该标签独立占据一行，该行不允许其他标签出现

* `style` 属性：设置样式

* `align` 属性：设置标题文字的水平对齐方式

* `align`取值范围：`left` 居左；`right` 居右；`center` 居中；`justify`：两端对齐



3.4、`<br/>` 换行标签



3.5、`<hr/> `分割线

* `size` 属性：设置分割线的高度

* `color` 属性：设置分割线颜色；一旦设置颜色将失去 `3D` 效果

* `width` 属性：设置分割线宽度

* `align` 属性：设置对齐方式



3.6、`<p></p>` 段落

* 作用：定义段落

* 属性：`align` 设置段落文字的水平对齐



3.7、`<img>` 图片

* 图片的格式：`JPG`、`GIF`、`PNG`、`BMP`等

* 作用：显示图片

* `src` 属性：指明图片位置（相对路径，绝对路径）**注意：图片的路径尽量不要出现中文。**

* `alt` 属性：图片无法显示时的替代信息
* `title` 属性：提示信息
* `width` 和 `height` 属性：图片的宽度和高度
* `align` 属性：设置周围文本对齐方式；（`bottom` 默认的；`middle`；`top`）
* `align` 属性：使图片浮动到段落的左边或者是右边；（`left`；`right`）



3.8、`font` 定义字符

* 作用：定义字符的相关样式
* `face` 属性：定义字体，默认宋体
* `color` 属性：定义字体颜色
* `size` 属性：字号，最大为 `7`，大于 `7` 全部按 `7` 号显示
* **在 `HTML 4.01` 中，`font` 元素不被赞成使用。**
* **在 `XHTML 1.0 Strict DTD` 中，`font` 元素不被支持。**



3.9、`<a></a>` 超链接

* 作用：超级链接

  1、实现页面之间的跳转

  2、页内跳转

  3、`mailto`

  4、资源下载

~~~html
<a name="top">我就是顶部<br /></a>
		<img src="img/1.jpg" /><br />
		<img src="img/1.jpg" /><br />
		<img src="img/1.jpg" /><br />
		<img src="img/1.jpg" /><br />
		<img src="img/1.jpg" /><br />
<a href="#top">返回顶部</a>
~~~



3.10、`<span></span>`标签

* 范围标签：显示某行内的独特样式

~~~html
<p>手机<span style="color:red;font-size:36px;">￥100</span>元一部</p>
~~~



311、有序列表



3.12、无序列表





## week02

