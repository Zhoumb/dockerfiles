FROM alpine:3.9
LABEL maintainer="zhoumb@qq.com" version="3.9"

ENV LANG C.UTF-8
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories \
  && apk add -U tzdata  \
  && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
  && echo 'Asia/Shanghai' >/etc/timezone \
  && apk del tzdata
