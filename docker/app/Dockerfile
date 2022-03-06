FROM node:latest

RUN apt update && apt -y upgrade && apt -y dist-upgrade
RUN apt install -y zip unzip vim

RUN npm update -g npm

RUN apt install -y default-mysql-client

# Git最新版インストール
RUN apt -y remove git
RUN apt -y install libcurl4-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev libghc-zlib-dev autoconf asciidoc xmlto docbook2x make gcc gettext

RUN cd /tmp \
     && wget https://github.com/git/git/archive/v2.33.1.tar.gz \
     && tar -zxf v2.33.1.tar.gz \
     && cd git-2.33.1 \
     && make prefix=/usr/local all \
     && make prefix=/usr/local install \
     && cd ../ \
     && rm ./v2.33.1.tar.gz \
     && rm -r ./git-2.33.1
