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
