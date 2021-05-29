# docker build -t hrcarsan/ubuntu:20.04-chrome88 .
FROM ubuntu:20.04
LABEL maintainer="hrcarsan@gmail.com"

RUN export DEBIAN_FRONTEND=noninteractive \
 && apt-get update -y \
 # install xvfb
 && apt-get install -y --no-install-recommends gconf-service libasound2 libatk1.0-0 libc6 libcairo2 \
    libcups2 libdbus-1-3 libgbm1 \
    libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 \
    libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 \
    libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 \
    ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget \
    xvfb x11vnc x11-xkb-utils xfonts-100dpi xfonts-75dpi xfonts-scalable xfonts-cyrillic x11-apps \
 # install Google Chrome 88.0.4324.96
 && cd /tmp \
 && wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb \
 && dpkg -i google-chrome-stable_current_amd64.deb \
 && rm google-chrome-stable_current_amd64.deb

ENV DISPLAY :99

# To run chrome
# docker run --rm -it hrcarsan/ubuntu:20.04-chrome88 bash
# Xvfb :99 -screen 0 1024x768x16 &
# google-chrome --no-sandbox
