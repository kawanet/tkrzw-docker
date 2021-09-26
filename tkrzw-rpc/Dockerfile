# vim:set ft=dockerfile:

FROM ubuntu:focal

RUN \
    apt-get update && \
    apt-get install -y --no-install-recommends \
        curl ca-certificates g++ make libz-dev libzstd-dev liblz4-dev liblzma-dev \
        libgrpc-dev libgrpc++-dev libprotobuf-dev protobuf-compiler-grpc \
        && \
	rm -rf /var/lib/apt/lists/* && \
    echo OK

# tkrzw

RUN \
    curl -sL https://github.com/estraier/tkrzw/archive/refs/heads/master.tar.gz | tar zxvf - -C /tmp && \
    cd /tmp/tkrzw-master && \
    ./configure --enable-opt-native --enable-most-features && \
    make clean all install && \
    /bin/rm -fr /tmp/tkrzw-master && \
    echo OK

# tkrzw-rpc

RUN \
    curl -sL https://github.com/estraier/tkrzw-rpc/archive/refs/heads/master.tar.gz | tar zxvf - -C /tmp && \
    cd /tmp/tkrzw-rpc-master && \
    ./configure && \
    make clean all install && \
    /bin/rm -fr /tmp/tkrzw-rpc-master && \
    echo OK

ENV LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH

EXPOSE 1978
