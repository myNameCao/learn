# node

Ryan Dahl最初期望设计一个高性能的Web服务􀙧，后来则演变为一个可以
基于它构建各种高􁤳、可伸缩网络应用的平台，因为一个Web服务器已经无法掩盖和代表它
的能力了。



+ ## 核心模块和文件模块
node  的核心模块在编译成可以执行的过程中被编译成二进制文件
其实分为  **c++** 编写的和 **javaScript**编写两部分 其中**c++**文件放在node项目的src 中**javaScrirpt**文件放在lib 目录下


+ ## package.json 

包描述文件用于表达非代码相关的信息
 
 
+ ## 异步I／O
 
 
 因为在浏览器中JavaScript在单线程上执行，
而且它还与UI渲染共用一个线程。这意味着JavaScript在执行的时候UI渲染和响应是处于停滞状态的


 + ## 高阶函数 

将函数作为参数或则 将函数作为返回值
 
``` js 
 
 var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b) {
return a - b;
});
[ 1, 5, 10, 25, 40, 100 ]

 ```
 + ## 偏函数用法
 创建一个调用另外一个部分————参数或则变量已经预设的函数————的函数的
用法
```js 
var toString = Object.prototype.toString;
var isString = function (obj) {
return toString.call(obj) == '[object String]';
};
var isFunction = function (obj) {
return toString.call(obj) == '[object Function]';
};
<=========================> 对比偏函数的用法 闭包
var isType = function (type) {
return function (obj) {
return toString.call(obj) == '[object ' + type + ']';
};
};
var isString = isType('String');
var isFunction = isType('Function');


```
+ ## events 模块  事件的订阅和发布

node 事件 没有 preventDefault() stopPropagation() 和stopImmediatePagation() 





