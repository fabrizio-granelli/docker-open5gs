FROM node:carbon

MAINTAINER Jose Nuñez <jonunyez@gmail.com>

ARG PACKAGE=open5gs
ARG VERSION=1.2.1

RUN set -e; \
    cd /usr/src; \
    rm -rf ./$PACKAGE; \
    curl -SLO "https://github.com/open5gs/$PACKAGE/archive/v$VERSION.tar.gz"; \
    tar -xvf v$VERSION.tar.gz; \
    mv ./$PACKAGE-$VERSION/ ./$PACKAGE;

WORKDIR /usr/src/open5gs/webui
RUN npm install 
RUN npm run build

EXPOSE 3000
