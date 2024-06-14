FROM alpine:latest

WORKDIR /box
COPY . /box

RUN mkdir /box/pb

# arm64 | amd64
ARG OS_ARCH=arm64
ARG PB_VERSION=0.22.13

RUN apk add --no-cache \
    unzip \
    ca-certificates

# download and unzip PocketBase
ADD https://github.com/pocketbase/pocketbase/releases/download/v${PB_VERSION}/pocketbase_${PB_VERSION}_linux_${OS_ARCH}.zip /box/pb.zip
RUN unzip /box/pb.zip -d /box/pb/

# uncomment to copy the local pb_migrations dir into the image
# COPY ./pb_migrations /pb/pb_migrations

# uncomment to copy the local pb_hooks dir into the image
# COPY ./pb_hooks /pb/pb_hooks
