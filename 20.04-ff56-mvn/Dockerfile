# docker build -t hrcarsan/ubuntu:20.04-ff56-mvn .
FROM hrcarsan/ubuntu:20.04-xvfb
LABEL maintainer="hrcarsan@gmail.com"

RUN export DEBIAN_FRONTEND=noninteractive \
 && apt-get update -y \
 # Install Maven
 && apt install -y --no-install-recommends maven \
 # Install Firefox
 && export VERSION=56.0 \
 && wget http://ftp.mozilla.org/pub/firefox/releases/${VERSION}/linux-x86_64/en-US/firefox-${VERSION}.tar.bz2 \
 && tar -xjf firefox-${VERSION}.tar.bz2 \
 && mv firefox /opt/ \
 && ln -s /opt/firefox/firefox /usr/bin/firefox \
 && rm firefox-${VERSION}.tar.bz2

ENV DISPLAY :99

# To run firefox
# docker run --rm -it hrcarsan/ubuntu:20.04-ff56-mvn bash
# Xvfb :99 -screen 0 1024x768x16 -ac -nolisten tcp -nolisten unix &
# firefox
