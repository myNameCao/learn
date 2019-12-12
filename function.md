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
   + 函数的prototype 属性
   
     ***call*** 和 ***apply***
     
     可以看做是方法的借用 通过调用方法间接的调用函数，call 和apply 的第一个实参是要调用函数的的母函数，他是调用上下文，在函数体内通过this 来获得它的引用，要想以对象o的方法来调用函数f() ,可以使用call() 和apply()
     
     ```js
     f.call(O)
     f.apply(O)
     
       === 
     
      o.m=f
      o.m()
      delete o.m
    
     ```
 
