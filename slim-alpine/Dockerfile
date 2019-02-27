FROM golang:1.12.0-alpine
RUN find /usr/local/go -name "*.tar" -type f -delete; \
    find /usr/local/go -name "*.bz2" -type f -delete; \
    find /usr/local/go -name "*.zip" -type f -delete

# use the same base image as golang:1.12.0-alpine but without the other layers which have
# testdata that we don't want
FROM alpine:3.9
COPY --from=0 /usr/local/go /usr/local/go

# setup path to match normal golang image
ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH

