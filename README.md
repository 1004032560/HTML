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

### 3、HTML 标签和属性

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

~~~~html
<ul>
    <li>数码</li>
    <ul>
        <li>笔记本</li>
        <li>手机</li>
        <li>电脑</li>
    </ul>
    <li>美容</li>
    <li>服装</li>
</ul>
~~~~

3.12、无序列表

~~~html
<ol>
    <li>确认购物</li>
    <li>付款</li>
    <li>确认收货</li>
    <li>付款</li>
    <li>付款给商家</li>
    <li>双方评价</li>
</ol>
~~~

3.13、定义列表（图文混排）

~~~html
<!-- 定义列表（图文混排） -->
<dl>
    <dd>描述信息</dd>
    <dt>图片</dt>
</dl>
~~~

3.14、`float` 属性：浮动

`float` 属性值：`left` 元素向左浮动；`right` 元素向右浮动；`none` 默认值，元素不浮动，并会显示在其文本中出现的位置

3.15、`clear` 属性：清除浮动

`clear` 属性值：`left` 在左侧不允许浮动元素；`right` 在右侧不允许浮动元素；`both` 在左右两侧不允许浮动元素；`none` 默认值，允许浮动出现在元素左右两侧

3.16、元素的外边距：`margin`、`margin-top`、`margin-left`、`margin-right`、`margin-bottom`

当前元素和外围的元素之间的间隔

3.17、元素的内边距：`padding`、`padding-top`、`padding-left`、`margin-right`、`margin-bottom`

当前元素和内部嵌套元素之间的间隔

3.18、`<video>` 标签在 `HTML5` 中，专门用于视频资源的播放

`<video>` 标签的属性：`controls` 控制面板；`autoplay` 自动播放；`loop` 循环播放

3.19、`<audio>` 标签在 `HTML5` 中，专门用于音频资源的播放

`<audio>` 标签的属性：`controls` 控制面板；`autoplay` 自动播放；`loop` 循环播放

3.20、其他标签

~~~html
<b>加粗内容</b><br />
<strong>加粗内容</strong><br />
<i>倾斜内容</i><br />
<u>下划线</u><br />
<s>删除</s><br />
<s>原价：￥1888</s>
~~~

3.21、空格

3.22、版权

### 4、表格

表格：行和列组成

作用：显示数据



~~~html
<table border="1" cellspacing="5" cellpadding="0" width="500px" height="200px" align="center" bgcolor="blue">
    <!-- 行 -->
    <tr align="center">
        <!-- 列 -->
        <td colspan="2">测试</td>
        <td rowspan="2">测试</td>
    </tr>
    <tr align="center">
        <td>测试</td>
        <td>测试</td>
    </tr>
    <tr align="center">
        <td>测试</td>
        <td>测试</td>
        <td>测试</td>
    </tr>
</table>
~~~

不规则表格 要合并单元格

`colspan` 属性：跨列

`rowspan` 属性：跨行

数最大行数和列数，制作表格；合并单元格；删除多余的单元格

### 5、表单

5.1、核心标签 `<form>`；其属性包括：

* `id`：该标签在当前页面的身份
* `name`：该标签在当前文档中的名称
* `method`：客户端向服务器提交数据的方式（常见 get 、 post 两种）
  * `get`：所提交的数据不进行加密处理，客户端浏览器地址栏可以直接看到提交的数据（数据写在请求头），同时表单提交数据大小不允许超过 `128k` 。应用场景：非安全或非关键数据。
  * `post`：所提交的数据全部进行网络安全加密，无法被客户端所截获，保证提交数据的安全性（数据写在请求体），并且提交数据的大小无限制。应用场景：安全数据或关键数据。
* `action`：客户端提交数据的目的地址和资源位置
* `enctype`：当表单中存在组建上传时必须使用标签设置表单的数据模式，添加此属性，将表单的数据以二进制格式提交服务器。而且 `method` 属性必须是 `post`
* `onSubmit`：当表单需要在提交数据前进行验证的时候须添加该属性，该属性与 `js` 动态脚本关联，达到表单提交前的数据验证，若验证不通过则不提交服务器。在 `HTML5` 版本下，很多表单元素自带基本验证机制，因此该属性使用频率也在下降

5.2、文本框

5.3、密码框

5.4、单选框

5.5、复选框

5.6、文件输入框

5.7、多行文本框（文本域）

5.8、下拉列表

5.9、按钮

* 系统按钮、提交、重置、自定义按钮

~~~html
<input type="submit" value="注册" /><br />
<input type="reset" /><br />
<input type="button" value="自定义按钮"/><br />
~~~

5.10、隐藏域

* 需求：方便服务端记住客户端的信息、但又不希望客户端看到的数据

~~~html
<input type="hidden" name="ip" value="192.168.70.200"/>
~~~





## week02

