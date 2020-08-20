## 1、通过ref使用DOM元素

vue.js 可以通过 ref

~~~html
<body>
    <div id="app">
        <my-com ref="xxx"></my-com>
        <button type="button" @click="run">点击</button>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                msg:'hello'
            },
            components:{
                'myCom':{
                    template:'<div>子组件</div>',
                    data(){
                        return {
                            sonMsg:'子组件数据'
                        }
                    },
                    methods:{
                        show(){
                            console.log("子组件的show方法");
                        }
                    }
                }
            },
            methods:{
                run(){
                    console.log(this.$refs.xxx.sonMsg);
                    this.$refs.xxx.show();
                }
            }
        })
    </script>
</body>
~~~

<br>

<br>

## 2、通过ref使用子组件中的data和methods

~~~html
<body>
    <div id="app">
        <my-com ref="xxx"></my-com>
        <button type="button" @click="run">点击</button>
    </div>
    <script type="text/javascript">
        var vm = new Vue({
            el:'#app',
            data:{
                msg:'hello'
            },
            components:{
                'myCom':{
                    template:'<div>子组件--{{sonMsg}}</div>',
                    data(){
                        return {
                            sonMsg:'子组件数据'
                        }
                    },
                    methods:{
                        show(x,y){
                            console.log(x+"  子组件的show方法  "+y);
                            this.sonMsg = x;
                        }
                    }
                }
            },
            methods:{
                run(){
                    console.log(this.$refs.xxx.sonMsg);
                    this.$refs.xxx.show("zs",24);
                }
            }
        })
    </script>
</body>
~~~





