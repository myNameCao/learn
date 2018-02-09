 ##  闭包
 **函数的作用域链:** 变量对象的指针列表（本地的活动变量和全局的变量）这个作用域是函数定义时创建的，并不是函数执行时定义的。
 
 
 ```js
 
 // 一般闭包
  var unique=(function(){
  var counter=0;
  return function(){return counter++}
  }())；
  //  多个嵌套函数都共享一个作用域 
  function conuter() {
    var n=8
    return {
        count:function () {
            return n++
        },
        reset:function () {
            n=0
        }
    }
};

var  a=conuter(); b=conuter();
console.log(a.count());//8
console.log(a.count());//9
console.log(b.count());//8 它们互不干扰
console.log(a.count());//10
console.log(a.reset());// undefined 
console.log(a.count()); // 0  reset()和count() 方法 共享状态
console.log(a.count());// 1
console.log(b.count());// 9 没有重置 b 
  
 ```
 
##  从技术角度 将闭包合并成属性存取器 

使用参数来保存私有状态 
``` js 
function counter(n) {
    return {
        get  count(){
            return n++
        },
        set  count(m){
            if(m>n)n=m
            else throw Error('你设置的不对')
        }
    }
};
var  c = counter(1000);
c.count  // 他不是一个函数  ** 注意 **
console.log(c.count) //1001
c.count=2000;
console.log(c.count)//2000
c.count

```

**以上是在同一个作用域中定义两个闭包 这两个闭包共享同样的作用域( 变量或私有变量)这是一个非常重要的技术**


## Array.length 
```js 

var arr=[1,2,3,4,5,6]
// Object.defineProperty(arr,'length',{writable:false})
arr.length=1
console.log(arr)// [1,2,3,4,5,6]

```


## 函数申明和变量申明谁在先

先函数声明前置，然后在变量声明JS解释器通过变量对象（Variable Object, VO)来获取。VO是一个抽象概念的“对象”，函数的VO分为两个阶段——变量初始化和代码执行。在变量初始化阶段，VO按照如下顺序填充：
+  函数参数（若未传入，初始化该参数值为undefined） 
+  函数声明（若发生命名冲突，会覆盖） 
+  变量声明（初始化变量值为undefined，若发生命名冲突，则忽略）;
```js
var hehe = function() {
    console.log('我被赋值给变量hehe');
}
function hehe() {
    console.log('我是具名函数hehe');
}
hehe(); // 我被赋值给变量hehe 说明函数申明在先 变量申明在后

```

## 函数的重载：

+ 重载函数是函数的一种特殊情况，为方便使用，C++允许在同一范围中声明几个功能类似的同名函数，但是这些同名函数的形式参数（指参数的个数、类型或者顺序）必须不同，也就是说用同一个运算符完成不同的运算功能。这就是重载函数。重载函数常用来实现功能类似而所处理的数据类型不同的问题。

+ javascript 是没有函数重载的，申明多个，后申明会覆盖先申明的函数.
+ 有一个方法可以实现函数的重载，通过重载这个构造函数让他根据传入参数的不同来执行不同的初始化方法。

**重载set 函数**

```js
function set(){
    this.values={};
    this.n=0;
    if(arguments.length==1&&isArrayLike(arguments[0]){
      this.add.play(this,arguments[0])
    }else if(arguments.length>0){
      this.add.play(this,arguments);
    }
}
```
## getter 和 setter 对象的存取器属性 
+ 和数据属性不同，存取器属性 ，不具可写行 ，如果属性同时具有getter 和setter 方法 那么他就是有读写属性  
+ 定义存取器属性最简单的的方法是使用对象的直接量语的一种扩展写法 

```js
var  o= {
         data_prop:value,
         get accessor_prop(){
             //     函数体
         },
         set accessor_prop ( value){
             //     函数体
         }
     }
 ？
//  修改对象的set和get 属性  
var o={};

Object.definepeoperty(o,name,{
value:1,
writable:true,
enumerable:false,
configurable:fals
})
```









