FROM golang:1.10.3-alpine3.8

# install xz tzdata zip ca-certificates wget
RUN apk --no-cache add tzdata zip ca-certificates wget upx git dep glide

# install UPX
# ADD https://github.com/upx/upx/releases/download/v3.94/upx-3.94-amd64_linux.tar.xz /usr/local
# RUN xz -d -c /usr/local/upx-3.94-amd64_linux.tar.xz | \
#  tar -xOf - upx-3.94-amd64_linux/upx > /bin/upx && \
#  chmod a+x /bin/upx

# glide
#ENV GLIDE_ARCH linux-amd64
#ENV GLIDE_VERSION 0.13.1
#ENV GLIDE_ARCHIVE glide-v$GLIDE_VERSION-$GLIDE_ARCH.tar.gz

#RUN cd /tmp \
#  && wget https://github.com/Masterminds/glide/releases/download/v$GLIDE_VERSION/$GLIDE_ARCHIVE \
#  && tar xf $GLIDE_ARCHIVE \
#  && mv $GLIDE_ARCH/glide /usr/local/bin \
#  && rm $GLIDE_ARCHIVE

# Install Dep
#RUN go get -u github.com/golang/dep/cmd/dep

# Install fresh
RUN go get github.com/pilu/fresh

# Create zoneinfo
WORKDIR /usr/share/zoneinfo
RUN zip -r -0 /usr/share/zoneinfo/zoneinfo.zip .

