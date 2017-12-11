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
   tat  -zxvf  direstory.tar //解压
   
   ```
 
## cpio 备份

+  -o 将数据复制出到文件或设备上

+  -i 将数据自文件或设备复制出到系统文件

+  -t  查看cpio建立的文件或设备的内容

+  -c  以一种较新的便携格式 储存

+  -v  让储存过程中文件名称可以在屏幕上显示 

+  -d  自动建立目录 由于cpio 的内容 可能不在同一目录

## ssh 登录 命令 




