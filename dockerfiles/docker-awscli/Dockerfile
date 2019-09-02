FROM docker:17.12.0-ce as static-docker-source
FROM debian:latest
COPY --from=static-docker-source /usr/local/bin/docker /usr/local/bin/docker
RUN apt-get update && apt-get install -y \
    python \
    python-pip
RUN pip install awscli
