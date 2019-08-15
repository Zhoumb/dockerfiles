FROM zhoumb/android:base
LABEL maintainer="zhoumb@qq.com" version="24"

# see https://github.com/alvr/alpine-android/blob/master/android-24/Dockerfile
ENV BUILD_TOOLS "24.0.3"
ENV TARGET_SDK "24"

RUN ${ANDROID_HOME}/tools/bin/sdkmanager "build-tools;${BUILD_TOOLS}" "platforms;android-${TARGET_SDK}"
