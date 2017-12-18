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


