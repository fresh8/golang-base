FROM golang:1.10.3

# install xz
RUN apt-get update && apt-get install -y \
  xz-utils \
  && rm -rf /var/lib/apt/lists/*
# install UPX
ADD https://github.com/upx/upx/releases/download/v3.94/upx-3.94-amd64_linux.tar.xz /usr/local
RUN xz -d -c /usr/local/upx-3.94-amd64_linux.tar.xz | \
  tar -xOf - upx-3.94-amd64_linux/upx > /bin/upx && \
  chmod a+x /bin/upx

# glide
ENV GLIDE_ARCH linux-amd64
ENV GLIDE_VERSION 0.13.1
ENV GLIDE_ARCHIVE glide-v$GLIDE_VERSION-$GLIDE_ARCH.tar.gz

RUN cd /tmp \
  && wget https://github.com/Masterminds/glide/releases/download/v$GLIDE_VERSION/$GLIDE_ARCHIVE \
  && tar xf $GLIDE_ARCHIVE \
  && mv $GLIDE_ARCH/glide /usr/local/bin \
  && rm $GLIDE_ARCHIVE


# Create binary directory
RUN mkdir -p $$GOPATH/bin

# Install Dep
RUN go get -u github.com/golang/dep/cmd/dep

# Install fresh
RUN go get github.com/pilu/fresh
