FROM ubuntu:15.04

RUN apt-get update && \
    apt-get -y install vim-gtk curl git && \
    curl http://j.mp/spf13-vim3 -L -o - | sh && \
    mkdir temp && cd temp && \
    echo "set encoding=utf-8" >> ~/.vimrc.local && \
    echo "imap jj <esc>">> ~/.vimrc.local
