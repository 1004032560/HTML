## 1、Vue生命周期

从 Vue 实例创建、运行、到销毁的期间，伴随这各种事件，这些事件统称为生命周期。

生命周期函数不能写到 methods 中，写在与 methods 平级的位置。

![lifecycle.png](image/lifecycle.png)

<br>

### 1.1、实例创建期间生命周期函数

#### 1.1.1、beforeCreate()

执行时机：实例被完全创建之前会执行它。

在 beforeCreate 生命周期函数执行的时候，data 中的数据和 methods 中的方法都没有被初始化。

~~~javascript
beforeCreate() {
    console.log(this.msg); //输出undefined
    //this.test();//报错  注意：方法调用也有this
    console.log('=====beforeCreate阶段======');
},
~~~

<br>

#### 1.1.2、created()

执行时机：实例被创建之后会执行它。

在 created 中 data 和 methods 都已经被初始化了。

如果想要调用 data 中的数据和 methods 中的方法，最早只能在 created 中操作。

~~~javascript
created() {
    console.log(this.msg); //输出undefined
    this.test(); //报错
    console.log('=====create阶段======');
},
~~~

<br>

#### 1.1.3、beforeMount()

执行时机：表示模板已经编译完成在内存中了，但是尚未把模板渲染到页面。

在 beforeMount 执行的时候，页面中的元素还没有真正的被替换，只是之前的模板字符串。

~~~javascript
beforeMount() {
    console.log(document.getElementById("app").innerText); //结果是{{msg}}
    console.log('=====beforeMount阶段======');
},
~~~

<br>

#### 1.1.4、mounted()

执行时机：内存中的模板已经挂载到了页面，用户已经可以看到完整的内容了。

mounted 是实例创建期间最后一个生命周期函数。

执行完 mounted 表示实例已经挂载完成，如果想要通过某些插件操作 DOM 节点，最早要在 mounted 中进行。

~~~javascript
mounted() {
    console.log(document.getElementById("app").innerText); //结果是hello
    console.log('=====mounted阶段======');
},
~~~

<br>

<br>

### 1.2、运行期间生命周期函数

运行期间的生命周期函数会执行多次。

<br>

#### 1.2.1、beforeUpdate()

执行时机：表示数据已经更新，页面还没有更新。

注意：页面和 data 中的数据没有同步。

~~~javascript
updated() {
    console.log('data中的数据：' + this.msg);
    console.log('页面中的数据：' + document.getElementById("app").innerText);
    console.log('=====updated阶段======');
},
~~~

<br>

#### 1.2.2、updated()

执行时机：data 中的数据和页面中的数据保持同步，数据都是最新的

~~~javascript
updated() {
    console.log('data中的数据：' + this.msg);
    console.log('页面中的数据：' + document.getElementById("app").innerText);
    console.log('=====updated阶段======');
},
~~~

<br>

<br>

### 1.3、销毁期间生命周期函数

#### 1.3.1、beforeDestory()

执行时机：销毁过程

data / methods / fiter / 指令... 都处于可用状态，并没真正执行销毁

~~~javascript
beforeDestroy() {
    //data/methods/fiter/指令...都处于可用状态,并没真正执行销毁
    console.log('=====beforeDestroy阶段======');
},
~~~

<br>

#### 1.3.2、destoryed()

执行时机：销毁过程

data / methods / fiter / 指令... 都处于不可用状态

~~~javascript
destroyed() {
    // data/methods/fiter/指令...都处于不可用状态
    console.log('====destroyed阶段======');
}
~~~

<br>

<br>

### 1.4、案例

~~~html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title></title>
		<script src="js/vue.js" type="text/javascript" charset="utf-8"></script>
	</head>
	<body>
		<div id="app">
			{{msg}}
		</div>
		<script>
			var vm = new Vue({
				el: '#app',
				data: {
					msg: 'hello',
				},
				methods: {
					test() {
						console.log('方法被调用...');
					}
				},
				//注意：生命周期函数，不在methods中
				//实例被完全创建之前会执行它。注意:在beforeCreate生命周期函数执行的时候,data中的数据和methods中的方法都没有被初始化
				beforeCreate() {
					console.log(this.msg); //输出undefined
					//this.test();//报错  注意：方法调用也有this
					console.log('=====beforeCreate阶段======');
				},
				//注意：在created中data和methods都已经被初始化了。如果想要调用data中的数据和methods中的方法,最早只能在created中操作
				created() {
					console.log(this.msg); //输出undefined
					this.test(); //报错
					console.log('=====create阶段======');
				},
				// 表示模板已经编译完成在内存中了,但是尚未把模板渲染到页面。在beforeMount执行的时候,页面中的元素还没有真正的被替换,只是之前的模板字符串
				beforeMount() {
					console.log(document.getElementById("app").innerText); //结果是{{msg}}
					console.log('=====beforeMount阶段======');
				},
				//内存中的模板已经挂载到了页面,用户已经可以看到完整的内容了。注意:mounted是实例创建期间最后一个生命周期函数。执行完mounted表示实例已经挂在完成，如果想要通过某些插件操作DOM节点,最早要在mounted中进行
				mounted() {
					console.log(document.getElementById("app").innerText); //结果是hello
					console.log('=====mounted阶段======');
				},
				//运行期间
				//表示页面还没有更新,数据已经被更新了。页面和data中的数据没有同步
				beforeUpdate() {
					console.log('data中的数据：' + this.msg);
					console.log('页面中的数据：' + document.getElementById("app").innerText);
					console.log('=====beforeUpdate阶段======');
				},
				//data中的数据和页面中的数据保持同步,都是最新的
				updated() {
					console.log('data中的数据：' + this.msg);
					console.log('页面中的数据：' + document.getElementById("app").innerText);
					console.log('=====updated阶段======');
				},
				//销毁过程
				beforeDestroy() {
					//data/methods/fiter/指令...都处于可用状态,并没真正执行销毁
					console.log('=====beforeDestroy阶段======');
				},
				destroyed() {
					// data/methods/fiter/指令...都处于不可用状态
					console.log('====destroyed阶段======');
				}
			});
		</script>
	</body>
</html>
~~~

