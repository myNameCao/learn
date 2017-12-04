 # shell
 ----------
 ## tar 压缩
 
 tar [-zxcvfpP] filename 
 
 + -z  是否同时具有gzip 
 
 + -x  解开一个压缩文件 
 
 + -t  查看tarfile 里面的文件 
 
 + -c  建立一个压缩文件 
 
 + -v  压缩过程中显示文件  
 
 + -f  使用文件名 
 
 + -p  使用原文件的原有属性（属性不会依据用户而改变）
 
 + -P  使用绝对路径 
 
  ```js
 
   tar -cvf  direstory.tar  filename  // 打包filename文件
   tar -xvf   direstoru.tar  
   tar -zcvf direstory.tar filename //  打包压缩 
   tat  -zxvf  direstory.tar 解压
       
   
   
   
   
   
   
   
   
   ```
 
