FROM busybox AS builder

ARG BUILDTYPE=AMD64

ENV URL_AMD64=https://aka.ms/downloadazcopy-v10-linux
ENV URL_ARM64=https://aka.ms/downloadazcopy-v10-linux-arm64

RUN eval url=\$URL_$BUILDTYPE && \
    wget $url -O azcopy.tar && \
    tar -xvf azcopy.tar && \
    mv azcopy_linux*/azcopy /

FROM alpine
LABEL maintainer="Boshi Lian<farmer1992@gmail.com>"

RUN apk add --no-cache ca-certificates && \
    update-ca-certificates

RUN apk add --no-cache gcompat

COPY --from=builder /azcopy /usr/bin/azcopy

CMD ["/usr/bin/azcopy"]
