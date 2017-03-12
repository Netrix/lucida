FROM lucida/djinntonic_base

WORKDIR /lucida/lucida/djinntonic/dig
RUN export CPATH=$CPATH:/usr/include/hdf5/serial && \
    export LIBRARY_PATH=$LIBRARY_PATH:/usr/lib/x86_64-linux-gnu/hdf5/serial/ && \
	make

