#### Docher Container Create & Run
> docker run -itd --name ubuntu ubuntu:latest 

#### Docher Container Exec
> docker exec ubuntu cat /etc/os-release 
> docker exec -it ubuntu bash 
>> locale 
>> apt-get update 
>> apt-get install -y locales 
>> locale-gen ko_KR.UTF-8 
>> locale -a 
>> date 
>> apt-get install -y tzdata 
>> exit 

#### Docker Container to Image
> docker commit ubuntu ubuntu-ko:test 

#### Docker Image Rename
> docker image ls 
> docker tag ubuntu-ko:test moricom/ubuntu-ko:test 

#### Docher Container Env & Remove
> docker run -it -e LC_ALL=ko_KR.UTF-8 -e TZ=Asia/Seoul --rm moricom/ubuntu-ko:test bash 
>> locale 
>> date 
>> exit 

#### Dockerfile Build 
> docker build -t moricom/ubuntu-ko:latest . 

#### Docker Image History
> docker history moricom/ubuntu-ko:test 
> docker history moricom/ubuntu-ko:latest 