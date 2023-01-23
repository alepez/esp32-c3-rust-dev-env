FROM ubuntu:22.04

RUN apt-get update -yy
RUN apt-get upgrade -yy
RUN apt-get install -yy \
  bison \
  ccache \
  cmake \
  dfu-util \
  flex \
  git \
  gperf \
  libffi-dev \
  libssl-dev \
  libusb-1.0-0 \
  ninja-build \
  python3 \
  python3-venv \
  wget

ENV IDF_TOOLS_PATH=/opt/espressif

RUN \
  mkdir /opt/esp && \
  cd /opt/esp && \
  git clone -b v5.0 --recursive https://github.com/espressif/esp-idf.git && \
  cd esp-idf && \
  ./install.sh esp32c3

RUN echo '. /opt/esp/esp-idf/export.sh &>/dev/null' >> /etc/bash.bashrc
