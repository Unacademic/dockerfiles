FROM ubuntu:15.04
MAINTAINER Jan Hein Hoogtad

ENV IOJS_VERSION 1.8.1

RUN apt-get update && \
    apt-get -y install vim-gtk curl git make g++ python tmux
RUN curl http://j.mp/spf13-vim3 -L -o - | sh && \
    echo "set encoding=utf-8" >> ~/.vimrc.local && \
    echo "imap jj <esc>">> ~/.vimrc.local
RUN echo "set-option -g prefix C-a" >> ~/.tmux.conf
RUN curl -SLO "https://iojs.org/dist/v$IOJS_VERSION/iojs-v$IOJS_VERSION-linux-x64.tar.gz" && \
    tar -xzf "iojs-v$IOJS_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 && \
    rm "iojs-v$IOJS_VERSION-linux-x64.tar.gz"
RUN git clone https://github.com/Unacademic/unacademic-frontend.git &&\
    cd unacademic-frontend && npm install
WORKDIR unacademic-frontend

RUN cp index.html build
RUN TERM='xterm-256color' 

CMD git pull && npm install && /bin/bash

EXPOSE 8080
