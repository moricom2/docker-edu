### 워드프레스 컨테이너로 실행하기 (--link 옵션)

[mysql](https://hub.docker.com/_/mysql)  
> docker run -d –name wp-db -e MYSQL_ROOT_PASSWORD=mysql -e MYSQL_DATABASE=wordpress mysql:5.7  

[wordpress](https://hub.docker.com/_/wordpress)  
> docker run -d –name wp –link wp-db:mysql -e WORDPRESS_DB_PASSWORD=mysql -p 80:80 wordpress:latest  

#### 전용 네트워크를 사용해서 만들기 (--net 옵션)
> docker network create wp-net  
> docker run -d –name wp-db -e MYSQL_ROOT_PASSWORD=mysql -e MYSQL_DATABASE=wordpress –net=wp-net mysql:5.7  
> docker run -d –name wp -e WORDPRESS_DB_HOST=wp-db:3306 -e WORDPRESS_DB_PASSWORD=mysql -p 80:80 –net=wp-net wordpress:latest  

#### docker-compose 로 blog라는 프로젝트로 묶어서 멀티컨테이너 관리
[https://github.com/moricom2/docker-edu/blob/master/compose/blog/docker-compose.yml](https://github.com/moricom2/docker-edu/blob/master/compose/blog/docker-compose.yml)  