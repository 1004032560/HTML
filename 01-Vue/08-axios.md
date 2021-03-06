## 1、axios

### 1.1、什么是axios

Axios 是一个基于 promise 的 HTTP 库，可以用在浏览器和 node.js 中。 

<br>

### 1.2、特性

- 从浏览器中创建 XMLHttpRequests
- 从 node.js 创建 http 请求
- 支持 Promise API
- 拦截请求和响应
- 转换请求数据和响应数据
- 取消请求
- 自动转换 JSON 数据
- 客户端支持防御 XSRF

<br>

### 1.3、使用案例

~~~javascript
methods:{
    getList(curPage){
        axios.get("http://localhost:8080/student/list?curPage="+curPage+"&name="+this.name)
        .then((resp)=>{
            this.page = resp.data.page
        })
    },
    save() {
        var student = new FormData(document.getElementById("form2"));
        axios.post('http://localhost:8080/student/add', student)
            .then(function(response) {});
        window.location.href = '/0818-student/list.html';
    }
}
~~~

