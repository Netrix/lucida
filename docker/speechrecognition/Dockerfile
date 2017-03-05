FROM lucida/base

WORKDIR /lucida/lucida/speechrecognition/kaldi_gstreamer_asr

RUN make
RUN pip install pyyaml ws4py 
RUN sudo apt-get install -y python3.5-dev
