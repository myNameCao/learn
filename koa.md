# KOA2
  
+ ### Koa vs Express
中间件的***处理上*** : Express由于是在ES6特性之前的，
中间件的基础原理还是callback方式的；而koa得益于generator特性和co框架（co会把所有generator的返回封装成为Promise对象），使得中间件的编写更加优雅。
