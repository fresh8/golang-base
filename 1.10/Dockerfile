FROM golang:1.10.3-alpine3.8

# install xz tzdata zip ca-certificates wget
RUN apk --no-cache add tzdata zip upx dep

# Create zoneinfo
WORKDIR /usr/share/zoneinfo
RUN zip -r -0 /usr/share/zoneinfo/zoneinfo.zip .

