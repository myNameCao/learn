+ git branch -a 查看分支

+ git remote -v  查看远程库

+ git remote rm origin    删除远程仓库

+ git diff  --name-status      只查看修改的文件名字

+ git  checkout name 切换分支

+  git remote add origin ‘youlocation’  关联远程仓库
+   rm -rf .git  删除本地git init 

+  git branch  name   创建分支
+  git show   commit_id   查看
+  git push origin new_branch  某次远程创建分支
+ git checkout -b updateUi origin/updateUi  常见关联
+ git  reset --hard HEAD   回退一个版本 
+ git  reset --hard commit_id  回退到任意的版本  版本号只要前几个就好 版本回退 
+ git  reset  commit_id   对应的版本回退  版本号只要前几个就好  但是代码还是 本地的 需Git checkout .
+ git   blame   查看某一个文件最近一次谁修改的    后面加版本号  是相对于版本之前的的修改记录
+ git  checkout .   改变的取消
+ git push origin --delete <BranchName> 删除远程的分支
+ git branch -d <BranchName>   删除本地分支
+ git fetch -p origin  更新远程分支  
 +git push origin master —force   强推   
 
 
+ ## workspace  _____index  _____  local repository  ______ remote resository  
  ## 本地代码  _______add  * _________ commit -m ________________push       



 
 
 
 

