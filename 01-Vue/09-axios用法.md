## 1、axios用法

* get 传参
* delete 传参
* post 传参

* put 传参（与 post 差不多）

<br>

### 1.1、post

put 请求与 post 请求是一样的

* 通过选项（名：值）传参，默认的格式是 JSON ，服务端对于 JSON 格式的数据需要添加注解 @RequestBody 进行格式转换

前端：

~~~javascript
<script type="text/javascript">
    axios.post('http://localhost:8080/user/add',{
        username:'zs',
        password:'123456'
    }).then(resp=>{
        console.log(resp.data);
    })
</script>
~~~

后端：

~~~java
@RequestMapping("/add")
public String add(@RequestBody User user){
    System.out.println(user);
    return "???:"+user;
}
~~~

<br>

* 通过 URLSearchParams 传参，参数的传递格式属于 Form-Data 格式的，所以服务器端接收时，不需要注解。
* 使用 Form 表单时，提交数据格式和该方法一样。

前端：

~~~javascript
<script type="text/javascript">
    var params = new URLSearchParams();
    params.append("username","zs");
    params.append("password","123456");
    axios.post('http://localhost:8080/user/add',params).then(resp=>{
        console.log(resp.data);
    })
</script>
~~~

Form表单

~~~html
	<body>
		<div id="app">
			<form id="form1" >
				用户名：<input type="text" name="username" value="zs">
				密码：<input type="password" name="password" value="123">
				<input type="button" value="提交"/>
			</form>
		</div>
		<script type="text/javascript">
			var fd = new FormData(document.getElementById("form1"));
			axios.post('http://localhost:8080/user/add',fd).then(resp=>{
				console.log(resp.data);
			})
		</script>
	</body>
~~~

后端：

~~~java
@RequestMapping("/add")
public String add(User user){
    System.out.println(user);
    return "???:"+user;
}
~~~

<br>

<br>

## 2、axios的响应结果

* data：数据

* status：状态码，正常返回200

* statusText：状态描述信息

* headers：响应头

<br>

<br>

## 3、axios全局配置

* 设置默认超时时间：`axios.defaults.timeout=3000`

* 设置默认地址：`axios.defaults.baseURL='http://localhost:8080'`

* 设置请求头：`axios.defaults.headers['mytoken'] = 'qwertyu'`

<br>