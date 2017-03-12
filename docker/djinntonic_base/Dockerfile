FROM lucida/base

WORKDIR /lucida/lucida/djinntonic/tools

RUN ./install-protobuf.sh
RUN export CPATH=$CPATH:/usr/include/hdf5/serial && \
	export LIBRARY_PATH=$LIBRARY_PATH:/usr/lib/x86_64-linux-gnu/hdf5/serial/ && \
	./install-caffe.sh
RUN cp common.hpp caffe/distribute/include/caffe/common.hpp

WORKDIR /lucida/lucida/djinntonic

RUN python -mthrift_compiler.main --gen cpp2 ../lucidaservice.thrift
RUN python -mthrift_compiler.main --gen cpp2 ../lucidatypes.thrift

WORKDIR /lucida/lucida/djinntonic/models
RUN wget http://web.eecs.umich.edu/~jahausw/download/djinn-weights-1.0.tar.gz && tar xvzf djinn-weights-1.0.tar.gz && rm -rf djinn-weights-1.0.tar.gz;

ENTRYPOINT echo djinntonic_base done
