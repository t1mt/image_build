FROM golang:alpine AS builder
WORKDIR /workspace

ARG VERSION=3.16.4
ARG TARGETOS=linux
ARG TARGETARCH=amd64

RUN wget --no-check-certificate -O helm.tar.gz https://get.helm.sh/helm-v$VERSION-$TARGETOS-$TARGETARCH.tar.gz
RUN tar -zxvf helm.tar.gz --strip-components=1
RUN ls -al

FROM alpine:latest
COPY --from=builder /workspace/helm /usr/local/bin/helm