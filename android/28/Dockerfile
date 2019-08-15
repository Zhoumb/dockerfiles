FROM zhoumb/android:base
LABEL maintainer="zhoumb@qq.com" version="28"

# see https://github.com/alvr/alpine-android/blob/master/android-28/Dockerfile
ENV BUILD_TOOLS "28.0.3"
ENV TARGET_SDK "28"

RUN ${ANDROID_HOME}/tools/bin/sdkmanager "build-tools;${BUILD_TOOLS}" "platforms;android-${TARGET_SDK}"
