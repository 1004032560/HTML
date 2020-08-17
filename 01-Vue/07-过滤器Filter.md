## 1、过滤器

### 1.1、局部过滤器

`filters:{ 过滤器名称(x){ return '$'+x+'元';} }`

<br>

#### 1.1.1、使用

`{{数据|过滤器名称}}`

<br>

#### 1.1.2、实例

~~~html
<body>
    <div id="app">
        {{price|yuan}}
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                msg:'hello',
                price:20.5
            },
            filters:{
                yuan(x){
                    return '$'+x+'元';
                }
            }
        })
    </script>
</body>
~~~

<br>

### 1.2、全局过滤器

#### 1.1.1、定义

`Vue.filter('过滤器名称',function(x,y){ return x+y; })`

<br>

#### 1.1.2、使用

`{{数据|过滤器名称(参数y)}}`

<br>

#### 1.1.3、实例

~~~html
<body>
    <div id="app">
        <!-- 使用全局过滤器 -->
        {{msg|myRev('你好')}}
    </div>
    <script type="text/javascript">
        //使用Vue.filter定义全局过滤器
        Vue.filter('myRev',function(x,y){
            //对 x（msg） 进行反转，对 y（'你好'） 进行拼接
            return x.split('').reverse().join('')+y;
        })
        var vm = new Vue({
            el:'#app',
            data:{
                msg:'hello',
            }
        })
    </script>
</body>
~~~

<br>

### 1.3、案例

~~~html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="js/vue.js" type="text/javascript" charset="utf-8"></script>
	</head>
	<body>
		<div id="app">
			<!-- 使用全局过滤器传一个参数(形如:’yyyy-MM-dd’或者’yyyy-MM-dd hh:mm:ss’)对data的时间数据进行格式化显示. -->
			{{msg|time('yyyy-MM-dd hh:mm:ss')}}
		</div>
		<script type="text/javascript">
			Vue.filter('time',function(date,y){
				
				var year = date.getFullYear();
				
				var month = date.getMonth() + 1;
				month = month<10?'0'+month:month;
				
				var day = date.getDate();
				day = day<10?'0'+day:day;
				
				var hours = date.getHours();
				var mins = date.getMinutes();
				var seconds = date.getSeconds();
				
				if(y=='yyyy-MM-dd'){
					return year+'-'+month+'-'+day;
				}
				if(y=='yyyy-MM-dd hh:mm:ss'){
					return year + '-' + month + '-' + day + '  ' + hours + ':' + mins + ':' + seconds;
				}
			});
			var vm = new Vue({
				el:'#app',
				data:{
					msg:new Date()
				}
			})
		</script>
	</body>
</html>
~~~

