FROM ubuntu:xenial

COPY Makefile /lucida/Makefile
COPY Makefile.common /lucida/Makefile.common
#COPY tools /lucida/tools

RUN mkdir -p /lucida/tools
WORKDIR /lucida/tools

# apt_deps
COPY tools/apt_deps.sh /lucida/tools/apt_deps.sh
RUN ./apt_deps.sh

ENV THREADS=4
ENV LD_LIBRARY_PATH=/usr/local/lib

# python
COPY tools/install_python.sh /lucida/tools/install_python.sh
COPY tools/python_requirements.txt /lucida/tools/python_requirements.txt
RUN ./install_python.sh

# java
COPY tools/install_java.sh /lucida/tools/install_java.sh
RUN ./install_java.sh

COPY tools/install_opencv.sh /lucida/tools/install_opencv.sh
COPY tools/check_opencv.cpp /lucida/tools/check_opencv.cpp
RUN ./install_opencv.sh

# thrift
COPY tools/check_thrift.thrift /lucida/tools/check_thrift.thrift
COPY tools/install_thrift.sh /lucida/tools/install_thrift.sh
RUN ./install_thrift.sh

# fbthrift
COPY tools/install_fbthrift.sh /lucida/tools/install_fbthrift.sh
RUN ./install_fbthrift.sh

# mongodb
COPY tools/install_mongodb.sh /lucida/tools/install_mongodb.sh
RUN ./install_mongodb.sh

COPY lucida /lucida/lucida

