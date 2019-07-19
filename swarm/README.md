#### 클러스터링 - 매니저 노드
> docker-machine ssh manager  
> docker swarm init ...  
> exit  

#### 클러스터링 - 워커 노드
> docker-machine ssh worker1  
> docker swarm join ...  
> exit  

#### 클러스터링 - 스웜 노드 조회
> docker node ls  

#### 서비스 생성
> docker service create -d -p 80:80 --name whoami moricom/nodejs-whoami  
#### 서비스 목록/상세/테스팅
> docker service ls  
> docker service ps whoami  
> curl http://192.168.99.100  
#### 서비스 확장
> docker service scale -d whoami=3  
#### 서비스 롤링 업데이트
> docker service update -d --image moricom/hello-rest --health-cmd="curl -sS 127.0.0.1:80" --health-retries=3 --health-interval=5s whoami  
