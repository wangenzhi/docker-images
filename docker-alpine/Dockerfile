FROM alpine:latest
MAINTAINER "WangEnZhi W_enzhi@163.com"

# Delete the cache And Configure aliyun Repository
RUN rm -rf /var/cache/apk/* && \
    rm -fr /tmp/* && \
    echo https://mirrors.aliyun.com/alpine/v3.8/main > /etc/apk/repositories && \
    echo https://mirrors.aliyun.com/alpine/v3.8/community >> /etc/apk/repositories
RUN apk update && apk upgrade

# Install alpine-pkg-glibc
RUN apk --no-cache add ca-certificates wget && \
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
    wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.28-r0/glibc-2.28-r0.apk && \
    apk add glibc-2.28-r0.apk
