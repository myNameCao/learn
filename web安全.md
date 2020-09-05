## web 安全

###  XSS  跨站脚本工具

+ 反射型
 
 上传 script 放在url后面诱导客户
 
 + 存储型
 
 #### 预防的形式： 
  
  * 特殊字符转化为 HTML 实体，这样在输出时，恶意的代码就无法执行了
  *  提交 代码字符串 保存到服务器 ，用户进入后 被动 被攻击
  * httpOnly:由于很多的xss 攻击都是盗用 cookie因此  可以通过 使用 httponly 属性防止直接通过 coument.cookie 来获取 cookie
  
  ### CSRF 跨站请求伪造
  
  预防的方式：1. 二次的确认 ，token 的认证
  


###  文件上传漏洞
