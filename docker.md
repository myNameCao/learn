# docker 


### 创建数据库

docker run -itd --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=chris mysql:5.7.28

### 启动容器

docker start id 

### 退出容器 

Ctrl+P+Q

### 进入容器  

docker exec -it `id`  /bin/bash

