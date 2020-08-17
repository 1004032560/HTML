## 1、Vue绑定class样式

### 1.1、使用数组绑定

#### 格式：

`<div :class="['样式名1','样式名2','样式名3']"></div>`

注意：数组中的样式名必须使用 `''`。

#### 案例：

1、样式

~~~html
<style type="text/css">
    .big{
        font-size: 36px;
    }
    .small{
        font-size: 10px;
    }
    .red{
        color: red;
    }
</style>
~~~

<br>

2、HTML

~~~html
<body>
    <div id="app">
        <div :class="['big','red']">
            {{msg}}
        </div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                msg:'Hello'
            }
        })
    </script>
</body>
~~~

<br>

### 1.2、三目运算

#### 格式：

`<div :class="[flag?'样式名1':'样式名2','样式名3']"></div>`

#### 案例：

~~~html
<body>
    <div id="app">
        <div :class="[flag?'big':'small','red']">
            {{msg}}
        </div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                flag:false,
                msg:'Hello'
            }
        })
    </script>
</body>
~~~

<br>

### 1.3、使用对象代替三目运算符绑定样式

#### 格式：

`<div :class="[{'样式名1':flag},'样式名2']"></div>`

#### 案例：

~~~html
<body>
    <div id="app">
        <div :class="[{'big':flag},'red']">
            {{msg}}
        </div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                flag:true,
                msg:'Hello'
            }
        })
    </script>
</body>
~~~

<br>

### 1.4、使用对象的方式

#### 格式：

`<div :class="{'样式名1':flag,'样式名2':flag}"></div>`

#### 案例：

~~~html
<body>
    <div id="app">
        <div :class="{'big':flag,'red':flag}">
            {{msg}}
        </div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                flag:true,
                msg:'Hello'
            }
        })
    </script>
</body>
~~~

<br>

~~~html
<body>
    <div id="app">
        <div :class="objClass">
            {{msg}}
        </div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                msg:'Hello',
                objClass:{'big':true,'red':true}
            }
        })
    </script>
</body>
~~~

