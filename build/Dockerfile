FROM golang:1.14-alpine as buildimage

COPY src /go/src/go-helloworld
RUN  cd /go/src/go-helloworld; go build
RUN  ls -l /go/src/go-helloworld

FROM alpine:3.12
COPY --from=buildimage /go/src/go-helloworld/helloworld .

ENTRYPOINT ["./helloworld"]