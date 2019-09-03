FROM jenkins/jenkins:2.193-alpine

USER root
ENV LANG C.UTF-8
RUN echo http://mirrors.ustc.edu.cn/alpine/v3.6/main > /etc/apk/repositories && \
  apk add -U tzdata && \
  cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
  echo 'Asia/Shanghai' >/etc/timezone && \
  apk del tzdata
USER jenkins
