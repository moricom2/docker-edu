FROM moricom/ubuntu-ko:latest
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    tar \
    vim \
    git \
    openjdk-8-jdk
RUN wget http://mirror.apache-kr.org/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz
RUN tar xzvf apache-maven-3.6.1-bin.tar.gz -C /usr/share/
RUN update-alternatives --install /usr/bin/mvn mvn /usr/share/apache-maven-3.6.1/bin/mvn 9999
WORKDIR /workspace
