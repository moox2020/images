FROM golang:1.12-alpine as confd
ARG CONFD_VERSION=0.16.0
ADD https://github.com/kelseyhightower/confd/archive/v${CONFD_VERSION}.tar.gz /tmp/
RUN apk add --no-cache bzip2 make && \
    mkdir -pv /go/src/github.com/kelseyhightower/confd /etc/confd  && \
    cd /go/src/github.com/kelseyhightower/confd && \
    tar --strip-components=1 -zxf /tmp/v${CONFD_VERSION}.tar.gz && \
    go install github.com/kelseyhightower/confd && \
    rm -rf /tmp/v${CONFD_VERSION}.tar.gz
ENTRYPOINT ["/go/bin/confd"]
