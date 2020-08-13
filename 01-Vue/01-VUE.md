## 1、VUE





<br>

## 2、前端MVVM

MVVM：M（Model）、V（View）、VM（ViewModel）实现双向数据绑定。

Model：保存页面中的数据

View：HTML 页面

ViewModel：V 和 M 之间的调用者，做中间处理，是 MVVM 的核心思想

<br>

## 3、Vue.js快速入门

~~~html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>hello</title>
		<!-- 1.引入 Vue.js -->
		<script src="js/vue.js" type="text/javascript" charset="utf-8"></script>
	</head>
	<body>
		<!-- 2.HTML 页面 View -->
		<div id="app" >
			<!-- 插值表达式 -->
			{{msg}}
		</div>
		<!-- 3.在 JavaScript 中创建 Vue 对象 -->
		<script type="text/javascript">
			var vm = new Vue({
				el:'#app',    //挂载 div 
				data:{    //Vue 实例的数据对象 Model
					msg:'Hello World!'
				}
			})
		</script>
	</body>
</html>
~~~

