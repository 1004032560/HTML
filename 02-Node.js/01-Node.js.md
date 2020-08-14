## 1、Node.js

### 1.1、什么是Node.js

Node.js 是 js 运行时的环境，类比于 Java 中的 JVM。

<br>

### 1.2、什么是ES6

ES6 是 ECMAScript 6.0 的简称，是 JavaScript 语言的下一代标准，他的目标是使得 JavaScript 语言可以用来编写大型的应用程序。



## 2、安装Node.js



<br>

## 3、变量的声明

### 3.1、var

var 声明变量（不属于 ES6）：预先解析（变量的提升），先使用后声明，不会报错，会输出 undefined。

~~~javascript
console.log(flag);
var flag = true;
console.log(flag);
~~~

<br>

### 3.2、let

let 声明变量（属于 ES6）：不会预先解析，先使用后声明，会报错。

~~~javascript
let flag = true;
console.log(flag);
//let flag = true;
console.log(flag);
~~~

<br>

## 4、重复定义



~~~javascript
//let flag = true;
//let flag = false;
var flag = true;
var flag = false;
console.log(flag);
console.log(flag);
~~~

<br>

## 5、{}作用域

{} 内部定义的变量，在外部不可以访问

var 在 {} 中定义的变量，在 {} 外部可以访问

~~~javascript
if (true) {
	var num = 1;
}
console.log(num);// 1
~~~

<br>

let 在 {} 中定义的变量，在 {} 外部不可以访问

~~~javascript
if (true) {
	let num = 1;
}
console.log(num);// num is not defined
~~~

<br>

## 6、const使用

* const 用来声明常量

<br>

* const 声明的常量，不允许重复赋值

~~~javascript
const num = 1;
const num = 2;
console.log(num);// Identifier 'num' has already been declared
~~~

<br>

* const 声明的常量必须进行初始化

~~~javascript
const num;
console.log(num);// Missing initializer in const declaration
~~~

<br>

* let 的块级作用域 {} 对 const 也适用

~~~javascript
if (true) {
	const num = 2;
}
console.log(num);// num is not defined
~~~

<br>

## 7、解构赋值

解构赋值可以同时定义 n 个变量并赋值，一次可以给多个变量赋值，每个变量赋一个值

### 7.1、使用[]进行解构

~~~javascript
let [a,b,c] = [1,2,3];
console.log(a,b,c);// 1 2 3
~~~

<br>

### 7.2、给变量设置默认值

~~~javascript
let [i=11,j,k=13]=[,15,];
console.log(i,j,k);// 11 15 13
~~~

<br>

### 7.3、对象的解构赋值

~~~javascript
let person = {id:101,name:'zs'}
console.log(person);// { id: 101, name: 'zs' }
~~~

<br>

### 7.4、字符串的解构赋值

* 变量和解构出来的值个数正好匹配

~~~javascript
let [a,b,c,d,e]='Hello';
console.log(a,b,c,d,e);// H e l l o
~~~

<br>

* 如果数据不足，不足的使用 undefined

~~~javascript
let [a,b,c,d,e]='Hello';
let [a,b,c,d,e,f,g,h,j,k]='Hello';
console.log(a,b,c,d,e,f,g,h,j,k);// H e l l o undefined undefined undefined undefined undefined
~~~

<br>

* 如果数据多，只取之前的

~~~javascript
let [a,b,c,d,e]='Hello123456';
console.log(a,b,c,d,e);// H e l l o
~~~

<br>

## 8、字符串扩展

* includes() 判断字符串是否有指定的子串（有：true，没有：false）

第一个参数：要进行匹配的子串

第一个参数：要从第几个参数进行查找（判断）

~~~javascript
let s = 'abcdef@163.com';
console.log(s.includes('abc'));// true
~~~

<br>

* startsWith() 判断是否以指定的子串开始

~~~javascript
let s = 'abcdef@163.com';
console.log(s.startsWith('1abc'));// false
~~~

<br>

* startsWith() 判断是否以指定的子串开始

~~~javascript
let s = 'abcdef@163.com';
console.log(s.endsWith('com'));// true
~~~

<br>

* 模板字符串：在反引号中采用 ${} 的方式取值

~~~javascript
let person = {id:102,name:'zs'};
let tp1 = `
	我是${person.name}，我的ID是：${person.id}，欢迎你的到来
`;
console.log(tp1);//       我是zs，我的ID是：102，欢迎你的到来
~~~

<br>

## 9、箭头函数

* 无参数函数 ES6 之前的写法

~~~javascript
function ch1(){
	console.log("Hello");
}
ch1();// Hello
~~~

<br>

* 无参数函数 ES6 的写法（箭头函数写法）

~~~javascript
let ch1 = () => {
	console.log("Hello");
}
ch1();// Hello
~~~

<br>

* 有单个参数的箭头函数的写法

~~~javascript
let ch1 = (num) => {
	console.log(num);
}
ch1(200);// 200
~~~

<br>

* 有多个参数的箭头函数的写法

~~~javascript
let ch1 = (num1,num2) => {
	console.log(num1+num2);
}
ch1(200,200);
~~~

<br>

* 箭头函数作为匿名函数

~~~javascript
let arr = [1,2,3,4,5];
arr.forEach((item,i)=>{
	console.log(i + '-----' + item);
})
~~~

<br>

## 10、计算属性



<br>



<br>



<br>



<br>