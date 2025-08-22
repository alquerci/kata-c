FROM alpine:3.18.3

RUN set -eux; \
    apk add --no-cache \
        gdb \
        build-base

RUN set -eux; \
    apk add --no-cache \
        ruby

RUN gem install ceedling:1.0.1
