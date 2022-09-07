FROM golang:1.17-alpine

RUN apk update && apk upgrade && apk add --no-cache git nodejs bash npm

RUN go get -u github.com/jteeuwen/go-bindata/...

RUN go get github.com/tools/godep

WORKDIR /go/src/github.com/sectenzorg/simple-go

COPY . .

ENV VERBOSE=0
ENV PKG=github.com/sectenzorg/simple-go
ENV ARCH=amd64
ENV VERSION=test

RUN build/build.sh

CMD [ "/go/bin/simple-go" ]