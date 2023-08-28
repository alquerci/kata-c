FROM alpine:3.18.3

RUN set -eux; \
    apk add --no-cache \
        build-base \
        clang \
        clang-extra-tools

RUN set -eux; \
    apk add --no-cache \
        ruby

ENV UNITY_ROOT /usr/local/share/unity

RUN set -eux; \
    version='cb03c3afa777b004a809f72535648a475c84a6e1'; \
    apk add --no-cache \
        curl \
    ; \
    \
    tmpDir='/tmp/unity'; \
    mkdir -p "${tmpDir}"; \
    curl -sSLf https://github.com/ThrowTheSwitch/Unity/archive/${version}.tar.gz | tar -C "${tmpDir}" -zxf -; \
    \
    mkdir -p "${UNITY_ROOT}"; \
    rmdir "${UNITY_ROOT}"; \
    mv "${tmpDir}"/Unity-${version} "${UNITY_ROOT}"; \
    \
    apk del --no-cache curl; \
    :;

COPY bin/ /usr/local/bin/
