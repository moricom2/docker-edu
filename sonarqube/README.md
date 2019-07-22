### SonarQube 컨테이너 실행하기 위해서 머신의 리소스 수정 ###
> docker-machine stop manager  
> VBoxManage modifyvm manager --cpus 2  
> VBoxManage modifyvm manager --memory 4096  
> docker-machine start manager  

### SonarQube 컨테이너 실행 ###
[SonarQube](https://hub.docker.com/_/sonarqube)  
> docker run -d --name sonarqube -p 9000:9000 sonarqube  

