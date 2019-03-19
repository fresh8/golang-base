FROM golang:1.12.1

# install xz
RUN apt-get update && apt-get install -y \
    xz-utils \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# install UPX
ADD https://github.com/upx/upx/releases/download/v3.94/upx-3.94-amd64_linux.tar.xz /usr/local
RUN xz -d -c /usr/local/upx-3.94-amd64_linux.tar.xz | \
    tar -xOf - upx-3.94-amd64_linux/upx > /bin/upx && \
    chmod a+x /bin/upx

# Install Dep
RUN go get -u github.com/golang/dep/cmd/dep
