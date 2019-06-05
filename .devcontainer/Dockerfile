FROM debian:stretch-slim

# Install flutter & some deps
RUN apt update && apt install -y curl wget git xz-utils
RUN wget https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_v1.5.4-hotfix.2-stable.tar.xz \
  && tar xf flutter_linux_v1.5.4-hotfix.2-stable.tar.xz \
  && rm flutter_linux_v1.5.4-hotfix.2-stable.tar.xz
ENV PATH="/flutter/bin:${PATH}"
RUN flutter precache

# Set a useful default shell
ENV SHELL /bin/bash