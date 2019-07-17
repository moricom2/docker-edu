FROM ubuntu:latest
RUN apt-get update && apt-get install -y \
    locales \
    tzdata

RUN locale-gen ko_KR.UTF-8
ENV LC_ALL ko_KR.UTF-8
ENV TZ Asia/Seoul
