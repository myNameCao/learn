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

ssh root@47.99.XX.XX

## cat  （查看命令）

## 进程列表 
你可以在一行中指定依次运行的一系列命令  这可以通过命令之间加入分号（;）
pwd ;ls  cd filename ;pwd  


## pwd  打印路径 
  
## echo  打印  反射 

## ps  列出所有的进程

## jobs 显示后台作业信息 等于 ps 

## history  显示你用过的命令

## alias  设置别名 

alias li='ls -al' 定义自己的别名(如果想写永久的可以在.bashrc  写 永久的)

scp -r * root@39.98.49.4:/var/www/html/chope

