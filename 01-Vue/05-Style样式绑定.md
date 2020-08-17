## 1、Vue绑定style样式

### 1.1、直接在:style写对象的显示

#### 格式：

`<div :style="{'color':'red','font-size':'36px'}">looper</div>`

#### 案例：

~~~html
<body>
    <div id="app">
        <div :style="{'color':'red','font-size':'36px'}">我是谁</div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{}
        })
    </script>
</body>
~~~

<br>

### 1.2、将样式保存到data中

#### 格式：

`<div :style="对象">looper</div>`

#### 案例：

~~~html
<body>
    <div id="app">
        <div :style="objStyle">我是谁</div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                objStyle:{'color':'red','font-size':'36px'}
            }
        })
    </script>
</body>
~~~

<br>

### 1.3、多个样式

#### 格式：

多个样式采用数组的形式进行绑定，数组中有 `[]`

`<div :style="[数组]">looper</div>`

#### 案例：

~~~html
<body>
    <div id="app">
        <div :style="[objStyle1,objStyle2]">我是谁</div>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                objStyle1:{'color':'red','font-size':'36px'},
                objStyle2:{'background':'green'}
            }
        })
    </script>
</body>
~~~

<br>

