FROM arm32v7/ubuntu:18.04
 
ADD https://github.com/guysoft/pytorch-docker-armv7/raw/master/src/qemu-arm-static /usr/bin
 
RUN apt-get update;\
    apt-get install -y libopenblas-dev libblas-dev m4 cmake cython python3-dev python3-yaml python3-setuptools git;

RUN mkdir /build

WORKDIR /build

RUN git clone --recursive https://github.com/pytorch/pytorch

WORKDIR /build/pytorch

ENV NO_CUDA=1
ENV NO_DISTRIBUTED=1
ENV NO_MKLDNN=1
ENV NO_NNPACK=1
ENV NO_QNNPACK=1
RUN python3 setup.py build
RUN python3 setup.py install

 
CMD ["/bin/sh"]
