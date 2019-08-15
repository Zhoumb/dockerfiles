FROM zhoumb/alpine:3.9

ENV JAVA_VERSION=8 \
  JAVA_UPDATE=161 \
  JAVA_BUILD=12 \
  JAVA_PATH=2f38c3b165be4555a1fa6e98c45e0808 \
  JAVA_HOME="/usr/lib/jvm/default-jvm"

RUN apk add --no-cache --virtual=build-dependencies wget ca-certificates unzip && \
  cd "/tmp" && \
  wget --header "Cookie: oraclelicense=accept-securebackup-cookie;" \
  "http://download.oracle.com/otn-pub/java/jdk/${JAVA_VERSION}u${JAVA_UPDATE}-b${JAVA_BUILD}/${JAVA_PATH}/jre-${JAVA_VERSION}u${JAVA_UPDATE}-linux-x64.tar.gz" && \
  tar -xzf "jre-${JAVA_VERSION}u${JAVA_UPDATE}-linux-x64.tar.gz" && \
  mkdir -p "/usr/lib/jvm/java-${JAVA_VERSION}-oracle" && \
  mv "/tmp/jre1.${JAVA_VERSION}.0_${JAVA_UPDATE}" "/usr/lib/jvm/java-${JAVA_VERSION}-oracle/jre" && \
  ln -s "java-${JAVA_VERSION}-oracle/jre" "$JAVA_HOME" && \
  ln -s "$JAVA_HOME/bin/"* "/usr/bin/" && \
  rm -rf "$JAVA_HOME/../"*src.zip && \
  rm -rf "$JAVA_HOME/../lib/missioncontrol" \
  "$JAVA_HOME/../lib/visualvm" \
  "$JAVA_HOME/../lib/"*javafx* \
  "$JAVA_HOME/lib/plugin.jar" \
  "$JAVA_HOME/lib/ext/jfxrt.jar" \
  "$JAVA_HOME/bin/javaws" \
  "$JAVA_HOME/lib/javaws.jar" \
  "$JAVA_HOME/lib/desktop" \
  "$JAVA_HOME/plugin" \
  "$JAVA_HOME/lib/"deploy* \
  "$JAVA_HOME/lib/"*javafx* \
  "$JAVA_HOME/lib/"*jfx* \
  "$JAVA_HOME/lib/amd64/libdecora_sse.so" \
  "$JAVA_HOME/lib/amd64/"libprism_*.so \
  "$JAVA_HOME/lib/amd64/libfxplugins.so" \
  "$JAVA_HOME/lib/amd64/libglass.so" \
  "$JAVA_HOME/lib/amd64/libgstreamer-lite.so" \
  "$JAVA_HOME/lib/amd64/"libjavafx*.so \
  "$JAVA_HOME/lib/amd64/"libjfx*.so && \
  wget --header "Cookie: oraclelicense=accept-securebackup-cookie;" \
  "http://download.oracle.com/otn-pub/java/jce/${JAVA_VERSION}/jce_policy-${JAVA_VERSION}.zip" && \
  unzip -jo -d "${JAVA_HOME}/lib/security" "jce_policy-${JAVA_VERSION}.zip" && \
  rm "${JAVA_HOME}/lib/security/README.txt" && \
  apk del build-dependencies && \
  rm "/tmp/"*
