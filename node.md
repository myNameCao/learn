# node 基础

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

如果同一个事件添加超过了10个监听器将会有一条警告 调用**emitter.setMaxListeners(num)** 可以将取消这个限制 
+ ## 继承 evnets 模块 
```js
//继承的方法 
var events = require('events');
function Stream() {
events.EventEmitter.call(this);
}
util.inherits(Stream, events.EventEmitter);

```
## node  和 v8  
 
node 是构建早chrome  的javasprict 运行平台的  2009 年 node 创始人选择了v8 作为 node 的javascript 
脚本引擎 。，


在Node中通过JavaScript使用内存时就会发现只能使用部分内存（64􀍮系统下约为1.4 GB，32􀍮系统下约为0.7 GB。在
这样的限制下，将会导致Node无法直接操作大内存对象，比如无法将一个2 GB的文件读入内存
中进行字符串分析处理，即使物理内存有32 GB。这样在单个Node进程的情况下，计算机的内存
资源无法得到充足的使用。

## v8  对象的分配 

node 
> process.memoryUsage() 
//
```js 
{
rss:mun
heaptoral:num
headUsed:num
}
```
