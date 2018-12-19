FROM resin/rpi-raspbian:jessie
ARG CHROMIUM_BASEURL=https://launchpad.net/~canonical-chromium-builds/+archive/ubuntu/stage/+build/8883797/+files
ARG CHROMIUM_DEB_FILE1=chromium-codecs-ffmpeg-extra_48.0.2564.82-0ubuntu0.15.04.1.1193_armhf.deb
ARG CHROMIUM_DEB_FILE2=chromium-browser_48.0.2564.82-0ubuntu0.15.04.1.1193_armhf.deb

RUN sudo apt-get update && \
    sudo apt-get install wget ttf-mscorefonts-installer libgnome-keyring0 && \
    useradd -ms /bin/bash chromium && \
    wget -O /tmp/$CHROMIUM_DEB_FILE1 $CHROMIUM_BASEURL/$CHROMIUM_DEB_FILE1 && \
    wget -O /tmp/$CHROMIUM_DEB_FILE2 $CHROMIUM_BASEURL/$CHROMIUM_DEB_FILE2

COPY install-chromium-browser.sh /
RUN /install-chromium-browser.sh
USER chromium