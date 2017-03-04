FROM ubuntu:xenial

COPY Makefile /lucida/Makefile
COPY Makefile.common /lucida/Makefile.common
COPY lucida /lucida/lucida
COPY tools /lucida/tools

WORKDIR /lucida/tools

RUN ./apt_deps.sh
RUN ./install_python.sh
RUN ./install_java.sh
RUN ./install_thrift.sh
RUN ./install_fbthrift.sh
RUN ./install_mongodb.sh

