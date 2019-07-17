# Docker Image Build & Share
> docker build -t moricom/devbox .
> docker push moricom/devbox
> docker pull moricom/devbox

# Docker in Docker 
[CentOS7]\
> which docker
> docker run -itd -v /var/run/docker.sock:/var/run/docker.sock -v /usr/bin/docker:/usr/bin/docker --name devbox moricom/devbox

[https://labs.play-with-docker.com]\
> which docker
> docker run -itd -v /var/run/docker.sock:/var/run/docker.sock -v /usr/local/bin/docker:/usr/bin/docker --name devbox moricom/devbox

[Boot2Docker]\
> docker-machine ssh manager which docker
> docker run -itd -v /var/run/docker.sock:/var/run/docker.sock -v /usr/local/bin/docker:/usr/bin/docker --name devbox moricom/devbox