  ##  函数 Function 
  
  ### 函数的属性
  
 + 函数的length 属性
  
  函数的length 指函数的形参的个数， **不是实参arguments 的长度**
   
   ```js 
   
   function checkout (args){
     var actual = args.length
     var expected = args.callee.length 
     if(actual !== expected){
     throw Error (`参数不匹配 `)
     }
   )
   funtion f(x,y,z){
   checkout(arguments)
   return x+y+z
   }

   ```
   
   + 每个对象都有一个__proto__属性，并且指向它的构造函数的prototype原型对象
   + 每个构造函数都有一个prototype原型对象
   + prototype原型对象里的constructor指向构造函数本身
   
   ### 函数的柯里化
   
  + 用于创建已经设置好的了一个或多个参数的函数
  + 函数的柯里化的基本方法和函数绑定是一样的：使用一个闭包返回一个函数
  + 两者的区别是：当函数被调用时,返回的函数还需要设置一些传入的参数
  
  
 ``` js
 function curry (fn) {
    var  args = Array.prototype.slice.call(argument,1)
     return function(){
     var interargs = Array.prototype.slice.call(arguments)
     var finalArgs = args.concat(interArgs)
      return fn.apply(null,finalArgs)
        
     }
 }
 
 function add (num1,num2){
 return num1+num2
 }
 var curryAdd =curry(add,5)
 console.log(curryAdd(3)) // 8
 
 //或者两个参数都绑定了
  var curryAdd =curry(add,1,3)
 console.log(curryAdd()) // 4
 
 ```
 + 函数的柯里化还常常作为函数绑定的一部分包含在其中,构造更为复杂的bind() 函数  ***( 体现一 )***
 
 ```js  
function bind (fn,context) {
    var  args = Array.prototype.slice.call(argument,2)
     return function(){
     var interargs = Array.prototype.slice.call(arguments)
     var finalArgs = args.concat(interArgs)
      return fn.apply(context,finalArgs)
     }
 }
 
 ```
 函数柯里化  也可以是返回一个对象  ***（体现二）***
 
 ```js
 // promise 的实现
 
 class PromiseA {
   coustructor(executor){...}
   then(){...}
   catch(err){
     this.then(null,err)
   }
 }
 
 
 
 constructor(executor){
   this.status =  'PENDING';
   this.value = 'undefined';
   this.reason = 'undefined';
   this.onResolvedCallbacks=[];
   this.onRejectedCallbacks=[];
   let resolve = (value) = >{
     if(value instanceof promiseA){
        value.then(resolve.reject)
        return 
     }
     if(this.status==='PENDING'){
            this.value=value;
            this.status= 'RESOLVED'
            this.onResolvedCallbacks.forEach(fn=>fn())
     }
  }
  
  let reject = (reason) =>{
      if(this.status== 'PENDING'){
         this.reason =  reason ;
         this.status ='REJECTED';
         this.onRejectedCallbacks.forEach(fn=>fn())
      }
  }
  try{
    executor(resolve,reject)
  }catch(e){
     reject(e)
  }
   
 }

then(onFulfilled, onRejected) {
    onFulfilled = typeof onFulfilled === 'function' ? onFulfilled:v=>v
    onRejected = typeof onRejected === 'function' ? onRejected:e=>{throw e}
    let promise2 = new PromiseA((resolve, reject) => {
        if (this.status === RESOLVED) {
            setTimeout(() => {
                try {
                    let x = onFulfilled(this.value);
                    resolvePromise(promise2, x, resolve, reject);
                } catch (e) {
                    reject(e)
                }
            });
        }
        if (this.status === REJECTED) {
            setTimeout(() => {
                try {
                    let x = onRejected(this.reason);
                    resolvePromise(promise2, x, resolve, reject);
                } catch (e) {
                    reject(e)
                }
            });
        }
        if (this.status === PENDING) {
            this.onResolvedCallbacks.push(() => {
                setTimeout(() => {
                    try {
                        let x = onFulfilled(this.value);
                        resolvePromise(promise2, x, resolve, reject);
                    } catch (e) {
                        reject(err);
                    }
                });

            })
            this.onRejectedCallbacks.push(() => {
                setTimeout(() => {
                    try {
                        let x = onRejected(this.reason);
                        resolvePromise(promise2, x, resolve, reject);
                    } catch (e) {
                        reject(err);
                    }
                });
            })
        }
    })
    return promise2;
 }
 
 
 function resolvePromise(promise2, x, resolve, reject) {

        if (promise2 === x) {
            return reject(new TypeError('返回的promise和当前promise不能是同一个对象哦，会嵌入死循环'))
        }
        if ((typeof x === 'object' && x !== null) || typeof x === 'function') {
            try {
                let then = x.then;
                if (typeof then === 'function') {
                    then.call(x,y=> {
                        resolvePromise(promise2, y, resolve, reject)
                    },r=> {
                        reject(r)
                    }
                    )
                } else {
                    resolve(x)
                }
            } catch (err) {
                reject(err)
            }
        } else {
            resolve(x);
        }
        
        
}
 
 ```
  
   
   
   ### Call and Apply
   
   + 可以看做是方法的借用 通过调用方法间接的调用函数
   + call 和apply 的第一个实参是要调用函数的的母函数，他是调用上下文，在函数体内通过this 来获得它的引用
   + 要想以对象o的方法来调用函数f() ,可以使用call 和apply
   
  ```js
  f.call(O)
  f.apply(O)

   === 

  o.m=f
  o.m()
  delete o.m

  Math.max.apply(Math,[1,2,4,6])


  [1,2,3,4,5,3].reduce(funtion(x,y){
  return x>y?x:y
  })
  // 只需要在原来的基础上 用下拓展运算符 剩余运算符即可
  ```

 ### Call 手动实现
```js
Function.prototype.myCall = function(obj,...arg){
    obj._fn_ = this;
    obj._fn_(...arg);
    delete obj._fn_;
}
//测试
let test = {
  name:'test'
}
let o = {
  name:'o',
  fn:function(){
      console.log(this.name, ...arguments);  //这里把参数显示一下
  }
}
o.fn(1,2,3) // "o" 1 2 3
o.fn.call(test,1,2,3) // "test" 1 2 3
o.fn.myCall(test,1,2,3) // "test" 1 2 3
  ```
  
  
  ###  不使用es6 的写法   

```js 
  Function.prototype.myCall = function(obj){
  let arg = [];
  for(let i = 1 ; i<arguments.length ; i++){
      arg.push( 'arguments[' + i + ']' ) ;
      // 这里要push 这行字符串  而不是直接push 值
      // 因为直接push值会导致一些问题
      // 例如: push一个数组 [1,2,3]
      // 在下面👇 eval调用时,进行字符串拼接,JS为了将数组转换为字符串 ，
      // 会去调用数组的toString()方法,变为 '1,2,3' 就不是一个数组了，相当于是3个参数.
      // 而push这行字符串，eval方法，运行代码会自动去arguments里获取值
  }
  obj._fn_ = this;
  eval( 'obj._fn_(' + arg + ')' ) // 字符串拼接，JS会调用arg数组的toString()方法，这样就传入了所有参数
  delete obj._fn_;
}

```
 
### Bind

+ 当在函数f()上调用bind ()方法 并传入一个对象o 作为参数 这个方法返回一个新的函数
+ (以函数调用的方法)调用新的函数将会把原始的函数f()当做o的方法调用 
```js
function f(y) {return this.x+y}
var o = {x:1}
var g= f.bind(o)
g(2) // 3
```

 
+ 可以通过一下的代码轻易的实现这种绑定
```js 
  function bind (f,o){
    if(f.bind)return f.bind(o)
    else return function (){
    return f.apply(o,argument)
    }
  }
  
  Function.prototype.bind=function(o,args){
    var self = this,boundArg = arguments; 
    return function (){
    var interargs = Array.prototype.slice.call(arguments).concat(Array.prototype.slice.call(boundArg))
     self.apply(o,interargs)
    }
}
```
  

  
      
 
