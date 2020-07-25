# Git 的常使用的命令和方法




###  remote 

+ git remote -v  查看远程库

+ git remote rm origin    删除远程仓库

+ git remote add origin ‘youlocation’  关联远程仓库

+ git rm -r --cached . 清除缓存

+ git clean -df     清空文件目录

+ rm -rf .git  删除本地git init 


### diff  

+ git diff  --name-status      只查看修改的文件名字

+ git diff head --<filename>   工作区vs版本库
 
+ git  diff -cached  缓存区vs版本库
 
+ git  diff  工作区vs缓存区


***假设仓库里已提交的有五个版本，依次提交的是A、B、C、D、E***

+ git diff HEAD^  版本 E 和D 的区别 

+ git diff  HEAD^^   当前 版本 和C  版本的区别


### show 

+ git show  commit_id 查看

### 三大分区的好处 （通过 checkout/stash/reset 等命令） 通过不同的参数搭配使用

+ <tag>





###  reset 

+ git  reset --hard HEAD   回退一个版本 
+ git  reset --hard commit_id  回退到任意的版本  版本号只要前几个就好 版本回退 
+ git  reset  commit_id   对应的版本回退  版本号只要前几个就好  但是代码还是 本地的 需Git checkout .
+ git  reset HEAD   取消git  add  的内容  加上 Git checout  . 取消修改
+ git  checkout .   改变的取消

### blame

+ git   blame   查看某一个文件最近一次谁修改的    后面加版本号  是相对于版本之前的的修改记录

### push 

+ git push origin --delete <BranchName> 删除远程的分支
 
+ git fetch -p origin  更新远程分支  

+ git push origin master —force   强推   

+ git push origin  --tags    推送所有的tags  

### pull

+ git pull origin master --allow-unrelated-histories


### branch 

+ git branch -d <BranchName>   删除本地分支
 
+ git branch  name   创建分支

+ git push origin new_branch  远程创建分支
 
+ git branch -a 查看分支

+ git checkout -b 本地分支名x origin/远程分支名x   拉去一个远程分支 到本地
 
+ git checkout -b ```branchname``` origin/```branchname```  常见关联
 
+ git  checkout name 切换分支
 
### tag

+ git tag [tagName] 添加tag  
+ git push origin [tagName]
+ git tag -d [tagName]  删除本地
+ git tag  查看 所有tag
+ git tag -l -n 查看分支和 标注

 ### 流程 
 
+ git的 四大区域  工作区—— 缓存区—— 版本库（本地仓库）—— 远程库

+ ## workspace  _____index  _____  local repository  ______ remote resository  
  

  ## 本地代码  _______add  * _________ commit -m ________________push    
  


 





 
 
 
 

