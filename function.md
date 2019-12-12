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
