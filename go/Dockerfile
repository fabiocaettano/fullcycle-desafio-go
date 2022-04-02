
FROM ubuntu:latest as build

WORKDIR /usr/src/app

RUN apt-get update && \
    apt install wget -y

RUN wget https://go.dev/dl/go1.18.linux-amd64.tar.gz

RUN rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.linux-amd64.tar.gz

ENV PATH=$PATH:/usr/local/go/bin

RUN chmod 777 $HOME/.profile

RUN $HOME/.profile

RUN rm go1.18.linux-amd64.tar.gz

WORKDIR /usr/src/app/hello