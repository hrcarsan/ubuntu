# docker build -t hrcarsan/ubuntu:20.04-chrome91 .
FROM hrcarsan/ubuntu:20.04-xvfb
LABEL maintainer="hrcarsan@gmail.com"

RUN export DEBIAN_FRONTEND=noninteractive \
 && apt-get update -y \
 ## install dependencies
 && apt-get install -y --no-install-recommends libcurl3-gnutls libcurl3-nss libcurl4 \
 # Install Google Chrome
 # Note: Check available versions here
 #   https://www.ubuntuupdates.org/package/google_chrome/stable/main/base/google-chrome-stable
 && cd /tmp \
 && export VERSION=91.0.4472.77-1 \
 && wget \https://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${VERSION}_amd64.deb \
 && dpkg -i google-chrome-stable_${VERSION}_amd64.deb \
 && rm google-chrome-stable_${VERSION}_amd64.deb

ENV DISPLAY :99

# To run chrome
# docker run --rm -it hrcarsan/ubuntu:20.04-chrome91 bash
# Xvfb :99 -screen 0 1024x768x16 &
# google-chrome --no-sandbox
