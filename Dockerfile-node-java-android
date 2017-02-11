FROM openjdk:8-jdk

# prequistes for building android APK
RUN apt-get update && apt-get install -y lib32stdc++6 lib32z1

# 1. install android SDK

ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV PATH $PATH:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools:${ANDROID_HOME}/build-tools/23.0.2

ENV ANDROID_SDK android-sdk_r24.4-linux.tgz

RUN cd /usr/local/ && \
    wget -q http://dl.google.com/android/${ANDROID_SDK} && \
    tar -xzf ${ANDROID_SDK} && \
    rm ${ANDROID_SDK} && \
    echo y | android update sdk --no-ui --all --filter platform-tools,build-tools-23.0.2,build-tools-25,android-23,android-25,extra-android-support,extra-android-m2repository,extra-google-m2repository


# 2. install Node.js

ENV NODE_VERSION 7

RUN curl -sL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash - && \
	apt-get install --no-install-recommends -y nodejs  && \
    apt-get -y autoremove && \
    apt-get -y autoclean && \
    rm -rf /var/lib/apt/lists/*


# 3. Install cordova/ionic app dependencies (just an example)

ENV APP=/tmp/app

COPY bower.json package.json config.xml ionic.config.json gulpfile.js $APP/
COPY resources/ $APP/resources/
COPY gulp-tasks/ $APP/gulp-tasks/

WORKDIR $APP

RUN mkdir ./www && \
    npm install -g gulp bower cordova@6.4.0 ionic@2.2.1 && \
    cordova telemetry off && \
    bower install --allow-root && npm install && \
    cordova prepare
