
 # [yarn](https://classic.yarnpkg.com/zh-Hans/)
 
 ## yarn  的 优势
 
 + 速度快 。速度快主要来自以下两个方面
 
           1.  并行安装：npm 是按照队列执行每个 package，也就是说必须要等到当前 package 安装完成之后，才能继续后面的安装。
           2. Yarn 是同步执行所有任务，提高了性能
           3.  离线模式：如果之前已经安装过一个软件包，用Yarn再次安装时之间从缓存中获取，就不用像npm那样再从网络下载了。
   
 + 安装版本统一
 
         取到不同的版本，Yarn 有一个锁定文件 (lock file) 记录了被确切安装上的模块的版本号。每次只要新增了一个模块，
         Yarn 就会创建（或更新）yarn.lock 这个文件
 
 
 + 更简洁的输出 
 
        1.  npm 的输出信息比较冗长。在执行 npm install 的时候，命令行里会不断地打印出所有被安装上的依赖。
        2.  Yarn 简洁太多：默认情况下，结合了 emoji直观且直接地打印出必要的信息，也提供了一些命令供开发者查询额外的安装信息
     
+ 多注册来源处理

       1.所有的依赖包，不管他被不同的库间接关联引用多少次，安装这个包时，只会从一个注册来源去装，要么是 npm 要么是 bower, 防止出现混乱不一致。


##  项目升级 

1. 全局下载yarn  
      > 服务器 
      
      下载`pacman -S yarn`
         
      查看`yarn --version`
      
      >前端 windon 
      
     下载` npm i yarn  -g `
     
     查看`yarn --version`
     
 2. 项目删除 `node_modules` 文件
 
 3. yarn 下载
 
 >在项目 跟目录(package.json 文件同级) 执行  `yarn`
      
      
