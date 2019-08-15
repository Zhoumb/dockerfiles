FROM zhoumb/android:28 AS android

FROM jenkins/jenkins:2.184-alpine
LABEL maintainer="zhoumb@qq.com" version="2.184"

# ses https://github.com/xmartlabs/docker-jenkins-android
ENV ANDROID_HOME "/opt/sdk"
COPY --from=android ${ANDROID_HOME} ${ANDROID_HOME}
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

USER root
RUN apk add -U tzdata  \
  && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
  && echo 'Asia/Shanghai' >/etc/timezone \
  && apk del tzdata \
  && chown -R jenkins:jenkins ${ANDROID_HOME}
USER jenkins
