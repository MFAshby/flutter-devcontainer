FROM debian:stretch-slim

# Apt dependencies
RUN apt update && apt install -y curl wget git xz-utils lib32stdc++6

# Flutter
RUN wget https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_v1.5.4-hotfix.2-stable.tar.xz
RUN tar xf flutter_linux_v1.5.4-hotfix.2-stable.tar.xz 
RUN rm flutter_linux_v1.5.4-hotfix.2-stable.tar.xz
ENV PATH="/flutter/bin:${PATH}"

# Android SDK
RUN wget https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip 
RUN apt install unzip
RUN mkdir android-sdk && unzip /sdk-tools-linux-4333796.zip -d android-sdk
RUN rm /sdk-tools-linux-4333796.zip
ENV ANDROID_HOME="/android-sdk"
ENV PATH="/android-sdk/tools/bin:${PATH}"

# Java
RUN mkdir -p /usr/share/man/man1 \
    && mkdir -p /usr/share/man/man7
RUN apt install openjdk-8-jdk-headless -y

# SDK manager
RUN yes | sdkmanager --licenses
RUN sdkmanager "platforms;android-28" "platform-tools" "build-tools;28.0.3"
ENV PATH="/android-sdk/tools:/android-sdk/build-tools:/android-sdk/platform-tools:${PATH}"

# Disable analytics
RUN flutter config --no-analytics

# Set a useful default shell
ENV SHELL /bin/bash

