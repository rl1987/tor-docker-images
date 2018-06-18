FROM alpine:3.7

RUN apk update
RUN apk add gcc git automake autoconf make libcrypto1.0 libssl1.0 zlib-dev libevent musl-dev libc6-compat libevent-dev openssl-dev

RUN mkdir -p /src/tor

WORKDIR /src/tor
RUN git clone https://git.torproject.org/tor.git .
RUN ./autogen.sh && ./configure --disable-asciidoc && make && make install

ENTRYPOINT [ "tor" ]
