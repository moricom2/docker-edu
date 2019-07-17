# dockerfiles
https://hub.docker.com/r/moricom/ubuntu-ko

https://hub.docker.com/r/moricom/devbox


# Dockerfile 지시어
지시어	설명

FROM	베이스 이미지 지정

MAINTAINER	Dockfile 생성자

RUN	명령어 실행

CMD	데몬 실행

LABEL	라벨 설정

EXPOSE	포트 export

ENV	환경변수 설정

ADD	파일/디렉토리 추가

COPY	파일 복사

VOLUME	볼륨 마운트

ENTRYPOINT	데몬실행

USER	사용자 설정

WORKDIR	작업디렉토리 설정

ONBUILD	build 완료후 실행할 명령어

