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
   +  函数的prototype 属性
    + 每个对象都有一个__proto__属性，并且指向它的prototype原型对象
    + 每个构造函数都有一个prototype原型对象
    + prototype原型对象里的constructor指向构造函数本身
     ***call*** 和 ***apply***
     
     可以看做是方法的借用 通过调用方法间接的调用函数，call 和apply 的第一个实参是要调用函数的的母函数，他是调用上下文，在函数体内通过this 来获得它的引用，要想以对象o的方法来调用函数f() ,可以使用call() 和apply()
     
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
 
      
    
     ```
        ***bind非常重要的方法***
        
        
  当在函数f()上调用bind ()方法 并传入一个对象o 作为参数 这个方法返回一个新的函数 (以函数调用的方法)调用新的函数将会把原始的函数f()当做o的方法调用 
  
  ```js
  
  
  ```
      
 
