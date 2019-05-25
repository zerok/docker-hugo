FROM debian:stretch-slim AS builder
ENV HUGO_VERSION 0.55.6
WORKDIR /src
RUN apt-get update && apt-get -y install curl && curl -L -o hugo_extended_${HUGO_VERSION}.tar.gz https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_Linux-64bit.tar.gz && \
        tar -xzvf hugo_extended_${HUGO_VERSION}.tar.gz


FROM debian:stretch-slim
LABEL maintainer="zerok@zerokspot.com"
ENV HUGO_VERSION 0.55.6
WORKDIR /src
ENTRYPOINT ["/usr/local/bin/hugo"]
COPY --from=builder /src/hugo /usr/local/bin/
